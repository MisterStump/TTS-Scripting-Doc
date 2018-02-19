AssetBundle is a special [Object](object) type that has access to assetbundle related functions like looping and trigger effects. Once you have a reference to an Object you can call these functions like this: `obj.AssetBundle.getLoopingEffects()`.

##Function Summary

###Object Functions

Function Name | Description
-- | --
getLoopingEffectIndex()  |  [Returns the index of the currently looping effect.](#getloopingeffectindex)
getLoopingEffects()  |  [Returns a Table with the keys "index" and "name" for each looping effect.](#getloopingeffects)
getTriggerEffects()  |  [Returns a Table with the keys "index" and "name" for each trigger effect.](#gettriggereffects)
playLoopingEffect(int index)  |  [Starts playing a looping effect. Index starts at 0.](#playloopingeffect)
playTriggerEffect(int index)  |  [Starts playing a trigger effect. Index starts at 0.](#playtriggereffect)

---

##Function Details

###getLoopingEffectIndex()

Returns the `int` of the index of the currently looping effect.

```Lua
	index = self.AssetBundle.getLoopingEffectIndex()
```

---


###getLoopingEffects()

Returns a `table` with the keys "index" and "name" for each looping effect.

``` Lua
	#Example usage
	effectTable = self.AssetBundle.getLoopingEffects()
```
``` Lua
	#Example returned table
	{
		{index=0, name="Effect Name 1"},
		{index=1, name="Effect Name 2"},
	}
```

---


###getTriggerEffects()


Returns a `table` with the keys "index" and "name" for each trigger effect.

``` Lua
	#Example usage
	effectTable = self.AssetBundle.getTriggerEffects()
```
``` Lua
	#Example returned table
	{
		{index=0, name="Effect Name 1"},
		{index=1, name="Effect Name 2"},
	}
```

---


###playLoopingEffect(...)

Starts playing a looping effect. Indexes for AssetBundles start at 0.

!!!warning "playLoopingEffect(int index)"
	* **int index**: Numeric index for the effect.

``` Lua
	#Example usage
	self.AssetBundle.playLoopingEffect(0)
```

---
	

###playTriggerEffect(...)

Starts playing a trigger effect. Indexes for AssetBundles start at 0.

!!!warning "playTriggerEffect(int index)"
	* **int index**: Numeric index for the effect.


``` Lua
	#Example usage
	self.AssetBundle.playTriggerEffect(0)
```

---