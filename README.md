StringBuilder
=============

If you build large strings in Javascript, you may want to consider using StringBuilder.


Typically you would build strings like this:

```javascript
var myString = "";
for (var i = 0; i < 1000; i++) {
    myString += i.toString();
}
```

The problem with that is, it uses a lot of memory. A *lot* of memory. After the 3rd iteration the following values will be in memory:

    ""
    "1"
    "12"
    "123"
    
Enter, the string builder:

```javascript
var myStringBuilder = StringBuilder();
for (var i = 0; i < 1000; i++) {
    myStringBuilder.append(i.toString());
}
```

After the 3rd iteration, only these values are in memory:

    "1"
    "2"
    "3"
    
This is a very simple example, imagine looping through a 2d array to build an html table. Memory balloons very quickly which leads to excessive Garbage Collection and poor performance using the concatenation method.

    
StringBuilder can also be used as an AMD module with Require.js:
```javascript
define(['stringbuilder'], function(StringBuilder) {
    var sb = StringBuilder();
    sb.append("foo");
    sb.append("bar");
    sb.toString(); // "foobar"
});
```