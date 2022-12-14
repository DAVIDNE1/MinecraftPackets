# C12PacketUpdateSign
This packet is sent by the client to set a signs text. It is called when the client closes the GuiEditSign is closed.
```java
this.mc.getNetHandler().addToSendQueue(new C12PacketUpdateSign(this.tileSign.getPos(), this.tileSign.signText));
```

## Params
```java
public C12PacketUpdateSign(BlockPos pos, IChatComponent[] lines)
```
> BlockPos, the position the sign is in the world

> An array of the 4 lines of text that will be written to the sign

## Use
After closing a GuiEditSign, the client sends an C12PacketUpdateSign.
```java
    /**
     * Called when the screen is unloaded. Used to disable keyboard repeat events
     */
    public void onGuiClosed()
    {
        Keyboard.enableRepeatEvents(false);
        NetHandlerPlayClient nethandlerplayclient = this.mc.getNetHandler();

        if (nethandlerplayclient != null)
        {
            nethandlerplayclient.addToSendQueue(new C12PacketUpdateSign(this.tileSign.getPos(), this.tileSign.signText));
        }

        this.tileSign.setEditable(true);
    }
```
The server has a few integrity checks that prevent you from simply editing any sign when you please.
Firstly it ensures the block is loaded.
```java
if (worldserver.isBlockLoaded(blockpos))
        {///
```
Secondly it verifies the block position specified is actually a sign.
```java
if (!(tileentity instanceof TileEntitySign)) {
                return;
}
```
And finally it confirms the sign has not already been edited, and if it has been edited it warns the server.
```java
if (!tileentitysign.getIsEditable() || tileentitysign.getPlayer() != this.playerEntity) {
  this.serverController.logWarning("Player " + this.playerEntity.getName() + " just tried to change non-editable sign");
  return;
}
```

