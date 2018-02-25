The Object class represents any entity within tabletop simulator. Once you have a reference to an object in youre script you can call functions on it directly. Example: `obj.getPosition(...)`. You can get a reference to an object multiple ways;

* Using the `self` property if your object is on an object and referring to the object it is on.
* Using [`getObjectFromGUID(...)`](base#getobjectfromguid) with the object's GUID (found by right clicking it with the pointer).
* Getting it as a return from another function, like with [`spawnObject(...)`](base#spawnobject).

##Member Variable Summary

###Member Variables
These are variables that objects share. They allow for direct access to an Object's property information without a helping function. Some are read-only.

Read Example = `isResting = self.resting` Write Example = `self.resting = true`

Variable | Description | Type
-- | -- | --:
angular_drag | Angular drag. [Unity rigidbody property](https://docs.unity3d.com/Manual/class-Rigidbody.html). | Float
auto_raise | If an object should be lifted above other objects to avoid collision when held by a player. | Bool
bounciness | Bounciness, value of 0-1. [Unity physics material](https://docs.unity3d.com/Manual/class-PhysicMaterial.html). | Float
drag | Drag. [Unity rigidbody property](https://docs.unity3d.com/Manual/class-Rigidbody.html). | Float
dynamic_friction | Dynamic friction, value of 0-1. [Unity physics material](https://docs.unity3d.com/Manual/class-PhysicMaterial.html). | Float
grid_projection | If grid lines can appear on the Object if visible grids are turned on. | Bool
guid | The 6 character unique Object identifier within Tabletop Simulator. | String
held_by_color | The Color of the Player that is holding the object. | String
interactable | If an object can be interacted with by Players. Other object will still be able to interact with it. | Bool
mass | Mass. [Unity rigidbody property](https://docs.unity3d.com/Manual/class-Rigidbody.html). | Float
name | The Object's name. Read only, use `setName("")` to write to it. | String
resting | If an Object is at rest. [Unity rigidbody property](https://docs.unity3d.com/412/Documentation/Components/RigidbodySleeping.html). | Bool
script_code | The Lua Script on the Object. | String
script_state | The saved data on the object. See [onSave()](event#onsave). | String
static_friction | Static friction, value of 0-1. [Unity physics material](https://docs.unity3d.com/Manual/class-PhysicMaterial.html). | Float
sticky | If other Objects on top of this one are also picked up when this Object is. | Bool
tag | This object's type. Read only. | String
tooltip | If the tooltip opens when a pointer hovers over the object. Tooltips display name and description. | Bool
use_gravity | If gravity affects this object. | Bool
use_grid | If snapping to grid is enabled or not. | Bool
use_hands | If this object can be held in a hand zone. | Bool
use_snap_points | If snap points are used or ignored. | Bool

These member variables are classes of their own, and have their own member variables. Each one is for a special type of Object.

Variable Name | Description
-- | --
AssetBundle | An [AssetBundle](assetbundle), which is a type of custom object made in Unity.
Clock | A [Clock](clock), which is the in-game digital clock.
Counter | A [Counter](counter), which is the in-game digital counter.
RPGFigurine | An [RPGFigurine](rpgfigurine), which is an in-game animated figurine.
TextTool | A [TextTool](texttool), which is an in-game text display system.

---


##Function Summary

###Transform Functions
These functions handle the physical attributes of an Object: Position, Rotation, Scale, Velocity. In other words, moving objects around as well as getting information on how they are moving.




Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
addForce(Vector, Int force_type) | Adds force to an object in a directional Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addforce)
addTorque(Vector, Int force_type) | Adds torque to an object in a rotational Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addtorque)
getAngularVelocity() | Returns a Vector of the current angular velocity. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getangularvelocity)



###UI Functions
These functions allow for the creation/editing/removal of functional buttons and text inputs which themselves trigger code within your scripts.


###Get Functions
These functions obtain information from an object.


###Set Functions
These functions apply action to an object. They take some property in order to work.


###Action Function
These functions perform general actions on objects and do not require any input parameters.

flip()













##Function Details



















