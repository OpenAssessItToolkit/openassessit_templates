## {{ audit.title }} [WCAG 2.4.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#bypass-blocks)[WCAG 4.1.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

iframe missing `title`:

![{{ item.node.snippet|striptags }} missing title](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add a descriptive `title` attribute.

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}
