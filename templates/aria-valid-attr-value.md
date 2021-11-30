## {{ audit.title }} [WCAG 1.3.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#info-and-relationships) [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#parsing) [WCAG 4.1.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value">WCAG 4.1.2)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element is using invalid aria attributes.

__Visual location:__

![aria valid attribute value problem](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

{{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}

{% include 'includes/other-options.md' %}

---

{% endfor %}