# JSON Comments in Ashiva
Ashiva regards serialised

 - `object keys`
 - `array values`
 - `strings`
 
 as comments, **whenever they are prefixed with** `//`.

`//`-prefixed `object keys`, `array values` and `strings` may be used in standard JSON, without rendering the JSON invalid.

_____

## Comment Notation

### Comments in JSON 'Objects' in Ashiva

```
{
  "//01 Comment": "Developer notes here",
  "//02 Comment": "More developer notes here",
  "Name":  "Value"
}
```
Any `key-value` pair where the `key` matches the regular expression `^\/{2}` will be regarded as comments.


### Comments in JSON 'Arrays' in Ashiva

```
[
  "//01 Comment: Developer notes here",
  "//02 Comment: More developer notes here",
  "Serialised Array Value"
]
```

Any `array value` matching the regular expression `^\/{2}` will be regarded as comments.


### Comments in JSON 'Strings' in Ashiva

```
"//01 Comment: Developer notes here",
"//02 Comment: More developer notes here",
"Serialised String Value"
```

Any `string` matching the regular expression `^\/{2}` will be regarded as a comment.


### Comments in JSON 'Numbers', 'Booleans' and '`null`' in Ashiva

'Number', 'Boolean' and '`null`' values may not be commented.

Instead, they may be preceded by a `//`-prefixed '`String`' which is regarded as a comment.

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
