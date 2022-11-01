# C0APacketAnimation

This packet is used for swinging.

## Called

### Swinging
This packet is called whenever the player presses the attack button.

### Block
This packet is sent when the player places a block.

## Example
```java
mc.getNetHandler().addToSendQueue(new C0APacketAnimation());
```
