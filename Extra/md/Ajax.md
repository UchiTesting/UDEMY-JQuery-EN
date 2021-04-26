AJAX
====

> Related demo :
> [Ajax demo](../demos/AjaxGet.html)

`$.ajax(url, {})` takes a second parameter that is an object with a set of properties.
Available settings [@jQuery official doc](https://api.jquery.com/jquery.ajax/#jQuery-ajax-settings)

## Loading a file

`$.ajax(url)`
`done(function (response) {})` is a method that can be chained to `ajax()` and deals with successfully completed request.
`fail(function (request, errorType, errorMessage){})`. The default error types are `timeout`,`error`,`abort`,`parseerror`,
`always(function () {})` is a chainable method that happens no matter the result of the query.

## Executing code before and after the call

`$.ajax(url, {})` takes a second parameter that is an object.

It contains properties:
- `beforeSend`: function to be executed before call.
- ``:


## Reading JSON

The default HTTP method is `GET`. It asks little setup along with the URL as shown in the snippet bellow:

```js
$.ajax('data.json', {
    dataType: 'json',
    contentType: 'application/json',
    cache: false

});
```

For a collection of elements, there is a `each(dataSource, function (index,element){...})` method to treat each item.
See the demo code for an example.