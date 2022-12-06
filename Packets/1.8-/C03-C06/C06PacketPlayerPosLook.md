# C06PacketPlayerPosLook
C06PacketPlayerPosLook is a subclass of [C03PacketPlayer](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C03PacketPlayer.md), it updates all three things that [C03PacketPlayer](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C03PacketPlayer.md), [C04PacketPlayerPosition](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C04PacketPlayerPosition.md), and [C05PacketPlayerLook](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C05PacketPlayerLook.md) update. This means this packet tells the server three things, the clients ground state, the clients position, and the clients rotation.

## Params

```java
 public C06PacketPlayerPosLook(final double playerX, final double playerY, final double playerZ, final float playerYaw, final float playerPitch, final boolean playerIsOnGround)
 ```
 
 > playerX, the players position on the X axis
 
 > playerY, the players position on the Y axis
 
 > playerZ, the players position on the Z axis
 
 > playerYaw, the yaw rotation of the player
 
 > playerPitch, the pitch rotation of the player
 
 > playerIsOnGround, the ground state, true meaning onground, false meaning off ground
 
 ## Use
 This packet is sent by the client when both its rotation and position have changed since the last position update.

## Related
> [C03PacketPlayer](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C03PacketPlayer.md)

> [C04PacketPlayerPosition](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C04PacketPlayerPosition.md)

> [C05PacketPlayerLook](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C05PacketPlayerLook.md)
