# C09PacketHeldItemChange

This packet is sent to tell the server the new slot of the item the player is holding.

```java
// Syncs the players current item
int i = this.mc.thePlayer.inventory.currentItem;

        if (i != this.currentPlayerItem)
        {
            this.currentPlayerItem = i;
            this.netClientHandler.addToSendQueue(new C09PacketHeldItemChange(this.currentPlayerItem));
        }
```

## Params
```java
public C09PacketHeldItemChange(int slotId)
```

> slotId, the slot you are changing too

## Use

```java
// PlayerControllerMP.java
/**
     * Syncs the current player item with the server
     */
    private void syncCurrentPlayItem()
    {
        int i = this.mc.thePlayer.inventory.currentItem;

        if (i != this.currentPlayerItem)
        {
            this.currentPlayerItem = i;
            this.netClientHandler.addToSendQueue(new C09PacketHeldItemChange(this.currentPlayerItem));
        }
    }
```
This is called before every controller action and update
