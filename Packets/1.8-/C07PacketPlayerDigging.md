# C07PacketPlayerDigging

## Parameters

### 1. C07PacketPlayerDigging.Action statusIn // The action we perform

### 2. BlockPos posIn // Where we interact, for release this is BlockPos.origin

### 3. EnumFacing facingIn // The facing, for release this is down

---
### Types of actions

        START_DESTROY_BLOCK, // Sent when the client is attempting to destroy the block
        ABORT_DESTROY_BLOCK, // Instantly cancels break progress
        STOP_DESTROY_BLOCK, // Sent when the client believes it has broken the block
        DROP_ALL_ITEMS, // Drops the full item stack
        DROP_ITEM, // Drops one of the items from the stack
        RELEASE_USE_ITEM; // Used to release bow, release sword, etc
        
        
