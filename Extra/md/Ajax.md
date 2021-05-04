AJAX
====

> Related demo :  
> [AJAX GET demo](../demos/AjaxGet.html)  
> [AJAX POST demo](../demos/AjaxPost.html)

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

## Posting data

POST does not need caching to true. the important bit is in it's setup, there is a data property to be set

```js
$.ajax('data.json', {
    type: 'POST',
    data: {
        data1: 235123,
        data2: "John Smith",
        data3: {
            temperature: 25,
            unit: "Celcius",
            windDirection: "NE",
            humidity: "50%",
            state: "Cloudy"
        }
    },
    dataType: 'json',
    contentType: 'application/json'

}).done(function (response) {
    // ... Do your thing here ...
});
```
The response will likely hold a JSON with expected data back.
In the following JSON object from a response:
```js
{
    "id": 78,
    "name": "John Smith",
    "age": 32
}
```

We could access the `name` property with `response.name`.