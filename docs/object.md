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
addForce(Vector, Int force_type) | Adds force to an object in a directional Vector. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addforce)
addTorque(Vector, Int force_type) | Adds torque to an object in a rotational Vector. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addtorque)
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
isSmoothMoving() | Indicates if an object is traveling as part of a Smooth move. Smooth moving is performed by setPositionSmooth and setRotationSmooth. Returns Bool. | 
positionToLocal(Vector) | Returns a Vector after converting a world Vector to a local Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#positiontolocal)
positionToWorld(Vector) | Returns a Vector after converting a local Vector to a world Vector. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#positiontoworld)
rotate(Vector) | Rotates Object smoothly in the direction of the given Vector. Returns Bool. | 
scale(Vector or Float) | Scales Object by a multiple. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#scale)
setAngularVelocity(Vector) | Sets a Vector as the current angular velocity. Returns Bool. | 
setPosition(Vector) | Instantly moves an Object to the given Vector. Returns Bool. | 
setPositionSmooth<br>(Vector, Bool collide, Bool fast) | Moves the Object smoothly to the given Vector. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setpositionsmooth)
setRotation(Vector) | Instantly rotates an Object to the given Vector. | 
setRotationSmooth<br>(Vector, Bool collide, Bool fast) | Rotates the Object smoothly to the given Vector. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setrotationsmooth)
setScale(Vector) | Sets a Vector as the current scale. Returns Bool. | 
setVelocity(Vector) | Sets a Vector as the current velocity. Returns Bool. | 
translate(Vector) | Smoothly moves Object by the given Vector offset. Returns Bool. | 



###UI Functions
These functions allow for the creation/editing/removal of functional buttons and text inputs which themselves trigger code within your scripts.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
clearButtons() | Removes all scripted buttons. Returns Bool. | 
clearInputs() | Removes all scripted inputs. Returns Bool. | 
createButton(Table parameters) | Creates a scripted button attached to the Object. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#createbutton)
createInput(Table parameters) | Creates a scripted input attached to the Object. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#createinput)
editButton(Table parameters) | Modify an existing button. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#editbutton)
editInput(Table parameters) | Modify an existing input. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#editinput)
getButtons() | Returns a Table of all buttons on this Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getbuttons)
getInputs() | Returns a Table of all inputs on this Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getinputs)
removeButton(Int index) | Removes a specific button. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#removebutton)
removeInput(Int index) | Removes a specific button. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#removeinput)



###Get Functions
These functions obtain information from an object.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
getColorTint() | Returns Color tint. | 
getCustomObject() | Returns a Table with the Custom Object information of a Custom Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getcustomobject)
getLock() | Returns a Bool of the lock status. True is locked. | 
getObjects() | Returns a Table of objects in the script zone/bag/deck. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getobjects)
getQuantity() | Returns an Int of how many objects are in the stack. Returns -1 if the Object is not a stack. | 
getRotationValues() | Returns a Table of rotation values. Rotation values are used to give value to different rotations (like dice). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getrotationvalues)
getStateId() | Returns an Int for the current [state](http://berserk-games.com/knowledgebase/creating-states/) ID (index) an object is it. Returns -1 if there are no other states. State ids (indexes) start at 1. | 
getStates() | Returns a Table of information on the [states](http://berserk-games.com/knowledgebase/creating-states/) of an Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getstates)
getValue() | Returns an Int as the value. What the value represents depends on what type of Object this function is used on. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getvalue)



###Set Functions
These functions apply action to an object. They take some property in order to work.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
setColorTint(Color) | Sets the Color tint. Returns Bool. | 
setCustomObject(Table parameters) | Sets a custom Object's properties. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setcustomobject)
setLock(Bool lock) | Sets if an object is locked in place. Returns Bool. | 
setRotationValues(Table rotation_values) | Sets rotation values of an object. Rotation values are used to give value to different rotations (like dice). Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setrotationvalues)
setState(Int state_id) | Returns Object of set [state](http://berserk-games.com/knowledgebase/creating-states/) of an Object. State ids (indexes) start at 1. | 
setValue(Var value) | Sets an Int as the value. What the value represents depends on what type of Object it is. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setvalue)



