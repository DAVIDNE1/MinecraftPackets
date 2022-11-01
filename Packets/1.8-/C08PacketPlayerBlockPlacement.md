# C08PacketPlayerBlockPlacement

## Params

### When not placing (ex consuming)

ItemStack stackIn - The item you are interacting with

every other parameter is automatically filled out as 
```java
this(field_179726_a, 255, stackIn, 0.0F, 0.0F, 0.0F);`
```

field_179726_a is a blockpos with the coordinates of (-1, -1, -1)


## When we are placing a block

- BlockPos positionIn - Where in the world we desire to place

- int placedBlockDirectionIn - This is the enum facing as an index

- ItemStack stackIn - This is the item we attempt to place with, if you have one item in your hand but attempt to place with another, the block will be placed (if you have a real block) but it will be delayed, make sure to always send the spoofed slot with your scaffold

- float facingXIn - This is the face on X where we are placing, this is used in MC to determine the slab rotation

- float facingYIn - This is the face on Y where we are placing, this is used in MC to determine the slab rotation

- float facingZIn - This is the face on Z where we are placing, this is used in MC to determine the slab rotation


## Called

## Minecraft.getMinecraft().playerController.sendUseItem
In vanilla, this is when the player interacts with their item (like consuming or blocking)

### Params of sendUseItem

- EntityPlayer playerIn - The entity using the item (ie thePlayer)
- World worldIn - The world
- ItemStack itemStackIn - The item the player is using

> It should be noted that this also calls the function
> syncCurrentPlayItem()
> This ensures that the item the client believes they are holding is the same serverside

### onPlayerRightClick

In vanilla this is used when placing, this will return false if the place fails, and the client will not swing

## Example

### Blocking

```java
mc.getNetHandler().addToSendQueue(new C08PacketPlayerBlockPlacement(Minecraft.getMinecraft.getHeldItem());
```

### Placing

```java
mc.getNetHandler().addToSendQueue(new C08PacketPlayerBlockPlacement(blockPos, enumFacing.getIndex(), player.inventory.getCurrentItem(), facingX, facingY, facingZ));
```




