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
changeColor(Color) | Changes player to this [Player Color](player-color). Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#changecolor)
getHandCount() | Returns the number of [hand zones](http://berserk-games.com/knowledgebase/hands/) owned by this color. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gethandcount)
getHandObjects(Int hand_index) | Returns a Table of Objects that are in this [hand zone](http://berserk-games.com/knowledgebase/hands/). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gethandobjects)
getHandTransform(Int hand_index) | Returns a Table of data on this [hand zone](http://berserk-games.com/knowledgebase/hands/). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gethandtransform)
getHoldingObjects() | Returns Table of Objects a Player is holding in their hand. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getholdingobjects)
getHoverObject() | Returns Object that the Player's pointer is hovering over. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#gethoverobject)
getPointerPosition() | Returns Vector of the Player's pointer coordinates. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getpointerposition)
getSelectedObjects() | Returns Table of Objects that the Player has selected with an area selection. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getselectedobjects)
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
