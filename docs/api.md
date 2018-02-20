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



###Default Events
These are functions which are triggered by an event taking place in-game.

Function Name | Description
-- | --
onChat(string message, player) | [This function is called, if it exists in your script, when a player chats. `return false` in this event to block the message.](#onchat)
onCollisionEnter(table collision_info) | [This function is called, if it exists in your script, when this object collides with another object. The Global script does not have this event since it is not an object which can collide with other objects.](#oncollisionenter)
onCollisionExit(table collision_info) | [This function is called, if it exists in your script, when this object stops touching another object. The Global Script does not have this event since it does not have a physical representation that can collide.](#oncollisionexit)













##Function Details

###onChat(...)

This function is called, if it exists in your script, when a player chats. `return false` in this event to block the message.

``` Lua
    function onChat(message, player)
        print(message)
        print(player.color)
    end
```

---


###onCollisionEnter(...)

onCollisionEnter(table collision_info) | This function is called, if it exists in your script, when this [object](object) collides with another object. The Global script does not have this event since it is not an object which can collide with other objects.

!!!warning "onCollisionEnter(table collision_info)"
	* **table collision_info**: A table containing data on colliding object.
		* **collision_info.*collision_object*** = [object](object) collision_object
		* **collision_info.*contact_points*** = table contact_points {>>This is an array (table) of tables. Each contact point is a vector.<<}
		* **collision_info.*relative_velocity*** = [vector](vector)

``` Lua
    --Example Usage
    function onCollisionEnter(info)
        print(info.collision_object)
    end
```
``` Lua
    --Example returned table
    {
		{
            collision_object = objectReference
            contact_points = {
                {x=5, y=0, z=-2, 5, 0, -2},
            }
            relative_velocity = {x=0, y=20, z=0, 0, 20, 0}
        }
    }
```

---


###onCollisionExit(...)

This function is called, if it exists in your script, when this object stops touching another [object](object). The Global Script does not this event since it does not have a physical representation that can collide.

!!!warning "onCollisionExit(table collision_info)"
	* **table collision_info**: A table containing data on exit-colliding object.
		* **collision_info.*collision_object*** = [object](object) collision_object
		* **collision_info.*contact_points*** = table contact_points {>>This is an array (table) of tables. Each contact point is a vector.<<}
		* **collision_info.*relative_velocity*** = [vector](vector)

``` Lua
    --Example Usage
    function onCollisionExit(info)
        print(info.collision_object)
    end
```
``` Lua
    --Example returned table
    {
		{
            collision_object = objectReference
            contact_points = {
                {x=5, y=0, z=-2, 5, 0, -2},
            }
            relative_velocity = {x=0, y=20, z=0, 0, 20, 0}
        }
    }
```

---


