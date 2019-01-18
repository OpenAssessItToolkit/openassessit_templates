{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

__Error:__

```
{{ item.description }}
```

#### Suggested solution:
Auditor TODO: If possible, add solution based on error.

-
<br>

{% endfor %}

<br>