### C00PacketKeepAlive

The server will frequently send out a S00PacketKeepAlive with a randomly generated key, the vanilla client then responds with the key. 
The client must respond to this within 30 seconds, else the server will disconnect them.

### What happens if the key is incorrect?

As long as atleast one key every 30 seconds is correct, you will not be kicked. However if all the keys are wrong for 30 seconds straight, you will be kicked.
