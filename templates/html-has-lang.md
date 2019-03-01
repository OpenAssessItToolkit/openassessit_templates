## {{ audit.title }}

{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

### Add `lang` attribute.

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Explanation:

{% include 'includes/explanation.md' %}

---
<br>

{% endfor %}