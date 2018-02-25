The Object class represents any entity within tabletop simulator. Once you have a reference to an object in youre script you can call functions on it directly. Example: `obj.getPosition(...)`. You can get a reference to an object multiple ways;

* Using the `self` property if your object is on an object and referring to the object it is on.
* Using [`getObjectFromGUID(...)`](base#getobjectfromguid) with the object's GUID (found by right clicking it with the pointer).
* Getting it as a return from another function, like with [`spawnObject(...)`](base#spawnobject).

##Member Variable Summary

###Member Variables

These are variables that objects share. They allow for direct access to an Object's property information without a helping function. Some are read-only.

Examples: `isResting = self.resting` or `self.resting = true`

Variable Name | Description
-- | --
angular_drag | A Float of an item's angular drag.
auto_raise | A Bool for if an object should be lifted above other objects to avoid collision when held by a player.
bounciness | A Float of bounciness.
drag | A Float of drag.
dynamic_friction | A Float of dynamic friction.
grid_projection | A Bool for if grid lines can appear on the object if visible grids are turned on.
guid | A String of the GUID, which is a 6 character unique object identifier within Tabletop Simulator.
held_by_color | A String of Color of the Player that is holding the object.
interactable | A Bool for if an object can be interacted with by Players. Other object will still be able to interact with it.
mass | A Float of the mass.
name | A String of the name. Read only, use `setName("")` to change names.
resting | A Bool for if an object is at rest.
script_code | A String of the Lua Script on the object.
script_state | A String of the saved data. See [onSave()](event#onsave).
static_friction | A Float of static friction.
sticky | A Bool for if objects on top of this one are also picked up when this one is.
tag | A String of this object's type. Read only.
tooltip | A Bool for if the tooltip opens when a pointer hovers over the object. Tooltips display name and description.
use_gravity | A Bool for if gravity affects this object.
use_grid | A Bool for is snapping to grid is enabled or not.
use_hands | A Bool for if this object can be held in a hand zone.
use_snap_points | A Bool for if snap points are used or ignored.

These member variables are classes of their own, and have their own member variables for controlling specific elements of the type of object they are for.

Variable Name | Description
-- | --
AssetBundle | An [AssetBundle](assetbundle), which is a type of custom object made in Unity.
Clock | A [Clock](clock), which is the in-game digital clock.
Counter | A [Counter](counter), which is the in-game digital counter.
RPGFigurine | An [RPGFigurine](rpgfigurine), which is an in-game animated figurine.
TextTool | A [TextTool](texttool), which is an in-game text display system.

---


##Function Summary



###Property Functions

###Transform Functions

These functions handle the position/rotation/scale/velocity of items. 

###Material Functions

These functions handle material transformation.

###UI Functions

These functions allow for the creation/editing/removal of functional buttons and text inputs which themselves can trigger code within your scripts.

###Object Functions
















##Function Details



















