The Object class represents any entity within tabletop simulator. Once you have a reference to an object in youre script you can call functions on it directly. Example: `obj.getPosition(...)`. You can get a reference to an object multiple ways;

* Using the `self` property if your script is on an Object and referring to that Object.
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
These functions handle the physical attributes of an Object: Position, Rotation, Scale, Bounds, Velocity. In other words, moving objects around as well as getting information on how they are moving.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
addForce(Vector, Int force_type) | Adds force to an object in a directional Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addforce)
addTorque(Vector, Int force_type) | Adds torque to an object in a rotational Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addtorque)
getAngularVelocity() | Returns a Vector of the current angular velocity. | 
getBounds() | Returns a Table of Vector information describing the size of an object in Global terms. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getbounds)
getBoundsNormalized() | Returns a Table of Vector information describing the size of an object in Global terms, as if it was rotated to {0,0,0}. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getboundsnormalized)
getPosition() | Returns a Vector of the current world position. | 
getRotation() | Returns a Vector of the current rotation. | 
getScale() | Returns a Vector of the current scale. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getscale)
getTransformForward() | Returns a Vector of the forward direction of this object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gettransformforward)
getTransformRight() | Returns a Vector of the right direction of this object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gettransformright)
getTransformUp() | Returns a Vector of the up direction of this object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gettransformup)
getVelocity() | Returns a Vector of the current velocity. | 
isSmoothMoving() | Indicates if an object is traveling as part of a Smooth move. Smooth moving is performed by setPositionSmooth and setRotationSmooth. | 
positionToLocal(Vector) | Returns a Vector after converting a world Vector to a local Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#positiontolocal)
positionToWorld(Vector) | Returns a Vector after converting a local Vector to a world Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#positiontoworld)
rotate(Vector) | Rotates Object smoothly in the direction of the given Vector. | 
scale(Vector or Float) | Scales Object by a multiple. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#scale)
setAngularVelocity(Vector) | Sets a Vector as the current angular velocity. | 
setPosition(Vector) | Instantly moves an Object to the given Vector. | 
setPositionSmooth<br>(Vector, Bool collide, Bool fast) | Moves the Object smoothly to the given Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setpositionsmooth)
setRotation(Vector) | Instantly rotates an Object to the given Vector. | 
setRotationSmooth<br>(Vector, Bool collide, Bool fast) | Rotates the Object smoothly to the given Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setrotationsmooth)
setScale(Vector) | Sets a Vector as the current scale. | 
setVelocity(Vector) | Sets a Vector as the current velocity. | 
translate(Vector) | Smoothly moves Object by the given Vector offset. | 



###UI Functions
These functions allow for the creation/editing/removal of functional buttons and text inputs which themselves trigger code within your scripts.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
clearButtons() | Removes all scripted buttons. | 
clearInputs() | Removes all scripted inputs. | 
createButton(Table parameters) | Creates a scripted button attached to the Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#createbutton)
createInput(Table parameters) | Creates a scripted input attached to the Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#createinput)
editButton(Table parameters) | Modify an existing button. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#editbutton)
editInput(Table parameters) | Modify an existing input. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#editinput)
getButtons() | Returns a Table of all buttons on this Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getButtons)
getInputs() | Returns a Table of all inputs on this Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getButtons)
removeButton(Int index) | Removes a specific button. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#removebutton)
removeInput(Int index) | Removes a specific button. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#removeinput)



