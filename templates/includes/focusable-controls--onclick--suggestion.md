#### Suggested solution:

Use an anchor `<a href="fancy-cats.html">` instead of the `onclick` handler.

__Alternative solution:__

If there is a reason an anchor cannot be used here, the `<div>` would need a `tabindex="0"` attribute to make it focusable and it will need additional keyboard event listeners to detect the enter key when the element is focused.

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
