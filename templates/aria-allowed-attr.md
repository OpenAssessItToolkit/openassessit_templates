## {{ audit.title }} [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#parsing) [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element's role is not valid.

__Visual location:__

![aria attribute not allowed here](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

TODO.

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}
