These are a loose collection of functions which can be used to perform a variety of actions within Tabletop Simulator. Some of them are used in almost every script.

##Function Summary

###Global Management Functions

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
addNotebookTab(Table parameters) | Returns Int of the index of the newly added notebook tab. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#addnotebooktab)
broadcastToAll(String message, Table [color](color)) | Returns Bool with result of printing an on-screen message to all Players. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#broadcasttoall)
broadcastToColor(String message,String [player_color](player), Table [color](color)) | Returns Bool with result of printing an on-screen message to a specified Player. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#broadcasttocolor)
clearPixelPaint() | Returns Bool with result of removing pixel paint from the instance. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#clearpixelpaint)
clearVectorPaint() | Returns Bool with result of removing vector paint from the instance. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#clearvectorpaint)
copy(Table object_list) | Returns Bool of result of copying a list of Objects the clipboard. Works with [paste(...)](#paste). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#copy)
destroyObject(Object obj) | Returns Bool with the result of destroying an Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#destroyobject)
editNotebookTab(Table parameters) | Returns Bool with the result of editing an existing Tab in the notebook. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#editnotebooktab)
flipTable() | Returns Bool with the result of flipping the table. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#fliptable)
getAllObjects() | Returns Table of all spawned [Objects](object) in the game. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getallobjects)
getNotebookTabs() | Returns Table of all tabs in the notebook. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getnotebooktabs)
getNotes() | Returns String of the contents of the on-screen notes section. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getnotes)
getObjectFromGUID(String guid) | Returns Object from GUID. Will return `nil` if it doesn't exist in-game. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getobjectfromguid)
getSeatedPlayers() | Returns Table of the colors of seated players. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#getseatedplayers)
log(Var element, String tag, String label) | Returns Bool with result of printing information to the log. (Shortcut: ~)  | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#log)
logStyle(String tag, Table color, String prefix, String prefix, String postfix) | Returns bool with result of setting style options for the specified tag type for the log. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#logstyle)
paste(Table parameters) | Returns Table of newly spawned objects that were pasted from the clipboard. Works with [copy(...)](#copy). | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#paste)
print(String message) | Prints a string into chat that only the host is able to see. Used for debugging scripts. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#print)
printToAll(String message, Table [color](#color)) | Returns Bool with the result of printing a message into the chat of all connected players. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#printtoall)
printToColor(String message,String [player_color](#color), Table [color](#color)) | Returns Bool with the result of printing a message to a specific Player. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#printtocolor)
removeNotebookTab(Int index) | Returns Bool with the result of removing a notebook tab. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#removenotebooktab)
sendExternalMessage(Table) | Returns Bool with the result of sending the table to your external script editor, most likely Atom. This is for custom editor functionality. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#sendexternalmessage)
setNotes(String notes) | Returns Bool with the result of replacing the text in the notes window with the string. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setnotes)
spawnObject(Table parameters) | Returns Object reference for the object spawned. View the [Spawnable Object](spawnableobject) page for Objects that can be spawned. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#spawnobject)
startLuaCoroutine(Object function_owner,String function_name) | Returns Bool with the result of starting a coroutine. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#startluacoroutine)
stringColorToRGB(String player_color) | Returns Table [Color](color) requivilent to the Player Color string. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#stringcolortorgb)



---

##Function Details

###addNotebookTab(...)

Returns Int of the index of the newly added notebook tab. If it failed to create a new tab, a -1 is returned instead. Indexes for notebook tabs begin at 0.

!!!info "addNotebookTab(Table parameters)"
	* **Table parameters**: A Table containing spawning parameters.
		* **parameters.title**: A String with the title for the new tab.
		* **parameters.body**: A String with text to place into the body of the new tab.
			* {>>Optional, defaults to an empty string<<}
		* **parameters.color**: A String with the [Player color](player) for the new tab's color.
			* {>>Optional, defaults to "Grey"<<}

``` Lua
parameters = {
	title = "New Tab",
	body = "Body text example.",
	color = "Grey"
}
addNotebookTab(parameters)
```

---


###broadcastToAll(...)

Returns Bool with result of printing an on-screen message to all Players.

!!!info "broadcastToAll(String message, Table [color](color))"
	* **String message**: A String of the message to display on-screen.
	* **Table color**: A Table containing the RGB color for the text.

``` Lua
msg = "Hello all."
rgb = {r=1, g=0, b=0}
broadcastToAll(msg, rgb)
```

---


###broadcastToColor(...)

Returns Bool with result of printing an on-screen message to a specified Player.

!!!info "broadcastToColor(String message, String [player_color](player), Table [color](color))"
	* **String message**: A String of the message to display on-screen.
	* **String player_color**: A String of the color of the Player who will receive the message.
	* **Table color**: A Table containing the RGB color for the text.

``` Lua
msg = "Hello White."
color = "White"
rgb = {r=1, g=0, b=0}
broadcastToColor(msg, color, rgb)
```

---


###clearPixelPaint()

Returns Bool with result of removing pixel paint from the instance.

``` Lua
clearPixelPaint()
```

---


###clearVectorPaint()

Returns Bool with result of removing vector paint from the instance.

``` Lua
clearPixelPaint()
```

---


###copy(...)

Returns Bool of result of copying a list of Objects the clipboard. Works with [paste(...)](#paste).

!!!info "copy(Table object_list)"
	* **Table object_list**: A Table of in-game objects to be copied.
		* {>>This is similar to highlighting the objects in-game and copying them.<<}

``` Lua
object_list = {
	getObjectFromGUID("######"),
	getObjectFromGUID("######"),
}
copy(object_list)
```

---


###destroyObject(...)

Returns Bool with the result of destroying an Object.

!!!info "destroyObject(Object obj)"
	* **Object obj**: The Object you wish to delete from the instance.

``` Lua
obj = getObjectFromGUID("######")
destroyObject(obj)
```

---


###editNotebookTab(...)

Returns Bool with the result of editing an existing Tab in the notebook. Indexes for notebook tabs begin at 0.

!!!info "editNotebookTab(Table parameters)"
	* **Table parameters**: A Table containing instructions for the notebook edit.
		* **parameters.index**: An Int of the index number for the tab.
		* **parameters.title**: A String of the title for the tab.
			* {>>Optional, defaults to the current title of the tab begin edited.<<}
		* **parameters.body**: A String of the body for the tab.
			* {>>Optional, defaults to the current body of the tab begin edited.<<}
		* **parameters.color**: A String of the Player color for who the tab belongs to.
			* {>>Optional, defaults to the current color of the tab begin edited.<<}

``` Lua
params = {
	index = 5,
	title = "Edited Title",
	body = "This tab was edited via script.",
	color = "Grey"
}
editNotebookTab(params)
```

---


###flipTable()

Returns Bool with the result of flipping the table.

``` Lua
flipTable()
```

---


###getAllObjects()

Returns Table of all spawned [Objects](object) in the game.

``` Lua
--Example Usage
objList = getAllObjects()
for _, obj in ipairs(objList) do
	print(obj.getName())
end
```
``` Lua
--Example Returned Table
objList = {object, object, object}
```

---


###getNotebookTabs()

Returns Table of all tabs in the notebook. Indexes for notebook tabs begin at 0.

``` Lua
--Example Usage
tabInfo = getNotebookTabs()
```
``` Lua
--Example Returned Table
{
	{index=0, title="", body="", color="Grey"},
	{index=1, title="", body="", color="Grey"},
	{index=2, title="", body="", color="Grey"},
}
```

---


###getNotes()

Returns String of the contents of the on-screen notes section.

``` Lua
print(getNotes())
```

---


###getObjectFromGUID(...)

Returns Object from GUID. Will return `nil` if it doesn't exist in-game.!!

!!!info "getObjectFromGUID(String guid)"
	* **String guid**: A String of the 6 character GUID of an object.
		* {>>GUID can be obtained by right clicking an object and going to Scripting.<<}
		* {>>In a script, it can be obtained from any Object by using .getGUID().<<}

``` Lua
obj = getObjectFromGUID("555555")
```

---


###getSeatedPlayers()

Returns Table of the colors of seated players.

!!!tip
	* Spectators ("Grey") are not returned.
	* DM seat ("Black") is not returned.
	* The order colors are returned in the table are in the same order as players joining the server.

``` Lua
--Example Usage
for _, v in ipairs(getSeatedPlayers()) do
	print(v)
end
```
``` Lua
--Example Returned Table
{"White", "Red", "Green"}
```

---


###log(...)

Returns Bool with result of printing information to the log. The log is a separate chat window which is visible to all players in the instance. It also automatically prints all data in a table if you input it as the Var.

!!!info "log(Var element, String tag, String label)"
	* **Var element**: The information you want placed into the log.
	* **String tag**: A String of text usable to group log messages by type. (See: [logStyle](logstyle))
		* {>>Optional, defaults to an empty String. Empty Strings are not displayed.<<}
	* **String label**: A String of text to be placed before the Var element is printed to the log.
		* {>>Optional, defaults to an empty String. Empty Strings are not displayed.<<}

``` Lua
log(getAllObjects(), "table", "All Objects:")
```

---


###logStyle(...)

Returns bool with result of setting style options for the specified tag type for the log. This can also be set in the system console with the "log_style_tag" command.

!!!info "logStyle(String tag, Table color, String prefix, String prefix, String postfix)"
	* **String tag_name**: A String of the log's tag.
	* **Table Color**: A Table of the RGB value of the text color.
		* {>>String color will also work. Example: "Red"<<}
	* **String prefix**: A String of text to place before the log entry of this tag type.
		* {>>Optional, defaults to an empty String. Empty Strings are not displayed.<<}
	* **String postfix**: A String of text to place after the log entry of this tag type.
		* {>>Optional, defaults to an empty String. Empty Strings are not displayed.<<}

``` Lua
function onLoad()
	logStyle("players", {0.5,0.5,0.5}, "", "End List")
	log(getSeatedPlayers(), "players")
end
```

---


###paste(...)

Returns Table of newly spawned objects that were pasted from the clipboard. Works with [copy(...)](#copy).

!!!info "paste(Table parameters)"
	* **Table parameters**: A Table containing instructions for the notebook edit.
		* **parameters.position**: A Table containing the position Vector of the first object to paste.
			* {>>Optional, defaults to {0, 3, 0}.<<}
		* **parameters.snap_to_grid**: A Bool which determines if snap-to-grid is active on the spawned item.
			* {>>Optional, defaults to false (off).<<}

``` Lua
params = {position = {5,5,0}, snap_to_grid = true}
paste(params)
```

---


###print(...)

Prints a string into chat that only the host is able to see. Used for debugging scripts.

!!!info "print(String message)"
	* **String message**: The String to be printed to chat.

``` Lua
function onLoad() print("Loading Complete") end
```

---


###printToAll(...)

Returns Bool with the result of printing a message into the chat of all connected players.

!!!info "printToAll(String message, Table [color](#color))"
	* **String message**: A String of the message to place into players chats.
	* **Table color**: A Table containing r/g/b values for the text's color.

``` Lua
printToAll("Hello World!", {r=1,g=0,b=0})
```

---


###printToColor(...)

Returns Bool with the result of printing a message to a specific Player.

!!!info "printToColor(String message, String [player_color](color), Table [color](color))"
	* **String message**: A String of the message to place into the player's chat.
	* **Straing player_color**: A String of the Player's color that will receive the message.
	* **Table color**: A Table containing r/g/b values for the text's color.

``` Lua
printToColor("Hello Red.", "Red", {r=1,g=0,b=0})
```

---


###removeNotebookTab(...)

Returns Bool with the result of removing a notebook tab. Notebook tab indexes begin at 0.

!!!info "removeNotebookTab(Int index)"
	* **Int index**: The Int of the index for the tab to remove.

``` Lua
removeNotebookTab(0)
```

---


###sendExternalMessage(...)

Returns Bool with the result of sending the table to your external script editor, most likely Atom. This is for custom editor functionality.

---


###setNotes(...)

Returns Bool with the result of replacing the text in the notes window with the string.

!!!info "setNotes(String notes)"
	* **String notes**: A String which will replace the contents of the notes area.

``` Lua
setNotes("This appears in the notes section")
```

---


###spawnObject(...)

Returns Object reference for the object spawned. View the [Spawnable Object](spawnableobject) page for Objects that can be spawned.

!!!tip
	Spawned Objects take a moment to be physically spawned into the game. The purpose of the callback functionality is to allow you to run additional actions after the Object has been initiated fully into the instance. It is also possible to add a delay using a [coroutine](#startluacoroutine).

!!!info "spawnObject(Table parameters)"
	* **Table parameters**: A Table of parameters used to determine how spawnObject will act.
		* **parameters.type**: A String of the [Spawnable Object](spawnableobject) type.
		* **parameters.position**: A Table Vector of the position to place Object.
			* {>>Optional, defaults to {x=0, y=3, z=0}.<<}
		* **parameters.rotation**: A Table Vector of the rotation of the Object.
			* {>>Optional, defaults to {x=0, y=0, z=0}<<}
		* **parameters.scale**: A Table Vector of the scale of the Object.
			* {>>Optional, defaults to {x=1, y=1, z=1}<<}
		* **parameters.sound**: A Bool for if the spawned Object noise is played.
			* {>>Optional, defaults to true.<<}
		* **parameters.snap_to_grid**: A Bool for snap-to-grid is active on the Object.
			* {>>Optional, defaults to false.<<}
		* **parameters.callback**: A String of the function name you want activated once the Object is initiated.
			* {>>Optional, no callback is triggered without it.<<}
			* {>>A callback function has 2 parameters, the Object spawned and, if used, the Table of params.<<}
		* **parameters.callback_owner**: An Object of what object has the callback function on it. Global is a valid target as well.
			* {>>Optional, defaults to Global. Serves no purpose if callback is not also used.<<}
		* **parameters.params**: A Table of data to send to the callback to use as parameters. See example.
			* {>>Optional, default is to not be used.<<}

If you are spawning a **custom Object**, you should call [setCustomObject](object#setcustomobject) immediately after spawnObject to set its custom properties.

``` Lua
function onLoad()
	futureName = "Spawned By Script!"
	spawnParams = {
		type = "rpg_BEAR",
		position       = {x=0, y=3, z=-5},
		rotation       = {x=0, y=90, z=0},
		scale          = {x=2, y=2, z=2},
		sound          = false,
		snap_to_grid   = true,
		callback       = "spawn_callback",
		callback_owner = Global,
		params         = {name = futureName}
	}
	spawnObject(spawnParams)
end

function spawn_callback(object_spawned, params)
	object_spawned.setName(params.name)
end
```

---


###startLuaCoroutine(...)

Returns Bool with the result of starting a coroutine. A coroutine is similar to a function, but has the unique ability to have its run paused until the next frame of the game using `coroutine.yield(0)`.

!!!Attention
	You MUST return a 1 at the end of any coroutine or it will throw an error.

!!!info "startLuaCoroutine(Object function_owner, String function_name)"
	* **Object function_owner**: The Object that the function being called is on. Global is a valid target.
	* **String function_name**: The String containing the name of the function being called as a coroutine.

``` Lua
function onLoad()
	startLuaCoroutine(Global, "print_coroutine")
end

--Prints a message, waits 250 frames, prints another message
function print_coroutine()
	print("Routine has Started")
	count = 0
	while count < 250 do
		count = count + 1
		coroutine.yield(0)
	end

	print("Routine has Finished")

	return 1
end
```

---


###stringColorToRGB(...)

Returns Table [Color](color) requivilent to the Player Color string.

!!!info "stringColorToRGB(String player_color)"
	* **String player_color** A String of a Player [Color](color).

``` Lua
printToAll("Blue message", stringColorToRGB("Blue"))
```

---
