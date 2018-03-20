Physics, a static global class, allows access to casts and gravity. Physics casts are a way to detect Objects. You call these functions like this: `Physics.getGravity()`.

For more information on physics casts in Unity, [refer to the Unity documentation](https://docs.unity3d.com/ScriptReference/Physics.html) under BoxCast/RayCast/SphereCast.

##Function Summary

###Functions

Function Name | Description | Return | &nbsp;
-- | -- | -- | --
cast([<span class="tag tab"></span>](typeandclass)&nbsp; parameters) | Returns Table containing information on hit Objects. | [<span class="ret tab"></span>](typeandclass) | [<span class="i"></span>](#cast)
getGravity() | Returns directional Vector of the direction gravity is pulling. | [<span class="ret tab"></span>](typeandclass) | 
setGravity([<span class="tag tab"></span>](typeandclass)&nbsp; Vector) | Sets the direction gravity gravity pulls. | [<span class="ret boo"></span>](typeandclass) 






---


##Function Details

###cast(...)

[<span class="ret tab"></span>](typeandclass)&nbsp; Returns Table containing information on hit Objects. There are three kinds of casts:

Type | Description
--- | ---
Ray | A line.
Box | A cube, rectangle, plane.
Sphere | A round ball. You cannot make ovals.

It draws the imaginary cast, then moves the rap/box/sphere along that path instantly. The debug Bool in the parameters allows you to see this shape, to aid in setup, but the visual is not instant (due to that making it pointless, if you can't see it).

!!!Warning
    Physics casts are somewhat expensive. When running 30+ at once it will cause your game to stutter and/or crash. Do not overuse.
    
!!!info "cast(Table parameters)"
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters**: A Table of parameters used to guide the function.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.origin**: A Vector of the starting point.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.direction**: A directional Vector for the cast to move in.
            * {>>Optional, but cast is motionless without a direction.<<}
        * [<span class="tag int"></span>](typeandclass)&nbsp; **parameters.type**: The type of cast. 1 = Ray, 2 = Sphere, 3= Box.
            * {>>Optional, defaults to 1.<<}
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.size**: A Vector of the size of the cast. Sphere/Box only.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.orientation**: A rotational Vector of the cast. Box only.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * [<span class="tag flo"></span>](typeandclass)&nbsp; **parameters.max_distance**: How fast the cast will travel.
            * {>>Optional, defaults to infinity. Won't move without direction.<<}
        * [<span class="tag boo"></span>](typeandclass)&nbsp; **parameters.debug**: If the cast is visualized for the user.
            * {>>Optional, defaults to false.<<}
    
!!!info "Returned Table of Hit Objects"
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **table**: A numerically indexed Table, one entry for each hit Object. Entries are in the order of being hit.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **table.point**: A Vector of the position the cast impact.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **table.normal**: A Vector of the surface normal of the impact point.
        * [<span class="tag flo"></span>](typeandclass)&nbsp; **table.distance**: A Float of the distance between cast origin and impact point.
        * [<span class="tag obj"></span>](typeandclass)&nbsp; **table.hit_object**: An Object reference to the object hit by the cast.

``` Lua
--Example usage
--This function, when called, returns a table of hit data
function findHitsInRadius(pos, radius)
    local radius = (radius or 1)
    local hitList = Physics.cast({
        origin       = pos,
        direction    = {0,1,0},
        type         = 2,
        size         = {radius,radius,radius},
        max_distance = 0,
        debug        = true,
    })

    return hitList
end
```

``` Lua
--Example returned Table
{
    {
        point = {x=0,y=0,z=0},
        normal = {x=1,0,0},
        distance = 4,
        hit_object = objectreference1,
    },
    {
        point = {x=1,y=0,z=0},
        normal = {x=2,0,0},
        distance = 5,
        hit_object = objectreference2,
    },
}
```
