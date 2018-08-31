# Objects and Classes

## Objects belong to classes
[isinstance](https://docs.python.org/3/library/functions.html?highlight=isinstance#isinstance)

[type](https://docs.python.org/3/library/functions.html?highlight=isinstance#type)
* The `isinstance(object, classinfo)` function returns `True` if
the *object* is an instance of the *classinfo* argument.
* The `type(object)` function returns the type of an *object*

## Defining a new class
* A class is defined using the `class` keyword.
```
class Dog:
    def speak(self):
        print("Woof!")
```
* The `self` argument to the `speak` function is the instance
of the class. Python automatically passes the instance to
the method
* The `self` variable can have any name; but *self* is the
correct name **by convention**

## Class level variables
When a variable is defined inside a class definition, that variable is
available on every object of that class. This information is common
to all instances of the class.
```
class Dog:
    scientific_name = "Canis lupus familiaris"

    def speak(self):
        print("Woof!")
```

## Instance level variables
A class can have instance variables. Inside the class methods,
instance variables can be accessed using the `self` parameter of
the function with the dot operator.
```
class Dog:
    scientific_name = "Canis lupus familiaris"

    def speak(self):
        print("Woof!")

    def learn_name(self, name):
        self.name = name

    def hear(self, words):
        if self.name in words:
            self.speak()
```

## Initializers
Python offers a special method named `init` that will be called
whenever a class is constructed.

```
class Dog:
    scientific_name = "Canis lupus familiaris"

    def __init__(self, name):
        self.name = name
```

When constructing an instance of the `Dog` class, the
`name` must be specified.

`fido = Dog("Scooby")`

## Inheritance

A *subclass* is a class created from the blue-print of another class.
* The subclass *inherits* all of the behavior of the existing class.
* The subclass can change or *override* behavior of the *superclass*.

```
class Dog:
    scientific_name = "Canis lupus familiaris"

    def __init__(self, name):
        self.name = name

    def speak(self):
        print("Woof!")


class Husky(Dog):
    origin = "Siberia"

    def speak(self):
        print("RUFF!")
```

* The `isinstance` function will return `True` when provided an instance
of the subclass and the type of the subclass.
* The `isinstance` function will also return `True` when provided an
instance of the subclass the type of the superclass.
```
fido = Husky("Fido")
isinstance(fido, Husky)     # True
isinstance(fido, Dog)       # True
```

The `issubclass` function evaluates if one *type* is a subclass of
another *type*

```
issubclass(Husky, Dog)     # True
issubclass(Dog, Husky)     # False
```

The `pass` statement is used in functions that have no code to
execute. This is useful in class hierarchies when a subclass
does not have an execution responsibility for an inherited method.

## IS-A vs HAS-A
A technique used to design an inheritance hierarchy:
* `Husky` **IS A** `Dog` : this is logically true
* `Cat` **IS A** `Dog` : this is logically false
* `Car` **HAS A** `Radio` : this is logically true

## Using super
[Reference](https://docs.python.org/3/library/functions.html#super)
Returns a proxy object that delegates method calls to a parent or
sibling class of the type.

To call the `__init__` method of the superclass:
`super().__init__()`