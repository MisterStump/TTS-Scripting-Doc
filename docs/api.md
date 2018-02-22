The API is consistent for Global or [Object](object) scripts, but [Object](object) scripts have access to `self` which is the Object the script is attached to. An introduction can be found [here](index).

##Classes

Tabletop Simulator contains classes. Classes, generally speaking, are collections of functions which interact with specific functionality of certain elements in-game. Links to all of the classes are also available on the left.

###Classes
* [Clock](clock)
* [Counter](counter)
* [Object](object)
* [AssetBundle](assetbundle)
* [RPGFigurine](rpgfigurine)
* [TextTool](texttool)

###Static Classes
* [JSON](json)
* [Player](player)
* [Timer](timer)
* [WebRequest](webrequest)
* [Physics](physics)
* [Lighting](lighting)


##Function Summary



###Default Events (Global & Object)
These are functions which are triggered by an event taking place in-game. They work when within the script of an Object or the Global script.

Function Name | Description
-- | --
onChat(String message, Player) | Called when a chat message is sent in game chat. [&#8263;](#onchat)
onExternalMessage(Table) | Called when an external script editor (like [Atom](atom)) sends a message back to the game. Used for custom editor functionality. [&#8263;](#onexternalmessage)
onFixedUpdate() | Called **every physics tick** (90 times a second). This is a frame independent onUpdate(). [&#8263;](#onfixedupdate)
onLoad(String save_state) | Called when a game save is finished loading every Object. It is where most setup code will go. [&#8263;](#onload)
onObjectDestroy(Object dying_object) | Called whenever any object is destroyed. [&#8263;](#onobjectdestroy)
onObjectDrop<br>(string player_color, Object dropped_object) | Called whenever any object is dropped by a player. [&#8263;](#onobjectdrop) 






###Default Events (Object Only)
These are functions which are triggered by an event taking place in-game. They only work within scripts that are on Objects, never in Global.

Function Name | Description
-- | --
onCollisionEnter(Table collision_info) | Called when an Object starts colliding with the Object the function is on. [&#8263;](#oncollisionenter)
onCollisionExit(Table collision_info) | Called when an Object stops colliding with the Object the function is on. [&#8263;](#oncollisionexit)
onCollisionStay(Table collision_info) | Called **every frame** that an Object is colliding with the Object this function is on. [&#8263;](#oncollisionstay)
onDestroy() | Called when an Object it is on is destroyed. [&#8263;](#ondestroy)
onDrop(String [player_color](player)) | Called when a player releases an Object after picking it up. [&#8263;](#ondrop)






---

##Function Details (Global & Object)

###onChat(...)

This function is called when a message is sent through the in-game chat. It does not trigger when global chat messages are sent. Using `#!lua return false` inside of this function prevents the chat message which triggered it to be supressed.

!!!info onChat(String message, Player)
	* **String message**: A String containing the chat message which triggered the function.
	* **Player**: A reference to the Player which sent the chat message.

``` Lua
    function onChat(message, player)
        print(message)
        print(player.color)
    end
```

---


###onExternalMessage(...)

This function is called when an external script editor (like [Atom](atom)) sends a message back to the game. Used for custom editor functionality.
	
!!!info "onExternalMessage(Table)"
	* **Table**: The data returned by the external editor into the game.
	
``` Lua
	function onExternalMessage(data)
		print("External message received")
	end
```

---


###onFixedUpdate()

Called **every physics tick** (90 times a second). This is a frame independent onUpdate(). [&#8263;](#onfixedupdate)

!!!warning
	This is a very expensive function and can easily slow/crash your game if missused. Use with caution.

``` Lua
	function onFixedUpdate()
		self.addTorque({0,100,0}, 1)
	end
```


###onLoad(...)

This function is called when a game save is finished loading every Object. This is where most setup code will go. The fast-forward and rewind feature will also cause this function to activate. If this function is in an Object's script and that Object is spawned, like by removing it from a container, it too will trigger onLoad().

!!!info "onLoad(String save_state)"
	* **String save_state**: The encoded string containing any save_state (saved) data.
		* {>>If there is no data saved, this returns an empty String.<<}

``` Lua
    function onLoad()
        print("Loading complete")
    end
```

???example "Example of onLoad and onSave being used to save/load data"
    ``` Lua
        --Runs whenever game is saved/autosaved
		function onSave()
			local data_to_save = {someData=50}
			saved_data = JSON.encode(data_to_save)
			--saved_data = "" --Remove -- at start & save to clear save data
			return saved_data
		end

		--Runs when game is loaded
		function onLoad(saved_data)
			--Loads the tracking for if the game has started yet
			if saved_data ~= "" then
				local loaded_data = JSON.decode(saved_data)
				someData = loaded_data.someData
			else
				someData = 50
			end
		end
    ```

---


###onObjectDestroy(...)

Called whenever any object is destroyed. The dying Object has 1 frame left to live. This event fires immediately before the dying Object’s `onDestroy()` but their lifetime is the same final frame.

!!!info "onObjectDestroy(Object dying_object)"
	* **Object dying_object**: The object that was destroyed.
	
``` Lua
	function onObjectDestroy(destroyedObj)
		print(destroyedObj.getName())
	end
```

---


###onObjectDrop(...)

Called whenever any object is dropped by a player.

!!!info "onObjectDrop(String player_color, Object dropped_object)"
	* **String player_color**: A String of the color of the player who dropped the object.
	* **Object dropped_object**: The Object in game which was dropped.
	
``` Lua
	function onObjectDrop(colorName, obj)
		print(colorName .. " dropped " .. obj.getName())
	end
```


    
	
	
	
















##Function Details (Object only)

###onCollisionEnter(...)

This function is called when an Object starts colliding with the Object the function is on. Does not work in Global.

!!!info "onCollisionEnter(Table collision_info)"
	* **table collision_info**: A Table containing data on colliding object.
		* **collision_info.*collision_object*** = [Object](object) collision_object
		* **collision_info.*contact_points*** = Table contact_points
			* {>>This is an array (table) of tables. Each contact point is a vector.<<}
		* **collision_info.*relative_velocity*** = [Vector](vector)

``` Lua
    --Example Usage
    function onCollisionEnter(info)
        print(info.collision_object)
    end
```
``` Lua
    --Example returned table
    {
        collision_object = objectReference
        contact_points = {
            {x=5, y=0, z=-2, 5, 0, -2},
        }
        relative_velocity = {x=0, y=20, z=0, 0, 20, 0}
    }
```

---


###onCollisionExit(...)

This function is called when an Object stops colliding with the Object the function is on. Does not work in Global.

!!!info "onCollisionExit(Table collision_info)"
	* **table collision_info**: A Table containing data on colliding object.
		* **collision_info.*collision_object*** = [Object](object) collision_object
		* **collision_info.*contact_points*** = Table contact_points
			* {>>This is an array (table) of tables. Each contact point is a vector.<<}
		* **collision_info.*relative_velocity*** = [Vector](vector)

``` Lua
    --Example Usage
    function onCollisionExit(info)
        print(info.collision_object)
    end
```
``` Lua
    --Example returned table
    {
        collision_object = objectReference
        contact_points = {
            {x=5, y=0, z=-2, 5, 0, -2},
        }
        relative_velocity = {x=0, y=20, z=0, 0, 20, 0}
    }
```

---


###onCollisionStay(...)

This function is called **every frame** that an Object is colliding with the Object this function is on. Does not work in Global.

!!!warning
	This is a very expensive function and can easily slow/crash your game if missused. Use with caution.

!!!info "onCollisionStay(Table collision_info)"
	* **table collision_info**: A Table containing data on colliding object.
		* **collision_info.*collision_object*** = [Object](object) collision_object
		* **collision_info.*contact_points*** = Table contact_points
			* {>>This is an array (table) of tables. Each contact point is a vector.<<}
		* **collision_info.*relative_velocity*** = [Vector](vector)

``` Lua
    --Example Usage
    function onCollisionStay(info)
        print(info.collision_object)
    end
```
``` Lua
    --Example returned table
    {
        collision_object = objectReference
        contact_points = {
            {x=5, y=0, z=-2, 5, 0, -2},
        }
        relative_velocity = {x=0, y=20, z=0, 0, 20, 0}
    }
```

---


###onDestroy()

This function is called when an [Object](object) it is on is destroyed. When `onDestroy()` is called, the Object has one frame left to live but its recommended to avoid using it as a reference here. This event fires immediately after [onObjectDestroy()](#onobjectdestroy) but their lifetime is the same final frame. Does not work in Global.

``` Lua
    function onDestroy()
        print("This object was destroyed!")
    end
```

---

###onDrop(...)

This function is called when this [Object](object) is dropped. Does not work in Global.

!!!info "onDrop(String player_color)"
	* **String player_color**: A String of a [Player](player)'s color.

``` Lua
    function onDrop(color)
        print(color)
    end
```

---



































