## {{ audit.title }}

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This `button` or `input` has no `value` attribute or it contains no inner text to indicate its purpose

__Visual location:__

![button is not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Explanation:

{% include 'includes/explanation.md' %}

---
<br>

{% endfor %}