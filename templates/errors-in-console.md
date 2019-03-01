## {{ audit.title }}

{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

__Error:__

```
{{ item.description }}
```

---
<br>

{% endfor %}