An RPGFigurine is an in-game Object of a figurine with built-in animations. It has its own class, RPGFigurine, with functions associated with it. This allows you to manipulate the special properties of these figurines.

##Function Summary

###Object Functions
These functions are called like this: `self.RPGFigurine.attack()`.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
attack() | Plays a random attack animation. Returns Bool. |
changeMode() | Changes the figurine's current mode. What the mode represents is based on the figurine. Returns Bool. |
die() | Plays the death animation or causes it to return to life. Returns Bool. |

###Event Functions
These functions are called by the game whenever a figurine attacks or is attacked. See details for example usage.

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
onAttack(Table hit_list) | Activates when an attack is performed by an identified RPGFigurine Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#onattack)
onHit(Object attacker) | Activates when an attack is performed on this RPGFigurine Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#onattack)





---

##Function Details

###Event Function Details

####onAttack(...)

Activates when an attack is performed by an identified RPGFigurine Object. An attack is triggered via the context menu or pressing the appropriate number key. If another RPGFigurine is within its attack arch, then the function will be triggered with the figurine hit passed as a parameter.

!!!info "onAttack(Table hit_list)"
    * **Table hit_list**: A Table of Object references for RPGFigurines within the reach of the attack.

``` Lua
--Monitoring and announcing a cyclops attacks
function onLoad()
    cyclops = getObjectFromGUID("aaa111")
    
    function cyclops.RPGFigurine.onAttack(hit_list)
        for _, v in ipairs(hit_list) do
            print(v.getName() .. " was hit!")
        end
    end
end
```

---


####onHit(...)

Activates when an attack is performed on this RPGFigurine Object. An attack is triggered via the context menu or pressing the appropriate number key. If this RPGFigurine is within the attack radius, this function is triggered, passing a parameter of the Object which attacked.

!!!info "onHit(Object attacker)"
    * **Object attacker**: An Object reference of the RPGFigurine attacking the indicated RPGFigurine.

``` Lua
--Monitoring and announcing a cyclops being hit
function onLoad()
    cyclops = getObjectFromGUID("aaa111")
    
    function cyclops.RPGFigurine.onHit(attacker)
        print(attacker.getName() .. " attacked the Cyclops!")
    end
end
```
