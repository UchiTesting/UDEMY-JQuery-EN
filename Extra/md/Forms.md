Forms
=====

##  Showing controls
We can determine if a block is shown depending on the state of any control.
One method can be by handling the relevant event on the determining control.
In that matter an interesting method avaible is `is()` which takes a CSS selector, a function or an object to match.
If the selector matches in the given element, it returns true. It returns false otherwise.
According to the official documentation event on sub elements are not taken in account.

## About dropdowns

They are likely managed with `change` event.

## About form submission

To have AJAX deal with submission of a form, we need to use the `submit` event from the actual form. Then we need a call to `preventDefault`.
```js
$("#formIdSelector").on('submit', function (event){
    event.preventDefault();
    // ... Do your thing here ...
})
```
We can get the value of the `action` attribute in the AJAX setup.
For the `data`, we can use `serialize()` method on the form to retrieve the entire form data.

```js
$("#formIdSelector").serialize();
```

Make sure to also validate on server side.