# JSON Comments in Ashiva


Not really entirely happy with any of this...

Basically I want the comments to be _completely gone_ when the JSON files are being used and _completely there again_ when the files are being read.

This means I need:

 - documented version (with comments) :: this is what is edited and saved
 - active version (without comments) :: this is what is used
 
I **really** don't want to have two distinct folders, containing two individual files.

_____
_____
_____




Although the JSON data-exchange format does not allow for comments, in certain contexts, Ashiva recognises the `//`-prefix as an indication that what follows is a `comment`.

`//`-prefixed `object keys`, `array values` and `strings` may be used in standard JSON, without rendering that JSON invalid.

Ashiva regards all `//`-prefixed `object keys`, `array values` and `strings` as _comments within the JSON_.

_____

## Ashiva JSON Files which may employ Comments

- `ashivaModuleManifest`
- `ashivaCodesheet`
- `ashivaModuleLogic`
- `ashivaServersheet`
- `ashivaPageManifest`
- `ashivaGlobalManifest`

_____




_____

## Comment Notation

### Comments in JSON '`Object Keys`' in Ashiva

```
{
  "//01 Comment": "Developer notes here",
  "//02 Comment": "More developer notes here",
  "Name":  "Value"
}
```
Any `key-value` pair where the `key` matches the regular expression `^\/{2}` will be regarded as comments.


### Comments in JSON '`Array Values`' in Ashiva

```
[
  "//01 Comment: Developer notes here",
  "//02 Comment: More developer notes here",
  "Serialised Array Value"
]
```

Any `array value` matching the regular expression `^\/{2}` will be regarded as comments.


### Comments in JSON '`Strings`' in Ashiva

```
"//01 Comment: Developer notes here",
"//02 Comment: More developer notes here",
"Serialised String Value"
```

Any `string` matching the regular expression `^\/{2}` will be regarded as a comment.


### Comments in JSON '`Numbers`', '`Booleans`' and '`Null`' in Ashiva

'`Number`', '`Boolean`' and '`null`' values may not be commented.

But they may be preceded by a `//`-prefixed '`String`' which is regarded as a comment.

______

##  Categorising JSON Comments in Ashiva using alpha=numeric labels

The sole requirement to indicate a JSON Comment in Ashiva is a `//`-prefix.

This means JSON Comments in Ashiva may use _alpha-numeric labels_ rather than simply _numeric labels_.

**Compare:**

```
{
  "//01 Comment" : "Developer notes here"
},

[
  "//01 Comment: Developer notes here"
],

"//01 Comment: Developer notes here",
"//02 Comment: Developer notes here"
```

**with:**

```
{
  "//Explanation Comment" : "Developer notes here"
},

[
  "//Context Comment: Developer notes here"
],

"//ActionItem01 Comment: Developer notes here",
"//ActionItem02 Comment: Developer notes here"
```
