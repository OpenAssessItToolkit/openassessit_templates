#### Suggested solution:

__Option 1:__

Use an element that can recieve focus by default like an anchor `<a href="fancy-cats.html">` instead of the `onclick` handler.

__Option 2:__

Example:

```js
var $fauxDivLink = $('.selector-of-this-type-of-faux-link');

// $fauxDivLink.attr('tabindex', '0'); // if you can't add the tabindex to the div in real life, you can add it here.

$fauxDivLink.keyup(function (e) {
    if (e.keyCode === 13 || e.keyCode === 32) { // key press for WCAG
        $fauxDivLink.click();
    }
});
```
