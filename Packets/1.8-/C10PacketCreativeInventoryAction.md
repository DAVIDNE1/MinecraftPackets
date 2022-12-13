# C10PacketCreativeInventoryAction

This packet is sent by the client when in creative, it can be used to generate any item (see the [Parameters](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C10PacketCreativeInventoryAction.md#params).

```java
    void sendSlotPacket
        if (this.currentGameType.isCreative())
            this.netClientHandler.addToSendQueue(new C10PacketCreativeInventoryAction(slotId, itemStackIn));
```

When dropping an item, the parameter slotIdIn is equal to -1.

Before the server begins processing the packet, it ensures the player is in creative.
```java

    /**
     * Update the server with an ItemStack in a slot.
     */
    public void processCreativeInventoryAction(C10PacketCreativeInventoryAction packetIn) {
        if (this.playerEntity.theItemInWorldManager.isCreative()) {
          //  ...
          //  ...
          //  ...
        }
     }
        
```

## Params
```java
public C10PacketCreativeInventoryAction(int slotIdIn, ItemStack stackIn)
```

> slotIdIn, the slot lmao
> stackIn, the item stack lmao

## Use

```java
    /**
     * Used in PlayerControllerMP to update the server with an ItemStack in a slot.
     */
    public void sendSlotPacket(ItemStack itemStackIn, int slotId) {
        if (this.currentGameType.isCreative())
            this.netClientHandler.addToSendQueue(new C10PacketCreativeInventoryAction(slotId, itemStackIn));
    }

    /**
     * Sends a CreativeInventoryAction to the server to drop the item on the ground
     */
    public void sendPacketDropItem(ItemStack itemStackIn) {
        if (this.currentGameType.isCreative() && itemStackIn != null)
            this.netClientHandler.addToSendQueue(new C10PacketCreativeInventoryAction(-1, itemStackIn));
    }
```