###Get Functions
These functions obtain information from an object.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
getColorTint() | Returns Color tint. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getcolortint)
getCustomObject() | Returns a Table with the Custom Object information of a Custom Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getcustomobject)
getLock() | Returns a Bool of the lock status. True is locked. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getlock)
getObjects() | Returns a Table of objects in the script zone/bag/deck. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getobjects)
getQuantity() | Returns an Int of how many objects are in the stack. Returns -1 if the Object is not a stack. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getquantity)
getRotationValues() | Returns a Table of rotation values. Rotation values are used to give value to different rotations (like dice). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getrotationvalues)
getStateId() | Returns an Int for the current [state](http://berserk-games.com/knowledgebase/creating-states/) ID (index) an object is it. Returns -1 if there are no other states. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getstateid)
getStates() | Returns a Table of information on the [states](http://berserk-games.com/knowledgebase/creating-states/) of an Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getstates)
getValue() | Returns an Int as the value. What the value represents depends on what type of Object it is. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getvalue)



###Set Functions
These functions apply action to an object. They take some property in order to work.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
setColorTint(Color) | Sets the Color tint. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getcolortint)
setCustomObject(Table parameters) | Sets a custom object's properties. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setcustomobject)
setLock(Bool lock) | Sets if an object is locked in place. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setcustomobject)
setRotationValues(Table rotation_values) | Sets rotation values of an object. Rotation values are used to give value to different rotations (like dice). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setrotationvalues)
setState(int state) | Sets the [state](http://berserk-games.com/knowledgebase/creating-states/) of an Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setstate)
setValue(variable value) | Sets an Int as the value. What the value represents depends on what type of Object it is. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setvalue)



