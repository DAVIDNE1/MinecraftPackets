### Transaction

In vanilla the server will send the client a S32PacketConfirmTransaction to confirm the server and the synchronized with respect to the inventory/container opened by the player.
Normally this is triggered by the client sending a C0EPacketClickWindow [link for C0EPacketClickWindow]

This packet has particular use in anticheats, many anticheat use this as a method to get accurate ping. In vanilla the way the server gets ping for scoreboard is with S00PacketKeepAlive and the clients response time to it.

---
## Random Fact!
The client will never respond to a transaction before a position update!
