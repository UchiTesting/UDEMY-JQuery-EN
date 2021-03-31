Selection
=========

> Related demo :
> - [Selectors and Multiple selection](../demos/SelectorMultiple.html)

## Basics of selection
HTML pages describe the structure and content of a document. It is hierarchical and looks like a tree. This is what we call the DOM (Document Object Model).

jQuery is heavily relying on selecting elements in the page in order to apply a variety of operations. 
The `$` symbol represents an access to jQuery functionality.
It can ask for a css selector in parenthesis.

For instance:

```js
$("#my .css.selector")
```

The above snippet would apply to a code that looks like this:

```html
<div id="my">
    <span class="css selector"></span>
</div>
```

The target would be the `<span>` element for it has an ancestor with id `my` and have both `css` and `selector` classes applied.

## CSS selectors in a nutshell

Basically:
- id attributes are prefixed with `#` i.e. `myId` is `#myId`.
- CSS classes are prefixed with `.` i.e. `myClass` is `.myClass`.
- Tags are as is i.e. `<p>` is simply `p`.
- Attritute are into square brackets `[ ]` i.e. `[attribute='value']` or simply `[attribute]` should attribute minimization be allowed.

Elements related to the same element are chained without space.
Just as in the example given earlier `.css.selector` refers to an element that has both `css` and `selector` classes.  
While `.css .selector` could apply to a DOM like such:

```html
<div class="css">
    <div class="selector"></div>
</div>
```

|Selector|Code| Description |
|---|---|---|
| parent > directChild | Sample 1 | Selects the direct child to the parent. |
| ancestor descendant | Sample 2 | Selects the all the `descendant` nodes that are under the `ancestor` node. |
| prev + next | Sample 3 | Selects the occurence of `next` right after an occurence of `prev`. |
| ref ~ siblings | Sample 4 | Selects the `siblings` element after the `ref` element at the same depth. They don't need to be directly or consecutively after `ref`. |
| [attr1='10'][attr2='default'] | Sample 5 | Selects elements having `attr1` with value 10 and `attr2` with value default. Giving no value just checks the attribute is present. |
| .class1, .class2 | Sample 6 | Selects all elements having `class1` or `class2`. |
| .class1:not(.class3) | Sample 7 | Selects all elements having `class1` exclusive of `class3`. |

> Sample 1: Selecting direct child
```html
<parent>
    <directChild></directChild> <!-- Selected element-->
</parent>
```

> Sample 2: Selecting descendants
```html
<ancestor>
    ... any hierarchy. 
    Do not need to be a direct descendant.
    <descendant></descendant> <!-- Selected element-->
</ancestor>
```

> Sample 3: Selecting the next sibling
```html
<div>
    <prev />
    <next /> <!-- Selected element-->
</div>
```

> Sample 4: Selecting the next siblings
```html
<ref></ref>
<anything />
<siblings /> <!-- Selected element-->
<siblings /> <!-- Selected element-->
<anything />
<siblings /> <!-- Selected element-->
```

> Sample 5: Selecting an element having multiple attributes
```html
<div attr1="10" attr2="default"></div> <!-- Selected element-->
```

> Sample 6
```html
<div class="class1"></div> <!-- Selected element-->
<div class="class2"></div> <!-- Selected element-->
<div class="class1"></div> <!-- Selected element-->
<div class="class3"></div>
<div class="class3 class2"></div> <!-- Selected element -->
<div class="class3 class1"></div> <!-- Selected element-->
<div class="class2"></div> <!-- Selected element-->
<div class="class3"></div>
<div class="class1"></div> <!-- Selected element-->
```

> Sample 7
```html
<div class="class1"></div> <!-- Selected element-->
<div class="class2"></div> <!-- Selected element-->
<div class="class1"></div> <!-- Selected element-->
<div class="class3"></div>
<div class="class3 class2"></div> <!-- Selected element -->
<div class="class3 class1"></div> <!-- Selected element-->
<div class="class2"></div> <!-- Selected element-->
<div class="class3"></div>
<div class="class1"></div> <!-- Selected element-->
```
There is also a jQuery `not(selector)` method to exclude selectors.

There is more to CSS selectors than what is present in this synthesis.

More info on CSS selectors:
- [@W3C CSS Working group](https://www.w3.org/TR/selectors-3/)
- [@Mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
- [@ W3Schools](https://www.w3schools.com/cssref/css_selectors.asp).