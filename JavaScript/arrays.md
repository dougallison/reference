# [Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

## General
* Arrays store *multiple* values into a *single* data structure.
* Arrays are create by listing comma separated values between
square brackets `[]`
* Arrays can hold any data type, and each element in the array
can be a different data type.
* Arrays can hold other arrays

```
var stuff = [1, "hello", 2, true, 3, [], "world", undefined];
```

## Properties and Methods

* Index starts at position zero.
* The `length` property returns the length of an array
* The `push()` method adds elements to the *end of an array*
* The `pop()` method removes an element from the *end of an array*
    * The `pop()` method returns the element that has been removed
* The `splice()` method lets you specify the index location to add
new elements, as well as the number of elements to delete (if any)
* The `reverse()` method reverses the elements in the string
* The `sort()` method sorts an array


## foreach()
The `foreach()` method iterates over an array and manipulates each
element in the array with a function.

```
var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
    19, 300, 3775, 299, 36, 209, 148, 169, 299,
    6, 109, 20, 58, 139, 59, 3, 1, 139
];

test.forEach(function(element, index, array) {
   if(element % 3 === 0) {
       array[index] = element + 100;
   }
});
```

## map()
The `map()` method creates a new array with the results of calling
a provided function on every element in the calling array.

```
var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
    19, 300, 3775, 299, 36, 209, 148, 169, 299,
    6, 109, 20, 58, 139, 59, 3, 1, 139
];

var plus15Percent = test.map(function(num) {
   return Number((num * 1.15).toFixed(2));
});
```