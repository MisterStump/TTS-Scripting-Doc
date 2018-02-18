AssetBundle is a special [Object](object) type that has access to assetbundle related functions like looping and trigger effects. Once you have a reference to an Object you can call these functions like this: `obj.AssetBundle.getLoopingEffects()`.

##Functions

###Version 1
Return | Function Name | Description 
-- | -- | -- 
int  |  getLoopingEffectIndex()  |  Returns the index of the currently looping effect. [**?**](#getloopingeffectindex) 
Table  |  getLoopingEffects()  |  Returns a Table with the keys "index" and "name" for each looping effect. 
Table  |  getTriggerEffects()  |  Returns a Table with the keys "index" and "name" for each trigger effect. [**?**](#gettriggereffects)
void  |  playLoopingEffect(int index)  |  Starts playing a looping effect. Index starts at 0. [**?**](#playloopingeffect)
void  |  playTriggerEffect(int index)  |  Starts playing a trigger effect. Index starts at 0. [**?**](#playtriggereffect)


###Version 2
The first 2 are slightly different formatting examples. The other 3 copies are just to show what a collection of these looks like

???abstract "getLoopingEffectIndex()"
	* **Return value**
		* number
	* **Function Description**
	    * Returns the index of the currently looping effect.
	* **Example**
		```Lua
			#Code block will go here
			print("String")
		```
	
	!!!Warning
		Special notes can go in here if needed

???abstract "getLoopingEffectIndex()"
	* {==Return value==}
		* number
	* {==Function Description==}
	    * Returns the index of the currently looping effect.
	* {==Example==}
		```Lua
			#Code block will go here
			print("String")
		```
	
	!!!Warning
		Special notes can go in here if needed

???abstract "getLoopingEffectIndex()"
	* **Return value**
		* number
	* **Function Description**
	    * Returns the index of the currently looping effect.
	* **Example**
		```Lua
			#Code block will go here
			print("String")
		```
	
	!!!Warning
		Special notes can go in here if needed
		
???abstract "getLoopingEffectIndex()"
	* **Return value**
		* number
	* **Function Description**
	    * Returns the index of the currently looping effect.
	* **Example**
		```Lua
			#Code block will go here
			print("String")
		```
	
	!!!Warning
		Special notes can go in here if needed

???abstract "getLoopingEffectIndex()"
	* **Return value**
		* number
	* **Function Description**
	    * Returns the index of the currently looping effect.
	* **Example**
		```Lua
			#Code block will go here
			print("String")
		```
	
	!!!Warning
		Special notes can go in here if needed



##Details (Goes with Version 1)

Details were going to go down down here for version 1.

###getLoopingEffectIndex
Function details and examples/warning/notes/etc

###getLoopingEffects
Function details and examples/warning/notes/etc

###getTriggerEffects
Function details and examples/warning/notes/etc

###playLoopingEffect
Function details and examples/warning/notes/etc

###playTriggerEffect
Function details and examples/warning/notes/etc