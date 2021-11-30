## {{ audit.title }} [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#compatible)

{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

__Error:__

```
{{ item.description }}
```

#### Suggested solution:

Debug JS code to find source of issue.

---

{% endfor %}