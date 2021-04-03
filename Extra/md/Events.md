Working with events
===================


## The basic method: on()

> Signature: `on("eventAsString", [delegateSelector], eventHandler)`

This method takes an event name as string and a callback function. It can also take an object containing sub-objects with the same format to handle multiple events

    > We apply the event to the `button` elements directly.
```js
$("button").on('click',function () { 
    //... Do your thing here ...
});
```


> Optionally we can provide a second parameter in order to apply event delegation.
```js
$("#container").on('click','button',function () { 
    //... Do your thing here ...
});
```

With event delegation we reference a container being a parent of the buttons, then in the 2nd parameter we precise what elements shall have an event handler.

> Event delegation is a preferred method, especially if there is a chance, the target elements are not loaded with the page.  
> It also comes in handy when we would like to isolate the event handling to buttons which are only in a specific container.

> Multiple events passed
```js
$( "div.test" ).on({
  click: function() {
    $( this ).toggleClass( "active" );
  }, mouseenter: function() {
    $( this ).addClass( "inside" );
  }, mouseleave: function() {
    $( this ).removeClass( "inside" );
  }
});
```

## Click event

This method is a shorthand for `on("click, eventHandler)`.
> signature: `click([optionalData],handler)`

## Some common events 

| Event | Description |
|---|---|
| click | Handles the click event. |
| change | Handles the change event. |
| keydown | A key has been pressed. |
| keyup | A key has been released. |

More on [Events @jquery official doc](https://api.jquery.com/category/events/).


## Select Dropdowns

We usually work on a parent. See this HTML code.
```html
<div id="#example" class="container">
    <select id="places">
        <option value="">Pick your destination</option>
        <option value="metz" data-price="100">Metz</option>
        <option value="krakow" data-price="500" selected>Kraków</option>
        <option value="luxembourg" data-price="300">Luxembourg</option>
    <select>
</div>
```

On simple cases if we just want to get the value from the dropdown, it is enough to call the `val()` method to retrieve it.

```js
$("#example").on('click', 'button',function () {
    $("#places").val();
});
```

If we need more information, from the data attributes for instance, we need to work with the `<option>` elements.

```js
$("#example").on('click', 'button', function () {
    var selected = $("#places option:selected");
    var value = selected.val();
    // Generic attribute method to get the price.
    // var price = selected.attr("data-price");
    // Specific data attribute method to get the price.
    var price = data("price"); 

    // ... Do your thing here ...
});
```
In the case of change event:
```js
$("#example").on('change', 'select',function () {
    var selected = $(this).find("option:selected");
    var value = selected.val();
    var price = data("price"); 

    // ... Do your thing here ...
});
```

## Preventing from the default behaviour

When we apply an event to some HTML elements, we keep their default behaviour. For instance if we add an event handler to show a modal when clicking on an `<a>` link, the modal may be displayed but, provided href is given an url, we still be redirected to that url.
To avoid this, simply use the `preventDefault()` method.

```js
$("#example").on('click', 'a',function (e) {
    e.preventDefault();

    // ... Do your thing here ...
});
```

## Event propagation
Say we have several `<div>` nested in each other and the deepest one is being applied a click event handler. Because that `<div>` is within bigger `<div>` elements, they share a common surface. It is like clicking on that smaller div still clicks on bigger `<div>` elements. In other words the click event on the "smaller" `div` will propagate to the bigger `div` ancestors.

This is very likely an unwanted behaviour and the solution is simply to use the `stopPropagation()` method.

Former versions of jQuery returned `false` in the event handler to get the same result.

```js
$("#example").on('click', 'a',function (e) {
    e.preventDefault();
    e.stopPropagation();

    // ... Do your thing here ...
});
```
