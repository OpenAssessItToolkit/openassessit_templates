## {{ audit.title }}

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### Meta refresh issue

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Explanation:

{% include 'includes/explanation.md' %}

---
<br>

{% endfor %}