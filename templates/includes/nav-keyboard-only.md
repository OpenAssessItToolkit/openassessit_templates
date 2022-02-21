## Menu not keyboard or screen reader compatible [WCAG 2.1.1](https://www.w3.org/TR/WCAG21/#keyboard)

Description:<br>
If new content, such as a dialog, is added to the page, the user&#39;s focus is directed to it. [Learn more](https://web.dev/managed-focus/).

### Main menu drop downs are inaccessible

Currently, only mouse-users can use the main menu drop downs.  The main menu should be accessible via the keyboard alone for keyboard-only and screenreader only users. People who user a keyboard will hit the Tab key to get through the menu.

__Visual location:__

![dropdown](assets/dropdown.png)

__HTML location:__

```html

```

####Suggested solution:

__Auto-expanding option:__

Add `:focus-within` in addition to the existing `:hover` selector to enable hover state for keyboard-users.  This will automatically expand the sub menu when the top level menu item gets focus

```css
:focus-within
```

__Dropdown toggle option:__

The main menu toggle button functions similarly to a disclosure navigation widget. AT users would benefit from proper markup and keyboard scripting for this type of widget to set expectations for interaction patterns and to convey state


Fully implement disclosure widget markup for the button as suggested by the WAI-ARIA Authoring Guidelines:

https://www.w3.org/TR/wai-aria-practices-1.1/examples/disclosure/disclosure-navigation.html

https://www.w3.org/WAI/GL/wiki/Using_the_WAI-ARIA_aria-expanded_state_to_mark_expandable_and_collapsible_regions#Example_1:_Using_a_button_to_collapse_and_expand_a_region

