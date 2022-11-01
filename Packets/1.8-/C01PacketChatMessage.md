### C01PacketChatMessage

The packet the client sends to send a chat packet to the server. The vanilla client automatically strips any length over 100.
`
  public C01PacketChatMessage(String messageIn)
    {
        if (messageIn.length() > 100)
        {
            messageIn = messageIn.substring(0, 100);
        }

        this.message = messageIn;
    }`
