The static global JSON class provides the ability to encode/decode data into JSON strings. This is largely used by the [onSave()](event#onsave) event function, but has other potential applications as well. The JSON class can be used on any String, Int, Float or Table. You call these functions like this: `JSON.encode(...)`.

!!!warning
    This class **does not** work with Object references. Use the Object's GUID instead.



##Function Summary

###Object Functions

Function Name | Description | <i class="material-icons" style="line-height:90%;">info_outline</i>
-- | -- | --:
decode(String json_string) | Returns Var from the decoded String. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#decode)
encode(Var data) | Returns String of the encoded data from a number, String or Table. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#encode)
encode_pretty(Var data) | Returns String of the encoded data from a number, String or Table. This version is slightly less efficient than encode(...) but is easier to read. | [<i class="material-icons" style="line-height:150%;">info_outline</i>](#encode_pretty)

---


##Function Details

###decode(...)

Returns Var from the decoded string.

!!!info "decode(String json_string)"
    * **String json_string**: A String that is decoded, generally created by encode(...) or encode_pretty(...).

``` Lua
coded = JSON.encode("Test")
print(coded) --Prints "Test"
decoded = JSON.decode(coded)
print(decoded) --Prints Test
```

---


###encode(...)

Returns String of the encoded data from a number, String or Table.

!!!info "encode(Var data)"
    * **Var data**: A Var, either String, Int, Float or Table, to encode as a string.

---


###encode_pretty(...)

Returns String of the encoded data from a number, String or Table. This version is slightly less efficient than encode(...) but is easier to read.

!!!info "encode_pretty(Var data)"
    * **Var data**: A Var, either String, Int, Float or Table, to encode as a string.
