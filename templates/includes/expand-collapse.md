# Expand-collapse widget issue

## Interactive controls are not keyboard focusable [WCAG 2.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#keyboard) and Custom controls are missing ARIA roles [WCAG 4.1.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value)


Description:<br>
If new content, such as a dialog, is added to the page, the user&#39;s focus is directed to it. [Learn more](https://web.dev/managed-focus/).


### Expand collapse not keyboard focusable and missing ARIA attributes to describe state

__Visual location:__

![expand collapse does not work](assets/expand-collapse.png)

Interactive components like this with show/hide functionality need to be accessible to keyboard-only and screen reader users.

This is by providing keyboard focus and ARIA attributes to describe the state of the object.

The toggle element must be keyboard focusable using the Tab key with a element of `<button>` or `<a href="" role="button">`

It must have a dynamic [aria-expanded](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-expanded) attribute that toggles its value. The value should match the visibility of its content. When it is hidden the value should be `false` and when its content gets shown the value should be `true`.

#### Suggested solution:

Add JS to toggle the expanded or collapsed state in a way similar to these examples.

<https://www.w3.org/WAI/ARIA/apg/patterns/disclosure/examples/disclosure-faq/>

<https://www.w3.org/WAI/ARIA/apg/patterns/accordion/examples/accordion/>

Note: If the expand/collapse area is directly after the the toggle element, you can omit the `aria-controls` attribute.
