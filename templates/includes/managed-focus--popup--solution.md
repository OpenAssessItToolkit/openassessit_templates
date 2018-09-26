__Short-term [Priority]:__<br>

Getting this short-term solution in place is the number one priority.

We can mitigate the problem a little bit by adding a couple lines of JS.  Lets add a keyboard listener for the `esc` key when a modal is active.  If a keyboard user activates the popup, they can recover from that action. Otherwise, the modal will be suck in front of the content and block access to content.

```js
// if the popup is open
if (jQuery('#wrapper-id-of-the-popup:visible')) {

    // make escape key close the modal
    $(document).keydown(function(e) {
        if (e.keyCode == 27) {
            // insert call to the API to close the popup
        }
    });
}
```

This does not fix it. But it mitigates the problem.

__Long-term:__<br>
A more accessible popup/modal library will need to replace the current inaccessible one. If we can get the short-term suggestion above on the live website, lets put this at the bottom of the list.

An valid alternative to replacing the library would be to detect that the link was activated by the keyboard, you could just send them directly to the content instead of presenting it in a popup window
