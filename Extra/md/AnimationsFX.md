Animations and effects
======================

> Related demo :
> - [Animations](../demos/Animations.html)

## Showing and hiding elements

Use `show()`, `hide()` or `toggle()` 
They take optional parameters such as an integer to determine the time it will take to animate from one state to other. Also a callback function that happen after completion of the action.
This is a script that plays both on `height` and `opacity` when a duration is passed. Sets `display` to `none` when it has to be hidden.

## Fading in/out/toggle
Use `fadeIn()`, `FadeOut()` or `fadeToggle()`
Same as show/hide/toggle apply regarding parameters.
This is a script that plays with `opacity` and sets `display` to `none` when it has to be hidden.

## Sliding in/out/toggle
Use `slideUp()`, `slideDown()` or `slideToggle()`
Same as show/hide/toggle apply regarding parameters.
This is a script that plays with `height` of the element and sets `display` to `none` when it has to be hidden.

```css
{
    overflow: hidden;
    margin-top:0;
    margin-bottom:0;
    padding-top: 0;
    padding-bottom: 0;
}
```

## Animate

The `animate()` method has 3 parameters

- An object holding the CSS to be applied. It can only deal with properties having numeric values. There might be some plugins to animate other properties such as background color.
- duration
- callback function upon completion.

More info about `animate()` [@jQuery official doc](https://api.jquery.com/animate/)