These are a loose collection of functions which can be used to perform a variety of actions within Tabletop Simulator. Some of them are used in almost every script.

##Function Summary

###Global Management Functions

Function Name | Description
-- | --
addNotebookTab(Table parameters) | Returns Int of the index of the newly added notebook tab. [&#8263;](#addnotebooktab)
broadcastToAll(String message, Table [color](color)) | Returns Bool with result of printing an on-screen message to all Players. [&#8263;](#broadcasttoall)
broadcastToColor<br>(String message, String [player_color](player), Table [color](color)) | Returns Bool with result of printing an on-screen message to a specified Player. [&#8263;](#broadcasttocolor)
clearPixelPaint() | Returns Bool with result of removing pixel paint from the instance. [&#8263;](#clearpixelpaint)
clearVectorPaint() | Returns Bool with result of removing vector paint from the instance. [&#8263;](#clearvectorpaint)
copy(Table object_list) | Returns Bool of result of copying a list of Objects the clipboard. Works with [paste(...)](#paste). [&#8263;](#copy)
destroyObject(Object obj) | Returns Bool with the result of destroying an Object. [&#8263;](#destroyobject)
editNotebookTab(Table parameters) | Returns Bool with the result of editing an existing Tab in the notebook. [&#8263;](#editnotebooktab)
flipTable() | Returns Bool with the result of flipping the table. [&#8263;](#fliptable)
getAllObjects() | Returns Table of all spawned [Objects](object) in the game. [&#8263;](#getallobjects)
getNotebookTabs() | Returns Table of all tabs in the notebook. [&#8263;](#getnotebooktabs)
getNotes() | Returns String of the contents of the on-screen notes section. [&#8263;](#getnotes)
getObjectFromGUID(String guid) | Returns Object from GUID. Will return `nil` if it doesn't exist in-game. [&#8263;](#getobjectfromguid)
getSeatedPlayers() | Returns Table of the colors of seated players. [&#8263;](#getseatedplayers)
log(Var element, String tag, String label) | Returns Bool with result of printing information to the log. (Shortcut: ~)  [&#8263;](#log)
logStyle(String tag, Table color,<br> String prefix, String prefix, String postfix) | Returns bool with result of setting style options for the specified tag type for the log. [&#8263;](#logstyle)
paste(Table parameters) | Returns Table of newly spawned objects that were pasted from the clipboard. Works with [copy(...)](#copy). [&#8263;](#paste)
print(String message) | Prints a string into chat that only the host is able to see. Used for debugging scripts. [&#8263;](#print)





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



























