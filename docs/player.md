Player, a static global class, allows control over in-game players and their [hand zones](http://berserk-games.com/knowledgebase/hands/). 

Example Usage: `Player["White"].seated` or `Player["Green"].mute()`


##Member Variables

Like [Object member variables](object#member-variables), Player has its own member variables.

Variable | Description | Type
-- | -- | :--
admin | If the player is promoted or the host of the game. Read only. | [<span class="tag boo"></span>](typeandclass)
blindfolded | If the player is blindfolded. | [<span class="tag boo"></span>](typeandclass)
color | The player's [Player Color](player-color). Read only. | [<span class="tag str"></span>](typeandclass)
host | If the player is the host. Read only. | [<span class="tag boo"></span>](typeandclass)
lift_height | The lift height for the player. This is how far an object is raised when held in a player's hand. Value is ranged 0 to 1. | [<span class="tag flo"></span>](typeandclass)
promoted | If the current player is promoted. | [<span class="tag boo"></span>](typeandclass)
seated | If a player is currently seated at this color. Read only. | [<span class="tag boo"></span>](typeandclass)
steam_id | The Steam ID of the player. This is unique to each player's Steam account. Read only. | [<span class="tag str"></span>](typeandclass)
steam_name | The Steam name of the player. Read only. | [<span class="tag str"></span>](typeandclass)
Team | The team of the player.<br>Options: `"None", "Clubs", "Diamonds", "Hearts", "Spades", "Jokers"`. | [<span class="tag str"></span>](typeandclass)

---

##Function Summary

###Class Functions

Function Name | Description | Return | &nbsp; 
-- | -- | -- | --
attachCameraToObject([<span class="tag tab"></span>](typeandclass)&nbsp; parameters) | Makes a Player's camera follow an Object. | [<span class="ret boo"></span>](typeandclass) | [<span class="i"></span>](#attachcameratoobject)
broadcast([<span class="tag str"></span>](typeandclass)&nbsp; message, [<span class="tag str"></span>](typeandclass)&nbsp; Color) | Print message on Player's screen and their game chat log. | [<span class="ret boo"></span>](typeandclass) | [<span class="i"></span>](#broadcast)
changeColor([<span class="tag str"></span>](typeandclass)&nbsp; player_color) | Changes player to this [Player Color](player-color). | [<span class="ret boo"></span>](typeandclass) | [<span class="i"></span>](#changecolor)
getHandCount() | Returns the number of [hand zones](http://berserk-games.com/knowledgebase/hands/) owned by this color. | [<span class="ret int"></span>](typeandclass)
getHandObjects([<span class="tag int"></span>](typeandclass)&nbsp; hand_index) | Returns a Table of Objects that are in this [hand zone](http://berserk-games.com/knowledgebase/hands/). | [<span class="ret tab"></span>](typeandclass) | [<span class="i"></span>](#gethandobjects)
getHandTransform([<span class="tag int"></span>](typeandclass)&nbsp; hand_index) | Returns a Table of data on this [hand zone](http://berserk-games.com/knowledgebase/hands/). | [<span class="ret tab"></span>](typeandclass) | [<span class="i"></span>](#gethandtransform)
getHoldingObjects() | Returns Table of Objects a Player is holding in their hand. | [<span class="ret tab"></span>](typeandclass)
getHoverObject() | Object that the Player's pointer is hovering over. | [<span class="ret obj"></span>](typeandclass)
getPointerPosition() | Returns the Vector of the Player's pointer coordinates. | [<span class="ret tab"></span>](typeandclass)
getSelectedObjects() | Returns Table of Objects that the Player has selected with an area selection. | [<span class="ret tab"></span>](typeandclass)
kick() | Kicks Player out of the room. | [<span class="ret boo"></span>](typeandclass)
lookAt([<span class="tag tab"></span>](typeandclass)&nbsp; parameters) | Moves a Player's camera, forcing 3'rd person camera mode. | [<span class="ret boo"></span>](typeandclass) | [<span class="i"></span>](#lookat)
mute() | Mutes or unmutes Player, preventing/allowing voice chat. | [<span class="ret boo"></span>](typeandclass)
print([<span class="tag str"></span>](typeandclass)&nbsp; message, [<span class="tag tab"></span>](typeandclass)&nbsp; Color) | Prints a message into the Player's game chat. | [<span class="ret boo"></span>](typeandclass) | [<span class="i"></span>](#print)
promote() | Promotes/demotes a Player. Promoted players have access to most host privileges. | [<span class="ret boo"></span>](typeandclass) |
setHandTransform([<span class="tag tab"></span>](typeandclass)&nbsp; parameters, [<span class="tag int"></span>](typeandclass)&nbsp; hand_index) | Sets transform elements of a hand zone. | [<span class="ret boo"></span>](typeandclass) | [<span class="i"></span>](#sethandtransform)



###Direct Class Functions
These functions return direct references to Players, not a Player Color. See details section for usage.

Function Name | Description | Return | &nbsp; 
-- | -- | -- | --:
getPlayers() | Returns Table of all Players in the instance. | [<span class="ret tab"></span>](typeandclass) | [<span class="i"></span>](#getplayers)
getSpectators() | Returns Table of all Players in spectator (Grey). | [<span class="ret tab"></span>](typeandclass) | [<span class="i"></span>](#getspectators)


---

##Function Details

###Class Function Details

####attachCameraToObject(...)

[<span class="ret boo"></span>](typeandclass)&nbsp; Makes a Player's camera follow an Object. Returns Bool.

!!!info "attachCameraToObject([<span class="tag tab"></span>](typeandclass)&nbsp; parameters)"
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters**: A Table with parameters which guide the function.
        * [<span class="tag obj"></span>](typeandclass)&nbsp; **parameters.object**: The Object to attach the camera to.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.offset**: A Vector to offset the camera by.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
    
``` Lua
self.attachCameraToObject({object=self})
```

---


####broadcast(...)

[<span class="ret boo"></span>](typeandclass)&nbsp; Print message on Player's screen and their game chat log.

!!!info "broadcast([<span class="tag str"></span>](typeandclass)&nbsp; message, [<span class="tag tab"></span>](typeandclass)&nbsp; Color)"
    * [<span class="tag str"></span>](typeandclass)&nbsp; **message**: The message to be displayed.
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **Color**: A [Color](typeandclass#color) table, used to tint the message.
        * {>>Optional, defaults to {r=1, g=1, b=1}.<<}

---


####changeColor(...)

[<span class="ret boo"></span>](typeandclass)&nbsp; Changes player to this [Player Color](player-color).

!!!info "changeColor([<span class="tag str"></span>](typeandclass)&nbsp; player_color)"
    * [<span class="tag str"></span>](typeandclass)&nbsp; **player_color**: The [player color](player-color) seat to move the Player to.

``` Lua
Player["White"].changeColor("Red")
```

---


####getHandObjects(...)

[<span class="ret tab"></span>](typeandclass)&nbsp; Returns a Table of Objects that are in this [hand zone](http://berserk-games.com/knowledgebase/hands/).

!!!info "getHandObjects([<span class="tag int"></span>](typeandclass)&nbsp; hand_index)"
    * [<span class="tag int"></span>](typeandclass)&nbsp; **hand_index**: An index, representing which hand zone to return Objects for.
        * {>>Optional, defaults to 1.<<}

!!!tip "Indexing"
    Hand indexes start at 1 and are numbered in the order of their creation. Each Player color has its own indexes.

---


####getHandTransform(Int hand_index)

[<span class="ret tab"></span>](typeandclass)&nbsp; Returns a Table of data on this [hand zone](http://berserk-games.com/knowledgebase/hands/).

!!!info "getHandTransform([<span class="tag int"></span>](typeandclass)&nbsp; hand_index)"
    * [<span class="tag int"></span>](typeandclass)&nbsp; **hand_index**: An index, representing which hand zone to return data on.
        * {>>Optional, defaults to 1.<<}

!!!info "Return Data Table"
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **data**: The Table the data is returned in.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **data.position**: A Vector of the position of the hand zone.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **data.rotation**: A Vector of the rotation of the hand zone.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **data.scale**: A Vector of the scale of the hand zone.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **data.forward**: A Vector of the forward direction of the hand zone.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **data.right**: A Vector of the right direction of the hand zone.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **data.up**: A Vector of the up direction of the hand zone.

!!!tip "Indexing"
    Hand indexes start at 1 and are numbered in the order of their creation. Each Player color has its own indexes.
    
---


####lookAt(...)

[<span class="ret boo"></span>](typeandclass)&nbsp; Moves a Player's camera, forcing 3'rd person camera mode.

!!!info "lookAt([<span class="tag tab"></span>](typeandclass)&nbsp; parameters)"
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters**: A Table of controlling parameters to point the player camera.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.position**: A Vector of the position to center the camera on.
        * [<span class="tag flo"></span>](typeandclass)&nbsp; **parameters.pitch**: The pitch angle of the camera. 0 to 90.
            * {>>Optional, defaults to 0.<<}
        * [<span class="tag flo"></span>](typeandclass)&nbsp; **parameters.yaw**: The yaw angle of the camera. -180 to 180.
            * {>>Optional, defaults to 0.<<}
        * [<span class="tag flo"></span>](typeandclass)&nbsp; **parameters.distance**: The distance the camera is from the position Vector.
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

[<span class="ret boo"></span>](typeandclass)&nbsp; Prints a message into the Player's game chat.

!!!info "print([<span class="tag str"></span>](typeandclass)&nbsp; message, [<span class="tag tab"></span>](typeandclass)&nbsp; Color)"
    * [<span class="tag str"></span>](typeandclass)&nbsp; **message**: The text to be displayed.
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **Color**: A [Color](typeandclass#color) Table for the text to be tinted.
        * {>>Optional, defaults to {r=1, g=1, b=1}.<<}

---


####setHandTransform(...)

[<span class="ret boo"></span>](typeandclass)&nbsp; Sets transform elements of a [hand zone](http://berserk-games.com/knowledgebase/hands/).

!!!info "setHandTransform([<span class="tag tab"></span>](typeandclass)&nbsp; parameters, [<span class="tag int"></span>](typeandclass)&nbsp; hand_index)"
    * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters**: The Table the data to transform the hand zone with.
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.position**: A Vector of the position of the hand zone.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.rotation**: A Vector of the rotation of the hand zone.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
        * [<span class="tag tab"></span>](typeandclass)&nbsp; **parameters.scale**: A Vector of the scale of the hand zone.
            * {>>Optional, defaults to {x=0, y=0, z=0}.<<}
    * [<span class="tag int"></span>](typeandclass)&nbsp; **hand_index**: An Int of the index, representing which hand zone to modify.
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

[<span class="ret tab"></span>](typeandclass)&nbsp; Returns Table of all Players in the instance.

``` Lua
--Blindfolding all players
playerList = Player.getPlayers()
for _, playerReference in ipairs(playerList) do
    playerReference.blindfolded = true
end
```

---


####getSpectators()

[<span class="ret tab"></span>](typeandclass)&nbsp; Returns Table of all Players in spectator (Grey).

``` Lua
--Printing steam name of all players to host chat
playerList = Player.getSpectators()
for _, playerReference in ipairs(playerList) do
    print(playerReference.steam_name)
end
```
