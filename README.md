# JSON Comments in Ashiva
Ashiva allows for comments to be used in standard JSON, without rendering the JSON invalid.

## Comments in JSON 'Objects' in Ashiva

```
{
  "//01": "Comment 1",
  "//02": "Comment 2",
  "Name":  "Value"
}
```
Any `key-value` pair where the `key` matches the regular expression `^\/{2}\d{2}$` will be ignored.


## Comments in JSON 'Arrays' in Ashiva

```
[
  "//01 Comment 1",
  "//02 Comment 2",
  "Value"
]
```

Any `array value` matching the regular expression `^\/{2}\d{2}\s` will be ignored.


## Comments in JSON 'Strings' in Ashiva

```
"//01 Comment 1",
"//02 Comment 2"
```

Any `string` matching the regular expression `^\/{2}\d{2}\s` will be ignored.


## Comments in JSON 'Numbers', 'Booleans' and '`null`' in Ashiva

'Number', 'Boolean' and '`null`' values may not be commented.
Instead, they may be preceded by a 'String' value containing a comment.
