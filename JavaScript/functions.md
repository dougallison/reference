# Functions

## Hoisting
* Function declarations and variable declarations are hoisted to
the top of the current scope
    * This happens at time of interpretation
* Variable assignments are **not** hoisted
* Function expressions are **not** hoisted - they involve variable
assignment and only variable declarations are hoisted

---

## Function Declarations
A function declaration defines a stand-alone function:
```
function catSays(max) {
	// code goes here
};
```

---

## Function Expressions
A function can be stored inside of a variable:

```
// This is an anonymous function, it does not have a name.

var doSomething = function(y) {
  return y + 1;
};
```

A function expression can also be named:

```
var doSomething = function addOne(y) {
  return y + 1;
};
```

A function expression can be inline (this is very common when you
know the inline function won't need to be used anywhere else):

```
function movies(messageFunction, name) {
	messageFunction(name);
}

movies(function displayFavorite(movieName) {
	console.log("My favorite move is " + movieName);
	}, "My favorite movie");
```

---

## Functions as parameters
When a function is stored inside of a variable, it becomes
simple to pass the function *into* another function. A function
that is passed into another function is called a **callback**.

```
function helloCat(callbackFunc) {
	return "Hello " + callbackFunc(3);
}

helloCat(catSays);
```