###Action Function
These functions perform general actions on objects and do not require any input parameters.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
call(String func_name,<br>Table func_params) | Used to call a Lua function on this Object. Returns Var. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#call)
flip() | Flip Object over. Returns Bool. | 
clone(Table parameters) | Copy/Paste this Object, returns a reference to the new Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#clone)
cut() | Cuts (splits in half) a deck or stack Object. | 
deal(Int number,<br>String player_color, Int index) | Deals Objects. Will deal from decks/bags/stacks/individual items. Returns Object dealt. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#deal)
dealToColorWithOffset<br>(Vector, Bool flip, String player_color) | Deals from a deck to a position relative to the hand zone. Returns Object dealt. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#dealtocolorwithoffset)
destruct() | Destroys Object. Allows for `self.destruct()`. Returns Bool. | 
highlightOn(Color, Float duration) | Creates a highlight around an Object. Returns Bool. | 
highlightOff(Color) | Removes a highlight from around an Object. Returns Bool. |
putObject(Object put_object) | Places an object into a container (chip stacks/bags/decks). Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#putobject)
randomize() | Shuffles deck/bag, rolls dice/coin, lifts other objects into the air. Same as pressing `R` by default. Returns Bool. | 
reload() | Returns Object reference of itself after it respawns itself. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#reload)
roll() | Rolls dice/coins. Returns Bool. | 
shuffle() | Shuffles/shakes up contents of a deck or bag. Returns Bool. |
shuffleStates() | Returns an Object reference to a new [state](http://berserk-games.com/knowledgebase/creating-states/) after randomly selecting and changing to one. | 
takeObject(Table parameters) | Returns an Object reference of Object taken from a container (bag/deck/chip stack) and placed into the world. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#takeobject)

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

???tip "Button Tips"
	* Buttons can not be clicked from their back side.
	* Buttons can not be clicked if there is another object between the pointer and the button. This does not include the Object the button is attached to.
	* Buttons are placed relative to the Object they are attached to.
	* The maximum font size is capped at 1000.
	* The minimum width/height is 60. Any lower number (besides 0) will appear to be 60. This prevents visual glitches involving the corner rounding.
	* A button width/height of 0 will cause the button not to be drawn, but its label will be. This can be a way to attach text to an Object.
	* You cannot assign an index to a button. It is given one automatically.

!!!info "createButton(Table parameters)"
	* **Table parameters**: A Table containing the information used to spawn the button.
		* **parameters.click_function**: A String of the function's name that will be run when button is clicked.
		* **parameters.function_owner**: The Object which contains the click_function function.
			* {>>Optional, Defaults to Global.<<}
		* **parameters.label**: A String of text that appears on the button.
			* {>>Optional, defaults to an empty string.<<}
		* **parameters.position**: A Vector of where the button appears, relative to the Object's center.
			* {>>Optional, defaults to {x=0, y=0, z=0}.<<}
		* **parameters.rotation**: A Vector of how the button is rotated, relative to the Object's rotation.
			* {>>Optional, defaults to {x=0, y=0, z=0}.<<}
		* **parameters.scale**: A Vector of the scale of the button, relative to the Object's scale.
			* {>>Optional, defaults to {x=1, y=1, z=1}.<<}
		* **parameters.width**: An Int of how wide the button will be, relative to the Object.
			* {>>Optional, defaults to 100.<<}
		* **parameters.height**: An Int of how tall the button will be, relative to the Object.
			* {>>Optional, defaults to 100.<<}
		* **parameters.font_size**: An Int of the size the label font will be, relative to the Object.
			* {>>Optional, defaults to 100.<<}
		* **parameters.color**: A Color for the clickable button.
			* {>>Optional, defaults to {r=1, g=1, b=1}.<<}
		* **parameters.font_color**: A Color for the label text.
			* {>>Optional, defaults to {r=0, g=0, b=0}.<<}
		* **parameters.tooltip**: A String for a popup of text, similar to how an Object's name is displayed on mouseover.
			* {>>Optional, defaults to an empty string.<<}
			
!!!info "click_function(Object obj, String player_clicker_color)"
	The click function which is activated by clicking this button has its own parameters it is passed automatically.
	
	* **Object obj**: The Object the button is attached to.
	* **String player_clicker_color**: A String of the Color of the player that pressed the button.

``` Lua
function onLoad()
	params = {
		click_function = "click_func",
		function_owner = self,
		label          = "Test",
		position       = {0, 1, 0},
		rotation       = {0, 180, 0},
		width          = 800,
		height         = 400,
		font_size      = 340,
		color          = {0.5, 0.5, 0.5},
		font_color     = {1, 1, 1},
		tooltip        = "This text appears on mouseover.",
	}
	self.createButton(params)
end

function click_func(obj, color)
	print(obj)
	print(color)
end
```

!!!bug
	Button scale currently distorts button height and width if the button is rotated at anything besides `{0,0,0}`.

---


####createInput(...)

Creates a scripted input attached to the Object. Scripted inputs are boxes you can click inside of in-game to input/edit text. Every letter typed triggers the function. The bool that is returned as part of the input_function allows you to determine when a player has finished editing the input.

???tip "Input Tips"
	* Inputs can not be clicked from their back side.
	* Inputs can not be clicked if there is another object between the pointer and the inputs. This does not include the Object the input is attached to.
	* Inputs are placed relative to the Object they are attached to.
	* The maximum font size is capped at 1000.
	* The minimum width/height is 60. Any lower number (besides 0) will appear to be 60. This prevents visual glitches involving the corner rounding.
	* Font that does not fit in the input window's width/height does NOT display. To know how much height you need for each line, the formula is `(font_size * # of lines) + 23`. In other words, multiply how many lines of text you want to display by your font_size and add 23. That is your height value.
	* You cannot assign an index to an input. It is given one automatically.

!!!info "createInput(Table parameters)"
	* **Table parameters**: A Table containing the information used to spawn the input.
		* **parameters.input_function**: A String of the function's name that will be run when a key is used or when it is deselected.
		* **parameters.function_owner**: The Object which contains the input_function function.
			* {>>Optional, Defaults to Global.<<}
		* **parameters.label**: A String of text that appears as greyed out text when there is no value in the input.
			* {>>Optional, defaults to an empty string.<<}
		* **parameters.position**: A Vector of where the input appears, relative to the Object's center.
			* {>>Optional, defaults to {x=0, y=0, z=0}.<<}
		* **parameters.rotation**: A Vector of how the input is rotated, relative to the Object's rotation.
			* {>>Optional, defaults to {x=0, y=0, z=0}.<<}
		* **parameters.scale**: A Vector of the scale of the input, relative to the Object's scale.
			* {>>Optional, defaults to {x=1, y=1, z=1}.<<}
		* **parameters.width**: An Int of how wide the input will be, relative to the Object.
			* {>>Optional, defaults to 100.<<}
		* **parameters.height**: An Int of how tall the input will be, relative to the Object.
			* {>>Optional, defaults to 100.<<}
		* **parameters.font_size**: An Int of the size the label/value font will be, relative to the Object.
			* {>>Optional, defaults to 100.<<}
		* **parameters.color**: A Color for the input's background.
			* {>>Optional, defaults to {r=1, g=1, b=1}.<<}
		* **parameters.font_color**: A Color for the value text.
			* {>>Optional, defaults to {r=0, g=0, b=0}.<<}
		* **parameters.tooltip**: A String for a popup of text, similar to how an Object's name is displayed on mouseover.
			* {>>Optional, defaults to an empty string.<<}
		* **parameters.alignment**: An Int for how text is aligned in the input box.
			* {>>Optional, defaults to 1.<<}
			* **1**: Automatic
			* **2**: Left
			* **3**: Center
			* **4**: Right
			* **5**: Justified
		* **parameters.value**: A String of the text entered into the input.
			* {>>Optional, defaults to an empty string.<<}
		* **parameters.validation**: An Int which determines what characters can be input into the value.
			* {>>Optional, defaults to 1.<<}
			* **1**: None
			* **2**: Integer
			* **3**: Float
			* **4**: Alphanumeric
			* **5**: Username
			* **6**: Name
		* **parameters.tab**: An Int which determines how pressing tab is handled when inputting.
			* {>>Optional, defaults to 1.<<}
			* **1**: None
			* **2**: Select Next Input
			* **3**: Indent

!!!info "input_function(Object obj, String player_clicker_color, String input_value, Bool selected)"
	The click function which is activated by clicking this button has its own parameters it is passed automatically.
	
	* **Object obj**: The Object the input is attached to.
	* **String player_clicker_color**: A String of the Color of the player that has selected/edited the input.
	* **String input_value**: A String of the text currently in the input.
	* **Bool selected**: A Bool for if the value box is still being edited or not.
	
``` Lua
function onLoad()
	self.createInput({
	    input_function = "input_func",
	    function_owner = self,
	    label          = "Gold",
	    alignment      = 4,
	    position       = {x=0, y=1, z=0},
	    width          = 800,
	    height         = 300,
	    font_size      = 323,
	    validation     = 2,
	})
end

function input_func(obj, color, input, stillEditing)
	print(input)
	if not stillEditing then
		print("Finished editing.")
	end
end
```	

---


####editButton(...)

Modify an existing button. The only parameter that is required is the index. The rest are optional, and not using them will cause the edited button's element to remain. Indexes start at 0. The first button on any given Object has an index of 0, the next button on it has an index of 1, etc. Each Object has its own indexes.

!!!info "editButton(Table parameters)"
	* **Table parameters**: A Table containing the information used to spawn the button.
		* **parameters.index**: An Int of the index of the button you want to edit.
		* **parameters.click_function**: A String of the function's name that will be run when button is clicked.
		* **parameters.function_owner**: The Object which contains the click_function function.
		* **parameters.label**: A String of text that appears on the button.
		* **parameters.position**: A Vector of where the button appears, relative to the Object's center.
		* **parameters.rotation**: A Vector of how the button is rotated, relative to the Object's rotation.
		* **parameters.scale**: A Vector of the scale of the button, relative to the Object's scale.
		* **parameters.width**: An Int of how wide the button will be, relative to the Object.
		* **parameters.height**: An Int of how tall the button will be, relative to the Object.
		* **parameters.font_size**: An Int of the size the label font will be, relative to the Object.
		* **parameters.color**: A Color for the clickable button.
		* **parameters.font_color**: A Color for the label text.
		* **parameters.tooltip**: A String for a popup of text, similar to how an Object's name is displayed on mouseover.

``` Lua
self.editButton({index=0, label="New Label"})
```

---


####editInput(...)

Modify an existing input. The only parameter that is required is the index. The rest are optional, and not using them will cause the edited input's element to remain. Indexes start at 0. The first input on any given Object has an index of 0, the next input on it has an index of 1, etc. Each Object has its own indexes.

!!!info "editInput(Table parameters)"
	* **Table parameters**: A Table containing the information used to spawn the input.
		* **parameters.index**: An Int of the index of the input you want to edit.
		* **parameters.input_function**: A String of the function's name that will be run when a key is used or when it is deselected.
		* **parameters.function_owner**: The Object which contains the input_function function.
		* **parameters.label**: A String of text that appears as greyed out text when there is no value in the input.
		* **parameters.position**: A Vector of where the input appears, relative to the Object's center.
		* **parameters.rotation**: A Vector of how the input is rotated, relative to the Object's rotation.
		* **parameters.scale**: A Vector of the scale of the input, relative to the Object's scale.
		* **parameters.width**: An Int of how wide the input will be, relative to the Object.
		* **parameters.height**: An Int of how tall the input will be, relative to the Object.
		* **parameters.font_size**: An Int of the size the label/value font will be, relative to the Object.
		* **parameters.color**: A Color for the input's background.
		* **parameters.font_color**: A Color for the value text.
		* **parameters.tooltip**: A String for a popup of text, similar to how an Object's name is displayed on mouseover.
		* **parameters.alignment**: An Int for how text is aligned in the input box.
			* **1**: Automatic
			* **2**: Left
			* **3**: Center
			* **4**: Right
			* **5**: Justified
		* **parameters.value**: A String of the text entered into the input.
		* **parameters.validation**: An Int which determines what characters can be input into the value.
			* **1**: None
			* **2**: Integer
			* **3**: Float
			* **4**: Alphanumeric
			* **5**: Username
			* **6**: Name
		* **parameters.tab**: An Int which determines how pressing tab is handled when inputting.
			* **1**: None
			* **2**: Select Next Input
			* **3**: Indent
			
	``` Lua
	self.editInput({index=0, value="New Value"})
	```

---


####getButtons()

Returns a Table of all buttons on this Object. The Table contains parameters tables with the same keys as seen in the [createButton](#createbutton) section, except each Table of parameters also contains an __index__ entry. This is used to identify each button, used by [editButton](#editbutton) and [removeButton](#removebutton).

Indexes start at 0.

---


####getInputs()

Returns a Table of all inputs on this Object. The Table contains parameters tables with the same keys as seen in the [createInput](#createinput) section, except each Table of parameters also contains an __index__ entry. This is used to identify each input, used by [editInput](#editinput) and [removeInput](#removeinput).

Indexes start at 0.

---


####removeButton(...)

Removes a specific button. Indexes start at 0. The first button on any given Object has an index of 0, the next button on it has an index of 1, etc. Each Object has its own indexes.

Removing an index instantly causes all other higher indexes to shift down 1.

!!!info "removeButton(Int index)"
	* **Int index**: An Int of the button's index to remove.

---


####removeInput(...)

Removes a specific input. Indexes start at 0. The first button on any given Object has an index of 0, the next input on it has an index of 1, etc. Each Object has its own indexes.

Removing an index instantly causes all other higher indexes to shift down 1.

!!!info "removeInput(Int index)"
	* **Int index**: An Int of the input's index to remove.

---


###Get Function Details


####getCustomObject()

Returns a Table with the Custom Object information of a Custom Object. See the [Spawnable Objects](spawnableobject) page for the kind of information returned.

``` Lua
--Example returned Table for a custom token
{
	image = "SOME URL HERE",
	thickness = 0.2,
	merge_distance = 15,
	stackable = false,
}
```

---


####getObjects()

Returns a Table of objects in the script zone/bag/deck. What it returns varies depending on the type of Object it is used on.

If an Object is inside of a container, it does not exist in-game. As a result, you only get data on each Object, not an Object reference.

!!!info "Return Table by Object Type"
	!!!info "Scripting Zone""
		Returns a Table of Object references to every object in the scripting zone.
		
		``` Lua
		{
			object_1,
			object_2,
		}
		```

	!!!info "Bag"
		Returns a Table of sub-Tables, each sub-Table containing data on 1 bagged item. Indexes start at 0.
		
		* **String name**: A String of the name of the Object.
		* **String guid**: A String of the GUID of the Object.
		* **Int index**: A String of the index of the Object, represents the Object's place in the bag.
		
		``` Lua
		{
			name  = "Object Name",
			guid  = "AAA111",
			index = 0,	
		}
		```

	!!!info "Deck"
		Returns a Table of sub-Tables, each sub-Table containing data on 1 card. Indexes start at 0.
		
		* **String nickname**: A String of the name of the card.
		* **String description**: A String of the description of the card.
		* **String guid**: A String of the guid of the card.
		* **Int index**: An Int of the index of the card, represents the card's order in the deck.
		* **String lua_script**: A String of any Lua scripting saved on the card.
		
		``` Lua
		{
			nickname    = "Object Name",
			description = "Object Descripotion",
			guid        = "AAA111",
			index       = 0,
			lua_script  = "Any Lua Script On This Card",
		}
		```

This function is often used with [takeObject(...)](#takeobject) to remove objects from containers.
	
---


####getRotationValues()

Returns a Table of rotation values. Rotation values are used to give value to different rotations (like dice) based on which side is pointed "up". It works by checking all of the rotation values assigned to an object and determining which one of them is closest to pointing up, and then displaying the value associated with that rotation.

You can manually assign rotation values to objects using the Rotation Value Gizmo tool (in the left side Gizmo menu) or using [setRotationValues(...)](setrotationvalues).

!!!info "Return Table"
	The returned Table contains sub-Tables, each sub-Table containing these 2 key/value pairs.
	
	* **Var value**: A Var of what value is associated with a given rotation. Often a String or Int.
	* **Vector rotation**: A Vector of the rotation of the object  that best represents the given value.

``` Lua
--Example returned Table for a coin
{
	{value="Heads", rotation={x=0, y=0, z=0}},
	{value="Tails", rotation={x=0, y=180, z=0}},
}
```

---


####getStates()

Returns a Table of information on the [states](http://berserk-games.com/knowledgebase/creating-states/) of an Object. Stated Objects have ids (indexes) starting with 1.

!!!info "Return Table"
	* **String name**: A String of name of the Object.
	* **String guid**: A String of the GUID of the Object.
	* **Int id**: An Int of the id (index) of the state.
	
``` Lua
--Example returned Table
{
	{
		name = "First State",
		guid = "AAA111",
		id   = 1,
	},
	{
		name = "Second State",
		guid = "BBB222",
		id   = 2,
	},
}
```

---


####getValue()

Returns an Int as the value. What the value represents depends on what type of Object this function is used on.

Object | Value
-- | --
[Clock](clock) | Returns Int of stopwatch/timer current time *(in seconds)*.
[Counter](clock) | Returns Int of counter value.
Rotation Value | Returns Var of the face-up value.
Hidden Zone | Returns String of the Player [Color](color) of the zone.
Poker Chip | Returns Int of the face value. {>>Does not work on custom chips.<<}
Tablet | Returns String of the current URL.

---


###Set Function Details

####setCustomObject(...)

Sets a custom Object's properties. It can be used after [spawnObject](base#spawnobject) or on an already existing custom Object. If used on an already existing custom Object, you must use [reload](#reload) on the object after setCustomObject for the changes to be displayed.

!!!info "setCustomObject(Table parameters)"
	The Table of parameters varies, depending on which type of custom Object it is. See the [Spawnable Object](spawnableobject) page for the parameters needed.
	
``` Lua
--Example of a custom token
params = {
	image = "SOME URL HERE",
	thickness = 0.2,
	merge_distance = 15,
	stackable = false,
}
obj.setCustomObject(params)
```

---


####setRotationValues(...)

Sets rotation values of an object. Rotation values are used to give value to different rotations (like dice). It works by checking all of the rotation values assigned to an object and determining which one of them is closest to pointing up, and then displaying the value associated with that rotation.

!!!info "setRotationValues(Table rotation_values)"
	* **Table rotation_values**: A Table containing Tables with the following values. 1 sub-Table per "face".
		* **rotation_values.value**: A Var of what value is associated with a given rotation. Often a String or Int.
		* **rotation_values.rotation**: A Vector of the rotation of the object  that best represents the given value.

``` Lua
--Example setting of rotation values for a coin
rotation_values = {
	{value="Heads", rotation={x=0, y=0, z=0}},
	{value="Tails", rotation={x=0, y=180, z=0}},
}
self.setRotationValues(rotation_values)
```

---


####setValue(...)

Sets an Int as the value of an Object. What the value represents depends on what type of Object it is.

Object | Value
-- | --
[Clock](clock) | Set Int for stopwatch/timer current time *(in seconds)*.
[Counter](clock) | Set Int for counter value.
Rotation Value | Set Var for the face-up value.
Hidden Zone | Set String for the Player [Color](color) of the zone.
Tablet | Set String for the current URL.

---


###Action Function Details

####call(...)

Used to call a Lua function on this Object. This is used to remotely call functions in other scripts, either in Global or Object scripts. `Global` is the "Object" to use to call a function in the Global script.

If the function that is called has a `return` Variable, it is returned like any function call would be. See example.

!!!info "call(String func_name, Table func_params)"
	* **String func_name**: A String of the function name you want to activate.
	* **Table func_name**: A Table containing any data you want to pass to that function.
		* {>>Optional, will not be sent by default.<<}

``` Lua
--Call, used from an Object script
params = {
	msg   = "Hello world!",
	color = {r=0.2, g=1, b=0.2},
}
--Success would be set to true by the return value in the function
success = Global.call("testFunc", params)
```
``` Lua
--Function in Global
function testFunc(params)
	broadcastToAll(params.msg, params.color)
	return true
end
```

---


####clone(...)

Copy/Paste this Object, returns a reference to the new Object.

!!!info "clone(Table parameters)"
	* **Table parameters**: A Table with information used when pasting.
		* **parameters.position**: A Vector of where the Object is placed.
			* {>>Optional, defaults to {x=0, y=3, z=0}.<<}
		* **parameters.snap_to_grid**: A Bool for if the Object snaps to grid.
			* {>>Optional, defaults to false.<<}

---


####deal(...)

Deals Objects to hand zones. Will deal from decks/bags/stacks as well as individual items. If dealing an individual item to a hand zone, it is a good idea to make sure that its [Member Variable](#member-variables) for `use_hands` is `true`.

!!!info "deal(Int number, String player_color, Int index)"
	* **Int number**: An Int of how many to deal.
	* **String player_color**: A String of the Color to deal to.
		* {>>Optional, defaults to an empty string. If not supplied, it will attempt to deal to all seated players.<<}
	* **Int index**: An Int of which Object to deal from a container.
		* {>>Optional, defaults to 0. If not supplied it will deal in regular order.<<}

---


####dealToColorWithOffset(...)

Deals from a deck to a position relative to the hand zone.

==Returns an Object reference to the dealt card.==

!!!info "dealToColorWithOffset(Vector, Bool flip, String player_color)"
	* **Vector**: A Vector of the x/y/z offset to deal to around the given hand zone.
	* **Bool flip**: A Bool for if the card is flipped over when dealt.
	* **String player_color**: A String of the hand zone Color to offset dealing to.

``` Lua
--Example of dealing 2 cards in front of the White player, face up.
self.dealToColorWithOffset({-2,0,5}, true, "White")
self.dealToColorWithOffset({ 2,0,5}, true, "White")
```


####putObject(...)

Places an object into a container (chip stacks/bags/decks).

!!!info "putObject(Object put_object)"
	* **Object put_object**: An Object to place into the container.

``` Lua
--Example of a script on a bag that places Object into itself
local obj = getObjectFromGUID("AAA111")
self.putObject(obj)
```

---


####reload()

Returns Object reference of itself after it respawns itself. This function causes the Object to be deleted and respawned instantly to refresh it, so its old Object reference will no longer be valid.

Most often this is used after using [setCustomObject(...)](#setcustomobject) to modify a custom object.

---


####takeObject(...)

Takes an object from a container (bag/deck/chip stack) and places it in the world.

==Returns an Object reference to the taken Object.==

!!!tip
	Spawned Objects take a moment to be physically spawned into the game. The purpose of the callback functionality is to allow you to run additional actions after the Object has been initiated fully into the instance. It is also possible to add a delay using a [coroutine](#startluacoroutine).
	
!!!info "takeObject(Table parameters)"
	* **Table parameters**: A Table of parameters used to determine how takeObject will act.
		* **parameters.position**: A Table Vector of the position to place Object.
			* {>>Optional, defaults to container's position + 2 on the x axis.<<}
		* **parameters.rotation**: A Table Vector of the rotation of the Object.
			* {>>Optional, defaults to the container's rotation.<<}
		* **parameters.flip**: A Bool for if the Object is flipped over.
			* {>>Optional, defaults to false. Only used with decks, not bags/stacks.<<}
			* {>>If rotation is used, flip's Bool will be ignored.<<}
		* **parameters.guid**: A String of the GUID of the Object to take.
			* {>>Optional,  no default. Only use index or guid, never both.<<}
		* **parameters.index**: An Int of the index of the Object to take.
			* {>>Optional,  no default. Only use index or guid, never both.<<}
		* **parameters.top**: A Bool for if an object is taken from the top (vs bottom).
			* {>>Optional, defaults to true.<<}
		* **parameters.smooth**: A Bool for if the taken Object moves smoothly or instantly. 
			* {>>Optional, defaults to true.<<}
		* **parameters.callback**: A String of the function name you want activated once the Object is initiated.
			* {>>Optional, no default.<<}
			* {>>A callback function has 2 parameters, the Object spawned and, if used, the Table of params.<<}
		* **parameters.callback_owner**: An Object of what Object has the callback function in its script. Global is a valid target.
			* {>>Optional, defaults to container Object. Serves no purpose if callback is not also used.<<}
		* **parameters.params**: A Table of data to send to the callback to use as parameters. See example.
			* {>>Optional, no default. Serves no purpose if callback is not also used.<<}

``` Lua
function onLoad()
    futureName = "Taken from container!"
    takeParams = {
        position = {x=0, y=3, z=5},
        callback = "take_callback",
        callback_owner = self,
        params = {name = futureName},
    }
    self.takeObject(takeParams)
end

function take_callback(object_spawned, params)
    object_spawned.setName(params.name)
end
```
	

???tip "Tip for using GUID to pull Object"
	When getting the GUIDs of objects in a container, it is possible items can have the same GUID while in a container. This is because only once two items try to exist at the same time is one of them given a new GUID, and Objects in a container do not currently exist. Removing all Objects from the container at once will force all of them to be given unique GUIDs.

???tip "Tip for using index to pull Object"
	When you take an Object from the container, all higher indexes are reduced by 1 instantly. If you pull more than once Object at once by their index, you must account for this index changing.








	
