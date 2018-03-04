##Keys

Vector is a type of Table that is used to define a position, rotation or direction. The Table will contain the keys `x`, `y`, `z` and/or `1`, `2`, `3`. The letter and numeric keys are duplicates of each other.

 Letter Key | Number Key
 --- | ---
 x | 1
 y | 2
 z | 3


As an example, An Object at coordinate X=5, Y=2, Z=-1 would return this table:
``` Lua
{
    x = 5,
    y = 2,
    z = -1,
    1 = 5,
    2 = 2,
    3 = -1,
}
```

---

##Mixed Keys


Only one type of key, number or letter, is required. If both a are present in a Table, the numeric key is ignored and only the **letter key** is used.

``` Lua
--Valid Table for 1 to the right
{x=1, y=0, z=0}
--Valid Table for 1 unit forward
{0, 0, 1}
--This Table would be for 1 unit to the right.
{x=1, y=0, z=0, 0, 0, 1}
```

---

##Value Range

The range of values depend on the type of Vector you are using.

Type | Description | Range
--- | --- | ---
Position | A point in space. | Any number within the bounds of the world.
Rotation | Angle, in degrees. | -180 to 180.
Direction | Vector direction. | -1 to 1.

---

##Type Details

###Position

X is right/left, Y is forward/back, Z is up/down. A positional Vector can be either world or local.

Type | Description
-- | --
World | The center of the instance is `{x=0, y=0, z=0}`. That is generally the tabletop's center.
Local | The center of the Object's model is `{x=0, y=0, z=0}`. The center of an Object is determined by the model's creator.

Generally speaking, Tabletop Simulator's functions use world positional Vectors. [positionToWorld(...)](object#positiontoworld) and [positionToLocal(...)](object#positiontolocal) can be used to convert them.

###Rotation

X is pitch (nodding your head), Y is yaw (shaking you head), Z is roll (tilting your head).

###Direction

X is right/left, Y is forward/back, Z is up/down.
