# Modifying Content With JavaScript

## [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)

All elements that inherit from the `Element` interface have an
`.innerHTML` property. This property returns a `string` containing
the markup of the element's content. Use this to:

* get an element's (and its descendants) HTML content
* set an element's HTML content

## [Element.outerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML)

Returns a `string` containing the HTML element itself, as well
as *its children*.

---

## [Node.textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)

The `.textContent` property contains the text of an element
(sans any  markup). This property can be used to:

* **set** the text content of an element and its descendants
* **get** the text content of an element and its descendants

If html markup is *set* using this property, it will render as plain
text; it will be be rendered as html. Use the `.innerHTML` property
to add html markup and have it rendered correctly.

---

## [Node.innerText](https://developer.mozilla.org/en-US/docs/Web/API/Node/innerText)

Represents the *rendered* text content of a node and its descendants.
Any styling applied to the text will be applied; the text is
returned as it would be seen visually.

If CSS is used to hide any text inside the element, `.innerText` will
**not** contain the hidden text. Conversely, `.textContent` **would** contain
the hidden text.

---

# Creating New Content with JavaScript

## [Document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)

```
var element = document.createElement(tagName[, options]);
```

Creates the HTML element specified by tagName, or an `HTMLUnknownElement`
if `tagname` isn't recognized.

This function only creates the element, it does not add it to the `DOM`.
To add the element to the `DOM`, use the `.appendChild()` function.

---

## [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)

```
element.appendChild(aChild);
```

Adds a node to the end of the list of children of a specified parent node.

**NOTE**: if an element *already exists* in the `DOM` and this element
is passed to `.appendChild()`, the `.appendChild()` function will
*move it* rather than duplicating it.

---

## [Document.createTextNode()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode)

```
var text = document.createTextNode(data);
```

Creates a new Text node. This is an alternative to using
the `.textContent` property but requires more steps.

---

## [Element.insertAdjacentHTML()]()

Inserts the specified `text` into the `DOM` tree at the specified
`position`.


```
element.insertAdjacentHTML(position, text);
```

The `position` argument allows the new element to be inserted in one
of four different locations:
* `beforebegin`: inserts `text` as a previous sibling
* `afterbegin`: inserts `text` as the first child
* `beforeend`: inserts `text` as the last child
* `afterend`: inserts `text` as a following sibling

```
<!-- beforebegin -->
<p>
    <!-- afterbegin -->
    Existing text/HTML content
    <!-- beforeend -->
</p>
<!-- afterend -->
```

---

# Remove Page Content

## [Node.removeChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)

Removes a child node from the `DOM` and returns the removed node.

```
var deletedNode = node.removeChild(nodeToBeDeleted);
```

* `node` is the parent node of `nodeToBeDeleted`
* `deletedNode === nodeToBeDeleted`

This function throws an exception if `nodeToBeDeleted` is not a
child of `node`.

Each element has a `parentElement` that can be exploited to remove
the element in question:

```
const mainHeading = document.querySelector('h1');

mainHeading.parentElement.removeChild(mainHeading);
```

---

## [ChildNode.remove()](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove)

Removes the object from the tree it belongs to (without having to
first select the parent).

```
node.remove();
```

---

# Style Page Content

## [HTMLElement.sytle](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)

* Gets/sets the **inline** style of an elment.
* The `style` property has the same (and highest) priority in the CSS
cascade as an inline style declaration set via the `style` attribute.
* Set works on one CSS property at a time; multiple lines
are required to set multiple properties.

The `.style.cssText` property allows setting multiple CSS styles
at once. Write the CSS styles just as they would be in a stylesheet.

## [HTMLElement.setAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)

Sets the complete inline style for the element by overriding the existing
inline styles.

This function can be used to set **any** attribute for an element,
not just CSS.

```
// Set multiple styles in a single statement
elt.style.cssText = "color: blue; border: 1px solid black";
// Or
elt.setAttribute("style", "color:red; border: 1px solid blue;");


elt.style.color = "blue"; // Set specific style while leaving other inline style values untouched
```

## [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)

* A read-only property that returns a live `DOMTokenList` collection of the
class attributes of the element.
* Returns all of the classes applied to an element in single *space
separated* `string`.

```
const mainHeading = document.querySelector('#main-heading');

// store the list of classes in a variable
const listOfClasses = mainHeading.classList;

// logs the array
console.log(listOfClasses);
```

The `.classList` property has it's own properties:

* `.add()` - to add a class ot the list
* `.remove()` - to remove a class from the list
* `.toggle()` - to add the class if it doesn't exist, or remove it
from the list if it does already exist
* `.contains()` - returns a boolean that indicates the class exists
in the list or not