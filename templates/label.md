## {{ audit.title }} [WCAG 3.3.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#labels-or-instructions)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element may be missing a label

__Visual location:__

![Element missing label](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

1. Check for a `<label for="something">` attribute.
2. If it exists, ensure the `for` element that it is referencing exists as an `id` on its intended form field.
3. If it is missing, Add `<label for="something">` to associate the label with that form field. If the form element does not have an ID attribute to associate add `id="something"`.

Also see "Other options" below for more valid solutions.

Note 1: In some cases, you could visually hide the label using 'invisible screen reader only text' so it is  still announced to screen reader users.

Note 2: `placeholder` attributes alone are not a valid substitute for `<label>`s, but having one that is descriptive is benificial. If the label uses screen reader only text, a `placeholder` is highly suggested.

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}

### FYI: What is 'invisible screen reader only text'?

{% include 'includes/link-name--sr-only--solution.md' %}