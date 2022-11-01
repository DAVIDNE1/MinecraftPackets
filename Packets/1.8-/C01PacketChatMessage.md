# C01PacketChatMessage

This packet is used to send chat messages to the server.

## Params
- messageIn - Message you wish to send

## Max Length
The vanilla client automatically strips any length over 100, the vanilla code is shown below.
```java
if (messageIn.length() > 100)
{
    messageIn = messageIn.substring(0, 100);   
}
```

## Called
### SendChatMessage
This is called when the player sends a chat message

## Example
```java
this.sendQueue.addToSendQueue(new C01PacketChatMessage(message));
```
