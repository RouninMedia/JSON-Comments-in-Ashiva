# JSON Comments in Ashiva
Ashiva allows for comments to be used in standard JSON, without rendering the JSON invalid.

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
Any `key-value` pair where the `key` matches the regular expression `^\/{2}` will be ignored.


### Comments in JSON 'Arrays' in Ashiva

```
[
  "//01 Comment: Developer notes here",
  "//02 Comment: More developer notes here",
  "Value"
]
```

Any `array value` matching the regular expression `^\/{2}` will be ignored.


### Comments in JSON 'Strings' in Ashiva

```
"//01 Comment: Developer notes here",
"//02 Comment: More developer notes here",
"Value"
```

Any `string` matching the regular expression `^\/{2}` will be ignored.


### Comments in JSON 'Numbers', 'Booleans' and '`null`' in Ashiva

'Number', 'Boolean' and '`null`' values may not be commented.

Instead, they may be preceded by a 'String' containing a comment.

______

##  Types of JSON Comment in Ashiva

JSON Comments in Ashiva may have _numbers_ and / or _names_.

**See:**

```
{
  "//01 Comment" : "Developer notes here"
},

[
  "//01 Comment: Developer notes here"
],

"//01 Comment: Developer notes here"
```

**versus:**

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
