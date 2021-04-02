DOM Traversing
==============

## find()
```js
$("#animals .creature");
```

is equivalent to

```js
$("#animals").find(".creature");
```

If no selector is provided into `find()`, returns all the descendants.

## children()
```js
$("#animals > .creature");
```

is equivalent to

```js
$("#animals").children(".creature");
```

Consider the direct children only. Can filter further with selector. Told to be more efficient in performance than classical CSS selector.

## first(), last(), next(), prev()

As their name implies. Methods `first()` and `last()` take no parameter. Methods `next()` and `prev()` consider the direct sibling in the respective direction they look for any element. They may take a selector as parameter. In such case the selector acts as a filter and may return an empty object.

## parent(), parents()

`parent()` return the direct parent only.
`parents()` return all the above hierarchy.
They both can take a selector as parameter to narrow down the search.

## closest()
Returns the closest element starting from the current element itself.
In comparison to `parent()` and `parents()` exclude that self element.