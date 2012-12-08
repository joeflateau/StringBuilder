StringBuilder
=============

If you need to build large strings in Javascript, and are currently using string concatenation, consider using StringBuilder. StringBuilder is a simple array-backed string builder implementation for JavaScript.
StringBuilder can be used Standalone or as an AMD module.

Usage is as simple as:

```javascript
var sb = StringBuilder();
sb.append("foo");
sb.append("bar");
sb.toString(); // "foobar"
```
or with Require.js:
```javascript
define(['stringbuilder'], function(StringBuilder) {
    var sb = StringBuilder();
    sb.append("foo");
    sb.append("bar");
    sb.toString(); // "foobar"
});
```