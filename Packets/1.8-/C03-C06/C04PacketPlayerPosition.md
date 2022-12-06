# C04PacketPlayerPosition
C04PacketPlayerPosition is a subclass of [C03PacketPlayer](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C03PacketPlayer.md), it updates the clients position and like all position updates, the clients ground state.

## Params

```java
public C04PacketPlayerPosition(double posX, double posY, double posZ, boolean isOnGround)
 ```
 
 > playerX, the players position on the X axis
 
 > playerY, the players position on the Y axis
 
 > playerZ, the players position on the Z axis
 
 > playerIsOnGround, the ground state, true meaning onground, false meaning off ground
 
 ## Use
 This packet is sent by the client when the players position, but not rotation, has changed since the last position update.

## Related
> [C03PacketPlayer](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C03PacketPlayer.md)

> [C05PacketPlayerLook](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C05PacketPlayerLook.md)

> [C06PacketPlayerPosLook](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C06PacketPlayerPosLook.txt)
