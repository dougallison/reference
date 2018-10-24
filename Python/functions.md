# Functions

## Parameters

* Parameter values are passed by object reference, not by object value
    * Functions can modify mutable arguments
    * Reference is lost if a formal function argument is rebound
        * To change a mutable argument, replace its *contents*
* Return statements pass by object reference
* Python supports named parameter invocation:

```
def add_numbers(x, y):
    return x + y


print(add_numbers(2, y = 2))
```

* Python supports default values for function parameters. 
    * The default values are *evaluated when def is evaluated*. This can cause problems when mutable values like *date-time* values are used for the default: the default value will only be evaluated once, not every time the function is called. 
    * Default values should be immutable constants

```
def add_item(item, list_items=None):
    if list_items is None:
        list_items = []

    list_items.append(item)
    return list_items
```