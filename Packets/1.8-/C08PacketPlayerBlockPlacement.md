# C08PacketPlayerBlockPlacement

## Parameters

## When not placing (ex consuming)

the only parameter is the item, ItemStack stackIn,

every other parameter is automatically filled out as `this(field_179726_a, 255, stackIn, 0.0F, 0.0F, 0.0F);`

field_179726_a is a blockpos with the coordinates of (-1, -1, -1)


## When we are attempting to place

### 1. BlockPos positionIn // Where in the world we desire to place
### 2. int placedBlockDirectionIn // This is the enum facing as an index
### 3. ItemStack stackIn // This is the item we attempt to place with, if you have one item in your hand but attempt to place with another, the block will be placed (if you have a real block) but it will be delayed, make sure to always send the spoofed slot with your scaffold
### 4. float facingXIn // This is the face on X where we are placing, this is used in MC to determine the slab rotation
### 5. float facingYIn // This is the face on Y where we are placing, this is used in MC to determine the slab rotation
### 6. float facingZIn // This is the face on Z where we are placing, this is used in MC to determine the slab rotation

