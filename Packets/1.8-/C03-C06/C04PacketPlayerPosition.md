C04PacketPlayerPosition is a type of C03PacketPlayer that updates the players position. 
This is sent when the players position has changed from last tick, but the players rotation has not.
Because this packet is a type of C03PacketPlayer, it updates the clients groundstate.

An example of using this packet might be:

```
//onAttackEvent
mc.thePlayer.sendQueue.addToSendQueue(new C04PacketPlayerPosition(mc.thePlayer.posX, mc.thePlayer.posY-0.1, mc.thePlayer.posZ, false));
```