## {{ audit.title }}

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

#### Explanation:

{% include 'includes/explanation.md' %}

---
<br>

{% endfor %}