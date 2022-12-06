# C03PacketPlayer

Every Client tick, the vanilla client will update its position to the server. Every update will update the clients ground state. C04-C06 all inherit C03 and update ground state along with a few other things.

Player position updates are often used as a sort of timer. Things like eating, oxygen, health regeneration, and more are all based on how often the player sends position updates.

Circling back to how C03 and all that inherit it update the clients ground state, you can exploit this to not take any fall damage.

An example of this would be intercepting all C03's and setting its ground state to true

```java
if(packet instanceof C03PacketPlayer) {
	((C03PacketPlayer) packet).setOnGround(false);	
}
```
Doing this tricks the vanilla server into believing the client is always on ground, as the server does not do its own ground calculations to verify this, atleast not in this fall damage scenario.

You can also exploit a variety of other things by sending more or less position updates then the client would normally. Remember earlier how we learned that things like eating, breathing, regeneration, and more were all based off of these updates? By sending more of these updates you can eat faster or regenerate faster. Or by sending less in water you could stay underwater longer without drowning.

## Related
> [C04PacketPlayerPosition](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C04PacketPlayerPosition.md)

> [C05PacketPlayerLook](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C05PacketPlayerLook.md)

> [C06PacketPlayerPosLook](https://github.com/Spinyfish/MinecraftPackets/blob/main/Packets/1.8-/C03-C06/C06PacketPlayerPosLook.txt)
