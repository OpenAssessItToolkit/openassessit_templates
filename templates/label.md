{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element is missing a label

__Visual location:__

![Element missing label](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add `<label for="something">` to associate the label with that form field. If the form element does not have an ID attribute to associate add `id="something"`.
If you wish to visually hide the label then add a class like `.sr-only` or `.element-invisible` to the `<label>`.

If that already exists, add a `placeholder` attribute. Hidden labels require a `placeholder` attribute so people know what the field is for.

{% include 'includes/other-options-w-details.md' %}

---
<br>

{% endfor %}

<br>