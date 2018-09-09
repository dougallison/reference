# [Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

Objects encapsulate related data and functionality into one single
container.

## Object-literal notation

* An *key* (representing a **property** or **method** name) and
its *value* are separated by a colon
* The `key: value` *pairs* are separated from each other by *commas*
* The object definition is wrapped in curly braces `{ }`
* An object's properties can be accessed using *dot notation* or
*bracket notation*
    * `object.propertyName`
    * `object["propertyName"]`

```
var something = {
	name: "something's name",
	doSomething: function() { return "Somthing has been done!"; },
	propertyX: "x"
};
```
