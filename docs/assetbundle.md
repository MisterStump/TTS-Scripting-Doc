AssetBundle is a special [Object](object) type that has access to assetbundle related functions like looping and trigger effects. Once you have a reference to an Object you can call these functions like this: `obj.AssetBundle.getLoopingEffects()`.

##Functions

Function Name | Description 
-- | -- 
getLoopingEffectIndex()  |  [Returns the index of the currently looping effect.](#getloopingeffectindex) 
getLoopingEffects()  |  [Returns a Table with the keys "index" and "name" for each looping effect.](#getloopingeffects) 
getTriggerEffects()  |  [Returns a Table with the keys "index" and "name" for each trigger effect.](#gettriggereffects)
playLoopingEffect(int index)  |  [Starts playing a looping effect. Index starts at 0.](#playloopingeffect)
playTriggerEffect(int index)  |  [Starts playing a trigger effect. Index starts at 0.](#playtriggereffect)


###Version 2
The first 2 are slightly different formatting examples. The other 3 copies are just to show what a collection of these looks like





##Function Details (Goes with Version 1)


???abstract "getLoopingEffectIndex()"
	###getLoopingEffectIndex()
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


???abstract "getLoopingEffects()"
	###getLoopingEffects()
	* **Return value**
		* table
	* **Function Description**
	    * Returns a Table with the keys "index" and "name" for each looping effect.
	* **Example**
		```Lua
			#Code block will go here
			print("String")
		```
		
###getTriggerEffects()

* **Return value**
	* table
* **Function Description**
	* Returns a Table with the keys "index" and "name" for each trigger effect.
* **Example**

```Lua
	#Code block will go here
	print("String")
```

###playLoopingEffect()

* **Return value**
	* *none*
* **Function Description**
	* Starts playing a looping effect.
* **Example**

```Lua
	#Code block will go here
	print("String")
```

!!!Note
	Indexes for AssetBundles start at 0!

###playTriggerEffect()

* **Return value**
	* *none*
* **Function Description**
	* Starts playing a trigger effect.
* **Example**

```Lua
	#Code block will go here
	print("String")
```

!!!Note
	Indexes for AssetBundles start at 0!