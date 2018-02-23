These are a loose collection of functions which can be used to perform general actions within Tabletop Simulator.

###Global Management Functions

Function Name | Description
-- | --
addNotebookTab(Table parameters) | Returns Int of the index of the newly added notebook tab. [&#8263;](#addnotebooktab)
broadcastToAll(String message, Table [color](color)) | Returns Bool with result of printing an on-screen message to all Players. [&#8263;](#broadcasttoall)
broadcastToColor<br>(String message, String [player_color](player), Table [color](color)) | Returns Bool with result of printing an on-screen message to a specified Player. [&#8263;](#broadcasttocolor)
clearPixelPaint() | Returns Bool with result of removing pixel paint from the instance. [&#8263;](#clearpixelpaint)
clearVectorPaint() | Returns Bool with result of removing vector paint from the instance. [&#8263;](#clearvectorpaint)
copy(Table object_list) | Returns Bool with result of copying a list of Objects. [&#8263;](#copy)
destroyObject(Object obj) | Returns Bool with the result of destroying an Object. [&#8263;](#destroyobject)







---

##Function Details

###addNotebookTab(...)

Returns Int of the index of the newly added notebook tab. If it failed to create a new tab, a -1 is returned instead.

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

Returns Bool with result of copying a list of Objects.

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



























