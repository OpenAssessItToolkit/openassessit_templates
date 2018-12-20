## :Focus indicator is missing

The key purpose of :focus is to give a user guidance. 

Links need to be focusable as the user tabs through the website for keyboard only users and screen reader users. If the focus indicator is missing, a keyboard user will have no idea what link they are on. [Learn more](https://www.deque.com/blog/accessible-focus-indicators/)

By default the :focus styles work in a webbrowser.  . Links, Buttons, and Form Fields / Controls (text fields, select boxes, radio buttons, etc.) are focusable. It is possible to inadvertently break this behavior.

__Compliant default :focus example:__

![default focus example](assets/https---focus-good-example.png)

Custom :focus states are allowed. The :focus states in the main content of this website are valid.

__Visual location:__

![menu missing focus](assets/)

__Code location of menu with no focus indicator:__

The offending code can be found in this aggregated CCS file:
```css
stuff
```

### Suggested solution:

The best way to fix this is to delete any references to outline, outline-width, outline-color, properties so it restores Drupal's valid and compliant behavior.

If that CSS/SASS can not be modified for some reason it be fixed in an additive manner by overriding the outline with a new outline with enough specificity to override the errant code.