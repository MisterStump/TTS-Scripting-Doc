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
onAttack(Table hit_list) | Activates when an attack is performed by an identified figurine Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#onattack)
onHit(Object attacker) | Activates when an attack is performed on this Object. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#onattack)





---

##Function Details

###Event Function Details

####onAttack(Table hit_list)

Activates when an attack is performed by an identified figurine Object.
