The clock is an in-game Object which either tells time or acts as a timer. It has its own class, Clock, with functions/members associated with it. This allows you to manipulate the special properties of a clock. You call these functions like this: `self.Clock.pauseStart()`.<br>Clocks have 3 modes:

* **Current Time**: Displays the current time of the host.
* **Stopwatch**: Displays a running count up.
* **Timer**: Displays a countdown and beeps once complete.

##Member Variables

Like [Object member variables](object#member-variables), Clocks have their own member variable.

Variable | Description | Type
-- | -- | :--
paused | If the clock timer is paused. | Bool

---

##Function Summary

###Object Functions

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
getValue() | Returns Int of the time in stopwatch or timer mode. Clock mode returns 0. This function acts the same as [Object's getValue()](object#getvalue). | 
pauseStart() | Pauses/resumes a Clock in stopwatch or timer mode. Returns Bool. |
setValue(Int seconds) | Switches clock to timer and sets countdown time. This function acts the same as [Object's setValue()](object#setvalue). Returns Bool. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#setvalue)
showCurrentTime() | Switches clock to display current time. It will clear any stopwatch or timer. Returns Bool. |
startStopwatch() | Switches clock to stopwatch, setting time to 0. It will reset time if already in stopwatch mode. Returns Bool. |

---

##Function Details

###setValue(...)

Set the timer to display a number of seconds. This function acts the same as [Object's setValue()](object#setvalue). If the Clock is not in timer mode, it will be switched. If it is in timer mode, it will be paused and the remaining time will be changed. This will not start the countdown on its own.

> Returns Bool

!!!info "setValue(Int seconds)"
    * **Int seconds**: An Int of how many seconds will be counted down.
    
``` Lua
self.Clock.setValue(30)
```