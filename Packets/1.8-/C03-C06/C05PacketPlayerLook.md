# C05PacketPlayerLook
C05PacketPlayerLook is a subclass of [C03PacketPlayer](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C03PacketPlayer.md), it updates the clients rotation and of course ground state.

## Params

```java
public C05PacketPlayerLook(float playerYaw, float playerPitch, boolean isOnGround)
 ```
 
 > playerYaw, the yaw rotation of the player
 
 > playerPitch, the pitch rotation of the player
 
 > playerIsOnGround, the ground state, true meaning onground, false meaning off ground
 
 ## Use
 This packet is sent by the client when the players rotation, but not position has changed since the last position update.
