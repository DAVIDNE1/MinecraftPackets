Every tick your player will send a type of C03 Packet.

This has a few variations from C03-C06, but all have one thing in common, which is that they update the clients Ground State.

This means that every tick the player updates its ground state to either true (meaning onground) or false (meaning offground). 

C03PacketPlayer itself only does one thing, it updates ground state. This is sent when the player has not changed rotation or position since the last tick.

An example of using this packet would be:

```
if(mc.thePlayer.fallDistance>2) {

	mc.thePlayer.sendQueue.addToSendQueue(new C03PacketPlayer(true));

}
```
This is a very basic anti fall damage, and is one of C03's many uses.

However C03 actually does alot more then it appears, in 1.8 Minecraft, this packet controls:
> how fast you regenerate
- how fast you lose hunger
> how fast you consume items
- how fast you pull your bow
> the speed of which potions run out
- and your Oxygen (when underwater).

This means that the client could send an extra C03 every tick, and get double the regeneration effect as a vanilla player.
Or you could instantly eat an item by sending a bunch of C03's whilst the player is consuming.
