Player, a static global class, allows control over in-game players and their [hand zones](http://berserk-games.com/knowledgebase/hands/). You call these functions like this: `Player["White"].seated` or `Player["Green"].mute()`.


##Member Variables

Like [Object member variables](object#member-variables), Player has its own member variables.

Variable | Description | Type
-- | -- | :--
admin | If the player is promoted or the host of the game. Read only. | Bool
blindfolded | If the player is blindfolded. | Bool
color | The player's [Player Color](player-color). Read only. | String
host | If the player is the host. Read only. | Bool
lift_height | The lift height for the player. This is how far an object is raised when held in a player's hand. Value is ranged 0 to 1. | Float
promoted | If the current player is promoted. | Bool
seated | If a player is currently seated at this color. Read only. | Bool
steam_id | The Steam ID of the player. This is unique to each player's Steam account. Read only. | String
steam_name | The Steam name of the player. Read only. | String
Team | The team of the player.<br>Options: `"None", "Clubs", "Diamonds", "Hearts", "Spades", "Jokers"`. | String

---

##Function Summary

###Class Functions

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
attachCameraToObject(Table parameters) | Makes a Player's camera follow an Object. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#attachcameratoobject)
broadcast(String message, Color) | Print message on Player's screen and their game chat log. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#broadcast)
changeColor(String player_color) | Changes player to this [Player Color](player-color). Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#changecolor)
getHandCount() | Returns the number of [hand zones](http://berserk-games.com/knowledgebase/hands/) owned by this color. | 
getHandObjects(Int hand_index) | Returns a Table of Objects that are in this [hand zone](http://berserk-games.com/knowledgebase/hands/). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gethandobjects)
getHandTransform(Int hand_index) | Returns a Table of data on this [hand zone](http://berserk-games.com/knowledgebase/hands/). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gethandtransform)
getHoldingObjects() | Returns Table of Objects a Player is holding in their hand. | 
getHoverObject() | Returns Object that the Player's pointer is hovering over. | 
getPointerPosition() | Returns Vector of the Player's pointer coordinates. |
getSelectedObjects() | Returns Table of Objects that the Player has selected with an area selection. | 
kick() | Kicks Player out of the room. Returns Bool. | 
lookAt(Table parameters) | Moves a Player's camera, forcing 3'rd person camera mode. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#lookat)
mute() | Mutes or unmutes Player, preventing/allowing voice chat. Returns Bool. | 
print(String message, Color) | Prints a message into the Player's game chat. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#print)
promote() | Promotes/demotes a Player. Promoted players have access to most host privileges. Returns Bool. |
setHandTransform(Table parameters, Int hand_index) | Sets transform elements of a hand zone. Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#sethandtransform)



###Direct Class Functions
These functions return direct references to Players, not a Player Color. 

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
getPlayers() | Returns Table of all Players in the instance. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getplayers)
getSpectators() | Returns Table of all Players in spectator (Grey). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getspectators)


---

##Function Details

###Class Function Details

####attachCameraToObject(...)

Makes a Player's camera follow an Object. Returns Bool.

> Returns Bool

!!!info "attachCameraToObject(Table parameters)"
    * **Table parameters**: A Table with parameters which guide the function.
        * **parameters.object**: The Object to attach the camera to.
        * **parameters.offset**: A Vector to offset the camera by.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
    
``` Lua
self.attachCameraToObject({object=self})
```

---


####broadcast(...)

Print message on Player's screen and their game chat log.

>Returns Bool.

!!!info "broadcast(String message, Color)"
    * **String message**: A String to be displayed.
    * **Color**: A Color Table for the text to be tinted.
        * {>>Optional, defaults to {r=1, g=1, b=1}.<<}

---


####changeColor(...)

Changes player to this [Player Color](player-color).

> Returns Bool.

!!!info "changeColor(String player_color)"
    * **String player_color**: A String of the color seat to move the Player to.

``` Lua
Player["White"].changeColor("Red")
```

---


####getHandObjects(...)

Returns a Table of Objects that are in this [hand zone](http://berserk-games.com/knowledgebase/hands/).

!!!info "getHandObjects(Int hand_index)"
    * **Int hand_index**: An Int of the index, representing which hand zone to return Objects for.
        * {>>Optional, defaults to 1.<<}

!!!tip "Indexing"
    Hand indexes start at 1 and are numbered in the order of their creation. Each Player color has its own indexes.

---


####getHandTransform(Int hand_index)

Returns a Table of data on this [hand zone](http://berserk-games.com/knowledgebase/hands/).

!!!info "getHandTransform(Int hand_index)"
    * **Int hand_index**: An Int of the index, representing which hand zone to return data on.
        * {>>Optional, defaults to 1.<<}

!!!info "Return Data Table"
    * **Table data**: The Table the data is returned in
        * **data.position**: A Vector of the position of the hand zone.
        * **data.rotation**: A Vector of the rotation of the hand zone.
        * **data.scale**: A Vector of the scale of the hand zone.
        * **data.forward**: A Vector of the forward direction of the hand zone.
        * **data.right**: A Vector of the right direction of the hand zone.
        * **data.up**: A Vector of the up direction of the hand zone.

!!!tip "Indexing"
    Hand indexes start at 1 and are numbered in the order of their creation. Each Player color has its own indexes.
    
---


####lookAt(...)

Moves a Player's camera, forcing 3'rd person camera mode.

> Returns Bool.

!!!info "lookAt(Table parameters)"
    * **Table parameters**: A Table of controlling parameters to point the player camera.
        * **parameters.position**: A Vector of the position to center the camera to.
        * **parameters.pitch**: A Float of the pitch angle of the camera. 0 to 90.
            * {>>Optional, defaults to 0.<<}
        * **parameters.yaw**: A Float of the yaw angle of the camera. -180 to 180.
            * {>>Optional, defaults to 0.<<}
        * **parameters.distance**: A Float of the distance the camera is from the position Vector.
            * {>>Optional, defaults to 40.<<}
        
``` Lua
--Assuming someone is in the White seat
Player["White"].lookAt({
    position = {x=0,y=0,z=0},
    pitch    = 25,
    yaw      = 180,
    distance = 20,
})
```

---


####print(...)

Prints a message into the Player's game chat.

> Returns Bool.

!!!info "print(String message, Color)"
    * **String message**: A String to be displayed.
    * **Color**: A Color Table for the text to be tinted.
        * {>>Optional, defaults to {r=1, g=1, b=1}.<<}

---


####setHandTransform(...)

Sets transform elements of a [hand zone](http://berserk-games.com/knowledgebase/hands/).

> Returns Bool.

!!!tip "setHandTransform(Table parameters, Int hand_index)"
    * **Table parameters**: The Table the data to transform the hand zone with.
        * **parameters.position**: A Vector of the position of the hand zone.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * **parameters.rotation**: A Vector of the rotation of the hand zone.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * **parameters.scale**: A Vector of the scale of the hand zone.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
    * **Int hand_index**: An Int of the index, representing which hand zone to modify.
        * {>>Optional, defaults to 1.<<}

!!!tip "Indexing"
    Hand indexes start at 1 and are numbered in the order of their creation. Each Player color has its own indexes.
    
``` Lua
--Example of moving/rotating/scaling hand zone
params = {
    position = {x=0, y=5, z=0},
    rotation = {x=0, y=45, z=0},
    scale    = {x=2, y=2, z=2},
}
Player["White"].setHandTransform(params, 2)
```

---


###Direct Class Function Details

####getPlayers()

Returns Table of all Players in the instance.

``` Lua
--Blindfolding all players
playerList = Player.getPlayers()
for _, playerReference in ipairs(playerList) do
    playerReference.blindfolded = true
end
```

---


####getSpectators()

Returns Table of all Players in spectator (Grey).

``` Lua
--Printing steam name of all players to host chat
playerList = Player.getSpectators()
for _, playerReference in ipairs(playerList) do
    print(playerReference.steam_name)
end
```
