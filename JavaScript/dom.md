# [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

The `DOM` is a tree structure that contains all of the elements,
the relationships between elements, and the properties of the
elements.

The `DOM` is not part of the JavaScript language, but rather
is constructed by the browser and is globally accessible by JavaScript
using the `document` object.

[DOM Specification](https://www.w3.org/standards/techs/dom#w3c_all)

---

## [Document.getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)

```
document.getElementById(idToFind);
```

Selects an element in the `DOM` by searching for it's ID tag.
`null` is returned if no matching element is found
in the document, otherwise a single element is returned.

---

## Select Multiple Elements at Once

### [document.getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName)

Returns an [HtmlCollection](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
of elements that match the **class** name provided.

### [document.getElementsByTagName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName)

Returns an [HtmlCollection](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)
of elements that match the **tag** name provided.

---

## Nodes, Elements and Interfaces

### [Node Interface](https://developer.mozilla.org/en-US/docs/Web/API/Node)

* `Node` = Class - an interface definition
* `node` = object - an instance of a Class

The `Node Interface` is the parent interface definition that every
`node` instance inherits.

### [Element Interface](https://developer.mozilla.org/en-US/docs/Web/API/Element)

The `Element Interface` is a descendant of the `Node Interface` and is
the most general base from which all objects in a `Document` inherit.

### [Interfaces](https://developer.mozilla.org/en-US/docs/Web/API)

---

## [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)

Selects elements with a selector; similar to CSS.

```
// find and return the element with an ID of "footer"
document.querySelector('#footer');

// find and return the first element with the class "footer"
document.querySelector('.footer');

// find and return the first <footer> element
document.querySelector('footer');
```

**CAUTION**
`querySelector()` only returns the *first* item it finds; even if there
are multiple matches.

---

## [querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)

Returns a static [NodeList](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
of the document's elements that match the specified selectors.

```
// find and return a list of elements with the class "footer"
document.querySelectorAll('.footer');

// find and return a list of <footer> elements
document.querySelectorAll('footer');
```