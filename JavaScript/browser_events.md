# Browser Events

## Events

* [MDN Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)
* [Dev Tools Monitor Events](https://developers.google.com/web/tools/chrome-devtools/console/events#monitor_events)

## [EventTarget](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

The `EventTarget` interface is implemented by objects that can receive
events and may have listeners for them

`EventTarget` <-- `Node` <-- `Element`

The `EventTarget` interface is inherited by all nodes and elements.
This *includes* the **document** object and *any* **DOM** object.

The `EventTarget` interface defines 3 functions:

1. `.addEventListener()`
1. `.removeEventListener()`
1. `.dispatchEvent()`

---

## [EventTarget.addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)

```
target.addEventListener(type, listener[, options]);
```

The `.addEventListener()` function has 3 arguments:

1. `type`: case-sensitive string representing the type of event to
listen for
1. `listener`: a function to run when the event occurs
1. `options`: specifies characteristics about the event listener

---

## [EventTarget.removeEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)

```
target.removeEventListener(type, listener[, options]);
```

The `removeEventListener()` function removes a previously registered
event listener from the target object.

The `removeEventListener()` function has 3 arguments:

1. `type`: case-sensitive string representing the type of event to
listen for
1. `listener`: a function to run when the event occurs
1. `options`: specifies characteristics about the event listener

**IMPORTANT**

When removing an event listener, the `listener` argument must be
the exact same function that was added using the `addEventListener()`
function.

Because of this, when calling `addEventListener()` it is good practice
to use a named function (instead of an *inline* function) as the
`listener` argument.

---

## [Event Phases](https://www.w3.org/TR/DOM-Level-3-Events/#event-flow)

3 different phased during the lifecycle of an event:

1. the *capturing* phase
1. the *at target* phase
1. the *bubbling* phase

When an event occurs, the *capturing* phase starts at the parent
object and traverses down to the child until the *target* is reached
and the event fires. After the event fires, the event *bubbles* back
up to the parent object.

If the `.addEventListener()` function is invoked with only 2
arguments (or when the 3rd argument is `false`), the event firing
method uses the bubbling phase. When the third argument is `true`,
the event firing method uses the capturing phase.

---

## The Event Object

```
document.addEventListener('click', function (event) {
   console.log('The document was clicked');
});
```

When an event occurs, the browser includes an **event object** that
contains information about the event.

---

## The Default Action

The `event` object passed into an event listener function has a
`preventDefault()` method that can be called to prevent the default
action for the object from occurring.

---

## Event Delegation

The `event` object passed into an event listener function has a
`.target` property that references the *target* of the event. This
can be examined during the *capturing* or *bubbling* phases to
determine which object was the actual target of the event.

> The idea is that if we have a lot of elements handled in a similar way,
> then instead of assigning a handler to each of them – we put a
> single handler on their common ancestor.
>
> In the handler we get event.target, see where the event actually
> happened and handle it.
>
> [Event Delegation](https://javascript.info/event-delegation)

> -----

> Event delegation allows you to avoid adding event listeners to
> specific nodes; instead, the event listener is added to one
> parent. That event listener analyzes bubbled events to find a
> match on child elements.
>
> [How Event Delegation Works](https://davidwalsh.name/event-delegate)

---

## [DOMContentLoaded](https://developer.mozilla.org/en-US/docs/Web/Events/DOMContentLoaded)

When the browser is parsing the HTML into DOM tokens and reaches a
`<script>` tag, it must wait to download the script file and execute
that JavaScript code. *This is why the placement of the JavaScript
tag matters*.

When the `DOM` has been fully loaded, the browser will fire an event
called `DOMContentLoaded()`. The `target` for the `DOMContentLoaded()`
event is the *document*.

The `DOMContentLoaded()` event can be used to add event listeners
to other objects on the page; objects that need to be loaded into
the DOM before the event listener can be added.

```
document.addEventListener('DOMContentLoaded', function () {
    document.querySelector('footer').style.backgroundColor = 'purple';
});
```
