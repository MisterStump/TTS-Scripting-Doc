Lighting, a static global class, is the in-game light of the map. It allows you to modify the lighting of the instance in the same way that the [in-game lighting menu](http://berserk-games.com/knowledgebase/lighting/) does. You call these functions like this: `Lighting.apply()`.

For more information on lighting in Unity, [refer to the Unity documentation](https://docs.unity3d.com/Manual/LightingOverview.html).

##Member Variables

Like [Object member variables](object#member-variables), Lighting has its own member variables. They are all numbers, and have specific valid ranges.

Variable | Description | Type
-- | -- | :--
ambient_type | The source of ambient light. 1 = background, 2 = gradient. | [<span class="tag int"></span>](typeandclass)
ambient_intensity | The strength of the ambient light. Range = 0 to 4. | [<span class="tag flo"></span>](typeandclass)
light_intensity | The strength of the directional light shining down in the scene. Range = 0 to 4. | [<span class="tag flo"></span>](typeandclass)
reflection_intensity | The strength of the reflections from the background. Range = 0 to 1. | [<span class="tag flo"></span>](typeandclass)

##Function Summary

###Functions

Function Name | Description | Return 
-- | -- | --:
apply() | Applies changes made to the lighting Class using these functions or member variables. | [<span class="ret boo"></span>](typeandclass)
getAmbientEquatorColor() | Returns Color Table of the gradient equator. Not used if `ambient_type = 1`. | [<span class="ret tab"></span>](typeandclass)
getAmbientGroundColor() | Returns Color Table of the gradient ground. Not used if `ambient_type = 1`. | [<span class="ret tab"></span>](typeandclass)
getAmbientSkyColor() | Returns Color Table of the gradient sky. Not used if `ambient_type = 1`. | [<span class="ret tab"></span>](typeandclass)
getLightColor() | Returns Color Table of the directional light, which shines straight down on the table. | [<span class="ret tab"></span>](typeandclass)
setAmbientEquatorColor([<span class="tag tab"></span>](typeandclass)&nbsp; Color) | Sets the color of the gradient equator. Not used if `ambient_type = 1`. | [<span class="ret boo"></span>](typeandclass)
setAmbientGroundColor([<span class="tag tab"></span>](typeandclass)&nbsp; Color) | Sets the color of the gradient ground. Not used if `ambient_type = 1`. | [<span class="ret boo"></span>](typeandclass)
setAmbientSkyColor([<span class="tag tab"></span>](typeandclass)&nbsp; Color) | Sets the color of the gradient sky. Not used if `ambient_type = 1`. | [<span class="ret boo"></span>](typeandclass)
setLightColor([<span class="tag tab"></span>](typeandclass)&nbsp; Color) | Sets the color of the directional light, which shines straight down on the table. | [<span class="ret boo"></span>](typeandclass)


---

##Function Details

###Example of making light red and bright

``` Lua
function onLoad()
    red = {r=1, g=0.6, b=0.6}
    Lighting.light_intensity = 2
    Lighting.setLightColor(red)
    Lighting.apply()
end
```