###Action Function
These functions perform general actions on objects and do not require any input parameters.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
call(String func_name, Table func_params) | Used to call a Lua function on this Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#call)
flip() | Flip Object over. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#flip)
clone(Table parameters) | Copy/Paste this Object, returns a reference to the new Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#clone)
cut() | Cuts (splits in half) a deck or stack Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#cut)
deal(Int number, String player_color, Int index) | Deals Objects. Will deal from decks/bags/stacks/individual items. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#deal)
dealToColorWithOffset(Vector, Bool flip, String player_color) | Deals from a deck to a position relative to the hand zone. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#dealtocolorwithoffset)
destruct() | Destroys Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#destruct)
highlightOn(Color, Float duration) | Creates a highlight around an Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#highlighton)
highlightOff(Color, Float duration) | Removes a highlight from around an Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#highlightoff)
putObject(Object put_object) | Places an object into a container (chip stacks/bags/decks). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#putobject)
randomize() | Shuffles deck/bag, rolls dice/coin, lifts other objects into the air. Same as pressing `R` by default. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#randomize)
reload() | Returns Object reference of itself after it respawns itself. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#reload)
roll() | Rolls dice/coins. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#roll)
shuffle()
shuffleStates() | Returns an Object reference to a new [state](http://berserk-games.com/knowledgebase/creating-states/) after randomly selecting and changing to one. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#shufflestates)
takeObject(Table parameters) | Takes an object from a container (bag/deck/chip stack) and places it in the world. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#takeobject)

---








##Function Details

###Transform Function Details

####addForce(...)

Adds force to an object in a directional Vector.

!!!info "addForce(Vector, Int force_type)"
	* **Vector**: A Vector of the direction and magnitude of force.
    * **Force Type**: An Int representing the force type to apply. Options below.
		* {>>Optional, defaults to 3.<<}
        * **1**: Continuous force, uses mass. *(Force)*
        * **2**: Continuous acceleration, ignores mass. *(Acceleration)*
		* **3**: Instant force impulse, uses mass. *(Impulse)*
		* **4**: Instant velocity change, ignores mass. *(Velocity Change)*

---


####addTorque(...)

Adds torque to an object in a rotational Vector.

!!!info "addTorque(Vector, Int force_type)"
	* **Vector**: A Vector of the direction and magnitude of rotational force.
	* **Force Type**: An Int representing the force type to apply. Options below.
		* {>>Optional, defaults to 3.<<}
        * **1**: Continuous force, uses mass. *(Force)*
        * **2**: Continuous acceleration, ignores mass. *(Acceleration)*
		* **3**: Instant force impulse, uses mass. *(Impulse)*
		* **4**: Instant velocity change, ignores mass. *(Velocity Change)*

---



####getBounds()

Returns a Table of Vector information describing the size of an object in Global terms. [Bounds](https://docs.unity3d.com/ScriptReference/Bounds.html) are part of Unity, and represent an imaginary square box that can be drawn around an object. Unlike scale, it can help indicate the size of an object in in-game units, not just relative model size.

!!!info "Return Table"
	* **center**: The center of the bounding box.
	* **size**: The size of the bounding box.
	* **offset**: The offset of the center of the bounding box from the middle of the Object model.

``` Lua
--Example returned Table
{
	center = {x=0, y=3, z=0, 0, 3, 0},
	size = {x=5, y=5, z=5}, 5, 5, 5},
	offset = {x=0, y=-1, z=0, 0, -1, 0}
}
```

---


####getBoundsNormalized()

Returns a Table of Vector information describing the size of an object in Global terms, as if it was rotated to {0,0,0}. [Bounds](https://docs.unity3d.com/ScriptReference/Bounds.html) are part of Unity, and represent an imaginary square box that can be drawn around an object. Unlike scale, it can help indicate the size of an object in in-game units, not just relative model size.

!!!info "Return Table"
	* **center**: The center of the bounding box.
	* **size**: The size of the bounding box.
	* **offset**: The offset of the center of the bounding box from the middle of the Object model.

``` Lua
--Example returned Table
{
	center = {x=0, y=3, z=0, 0, 3, 0},
	size = {x=5, y=5, z=5}, 5, 5, 5},
	offset = {x=0, y=-1, z=0, 0, -1, 0}
}
```

---


####getScale()

Returns a Vector of the current scale. Scale is not an absolute measurement, it is a multiple of the Object's default model size. So {x=2, y=2, z=2} would be a model twice its default size, not 2 units large.

---


####getTransformForward()

Returns a Vector of the forward direction of this Object. The direction is relative to how the object is facing.

``` Lua
--Example of moving forward 5 units
function onLoad()
    distance = 5
    pos_target = self.getTransformForward()
    pos_current = self.getPosition()
    pos = {
        x = pos_current.x + pos_target.x * distance,
        y = pos_current.y + pos_target.y * distance,
        z = pos_current.z + pos_target.z * distance,
    }
    self.setPositionSmooth(pos)
end
```

---


####getTransformRight()

Returns a Vector of the forward direction of this object. The direction is relative to how the object is facing.

``` Lua
--Example of moving right 5 units
function onLoad()
    distance = 5
    pos_target = self.getTransformRight()
    pos_current = self.getPosition()
    pos = {
        x = pos_current.x + pos_target.x * distance,
        y = pos_current.y + pos_target.y * distance,
        z = pos_current.z + pos_target.z * distance,
    }
    self.setPositionSmooth(pos)
end
```

---


####getTransformUp()

Returns a Vector of the up direction of this Object. The direction is relative to how the object is facing.

``` Lua
--Example of moving up 5 units
function onLoad()
    distance = 5
    pos_target = self.getTransformUp()
    pos_current = self.getPosition()
    pos = {
        x = pos_current.x + pos_target.x * distance,
        y = pos_current.y + pos_target.y * distance,
        z = pos_current.z + pos_target.z * distance,
    }
    self.setPositionSmooth(pos)
end
```

---


####positionToLocal(...)

Returns a Vector after converting a world vector to a local Vector. A world Vector is a positional Vector using the world's coordinate system. A Local Vector is a positional Vector that is relative to the position of the given object.

---


####positionToWorld(...)

Returns a Vector after converting a local Vector to a world Vector. A world Vector is a positional Vector using the world's coordinate system. A Local Vector is a positional Vector that is relative to the position of the given object.

---


####rotate(Vector)

Rotates Object smoothly in the direction of the given Vector. This does not set the Object to face a specific rotation, it rotates the Object around by the number of degrees given for x/y/z.

``` Lua
--Rotates object 90 degrees around its Y axis
self.rotate({x=0, y=90, z=0})
```

---


####scale(...)

Scales Object by a multiple. This does not set the Object to a specific scale, it scales the Object by the given multiple.

!!!info "scale(Vector or Float)"
	This function accepts either a Vector or Float as a parameter. If you use a Float, it will multiple the Object's x/y/z by that number.

``` Lua
--Both examples work to scale an object to be twice its current scale
self.scale({x=2, y=2, z=2})
self.scale(2)
```

---


####setPositionSmooth(...)

Moves the Object smoothly to the given Vector.

!!!info "setPositionSmooth(Vector, Bool collide, Bool fast)"
	* **Vector**: A positional Vector.
	* **Bool collide**: A Bool for if the Object will collide with other Objects while moving.
	* **Bool fast**: A Bool for if the Object is moved quickly.
	
---


####setRotationSmooth(...)

Rotates the Object smoothly to the given Vector.

!!!info "setRotationSmooth(Vector, Bool collide, Bool fast)"
	* **Vector**: A rotational Vector.
	* **Bool collide**: A Bool for if the Object will collide with other Objects while rotating.
	* **Bool fast**: A Bool for if the Object is rotated quickly.

---


###UI Function Details

####createButton(...)

Creates a scripted button attached to the Object. Scripted buttons are buttons that can be clicked while in-game that trigger a function in a script.

!!!info "createButton(Table parameters)"
	* **Table parameters**: A Table containing the information used to spawn the button.
		* **parameters.click_function**: A String of the function's name that will be run when button is clicked.
		* **parameters.function_owner**: The Object which contains the click_function function.
			* {>>Defaults to Global.<<}
		* **parameters.label**: A String of text that appears on the button.
			* {>>Optional, defaults to an empty string.<<}
		* **parameters.position**: A Vector of where the button appears, relative to the Object's center.
			* {>>Optional, defaults to {x=0, y=0, z=0}.<<}
		* **parameters.rotation**: A Vector of how the button is rotated, relative to the Object's rotation.
			* {>>Optional, defaults to {x=0, y=0, z=0}.<<}
		* **parameters.scale**: A Vector of the scale of the button, relative to the Object's scale.
			* {>>Optional, defaults to {x=1, y=1, z=1}.<<}
		* **parameters.width**: An Int of how wide the button will be, relative to the Object.
			* {>>Optional, defaults to 500.<<}
		* **parameters.height**: An Int of how tall the button will be, relative to the Object.
			* {>>Optional, defaults to 500.<<}
		* **parameters.font_size**: An Int of the size the label font will be, relative to the Object.
			* {>>Optional, defaults to 500.<<}
		* **parameters.color**: A Color for the clickable button.
			* {>>Optional, defaults to {r=1, g=1, b=1}.<<}
		* **parameters.font_color**: A Color for the the label text.
			* {>>Optional, defaults to {r=0, g=0, b=0}.<<}
		* **parameters.tooltip**: A String for a popup of text, similar to how an object's name is displayed on mouseover.
			* {>>Optional, defaults to an empty string.<<}

``` Lua
params = {
	click_function = "click_func",
	function_owner = self,
	label = "Test",
	position = {0, 1, 0},
	rotation = {0, 180, 0},
	width= 800,
	height=400,
	font_size = 340,
	color = {0.5, 0.5, 0.5},
	font_color = {1, 1, 1},
	tooltip = "This text appears on mouseover.",
}
self.createButton(params)
```

!!!tip "Button Tips"
	* Buttons can not be clicked from their back side.
	* Buttons can not be clicked if there is another object between the pointer and the button. This does not include the Object the button is attached to.
	* Buttons are placed relative to the Object they are attached to.
	* The maximum font size is capped at 1000.
	* The minimum width/height is ~100 before you won't see it getting any smaller.
	* A button width/height of 0 will cause the button not to be drawn, but its label will be. This can be a way to attach text to an Object.

!!!bug
	Button scale currently distorts button height and width if the button is rotated at anything besided `{0,0,0}`.








	
