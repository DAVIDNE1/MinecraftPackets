# C02PacketUseEntity
This packet is used for interacting with other entities.

## Params
- Entity entity - T entity thats being interacted with in some form
- C02PacketUseEntity.Action action - This is the action we are performing
OR
- Entity entity - T entity thats being interacted with in some form
- Vec3 hitVec - The vector of where you were facing when you hit

## Example
### Attacking
```java
mc.thePlayer.sendQueue.addToSendQueueSilent(new C02PacketUseEntity(entity, C02PacketUseEntity.Action.ATTACK));
```
### Interacting
```java
mc.thePlayer.sendQueue.addToSendQueueSilent(new C02PacketUseEntity(target, C02PacketUseEntity.Action.INTERACT));
```
---
### Action Types
```
INTERACT,
ATTACK,
INTERACT_AT;
```
