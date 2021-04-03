DOM Manipulation
================

> Related demo :
> - [DOM Manipulation](../demos/DomManipulation.html)

## Appending

```js
var html = "<div><p>New element to add</p></div>";
// One way
$("#container").append(html);

// Another way
$(html).appendTo("#container");
```

## Prepending

```js
var html = "<div><p>New element to add</p></div>";
// One way
$("#container").prepend(html);

// Another way
$(html).prependTo("#container");
```

## Before and After
```js
var html = "<div><p>New element to add</p></div>";

$("#container").find("#aReferenceElement").after(html);
$("#container").find("#aReferenceElement").before(html);
```

## Removing elements
Chain `remove()` to the relevant target.
Chain `empty()` to remove everything in the relevant element.

## Changing the content of a node
Use `text()` or `html()` to respectively write plain text or have the given text being interpreted as HTML.

Chain attr("newAttributeName", value) to write a new attribute. Omit the second parameter to read the value.