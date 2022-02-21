# Expand-collapse widget issue

## Interactive controls are not keyboard focusable [WCAG 2.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#keyboard) and Custom controls are missing ARIA roles [WCAG 4.1.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value)


Description:<br>
If new content, such as a dialog, is added to the page, the user&#39;s focus is directed to it. [Learn more](https://web.dev/managed-focus/).


### Expand collapse not keyboard focusable and missing ARIA attributes to describe state

__Visual location:__

![expand collapse does not work](assets/expand-collapse.png)

Interactive components like this with show/hide functionality need to be accessible to keyboard-only and screen reader users.

This is by providing keyboard focus and ARIA attributes to describe the state of the object.

#### Suggested solution:

Change HTML to become keyboard focusable and add ARIA attributes. Similar to the following:


Add JS to toggle expand or collapsed state.

<https://www.w3.org/WAI/GL/wiki/Using_the_WAI-ARIA_aria-expanded_state_to_mark_expandable_and_collapsible_regions#Example_1:_Using_a_button_to_collapse_and_expand_a_region>
