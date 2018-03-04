##Keys

Color is a type of Table that is used to define a color. The Table will contain the keys `r`, `g`, `b`, `a` and/or `1`, `2`, `3`, `4`. The letter and numeric keys are duplicates of each other, and each represents a color or transparency.

Color | Letter Key | Number Key
--- | --- | ---
red | r | 1
green | g | 2
blue | b | 3
alpha | a | 4

As an example, an Object with a white color tint would return this table:
``` Lua
{
    r = 1,
    g = 1,
    b = 1,
    1 = 1,
    2 = 1,
    3 = 1,
}
```

Notice it does not contain the `a` or `4` keys. This is because currently only scripted buttons and scripted inputs utilize the alpha channel (transparency).

##Mixed Keys

Only one type of key, number or letter, is required. If both a are present in a Table, the numeric key is ignored and only the **letter key** is used.

``` Lua
--Valid Table for red
{r=1, g=0, b=0}
--Valid Table for blue
{0, 0, 1}
--This Table would be red.
{r=1, g=0, b=0, 0, 0, 1}
```

##Value

Values are between 0 and 1 for each key. If you are using RGB color that is in 0-255, you can use simple math to convert to the proper value.
``` Lua
--To display a color that is r=50, b=83, g=199
self.setColorTint({50/255, 83/255, 199/255})
```
