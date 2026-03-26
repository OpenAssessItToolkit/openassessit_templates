## {{ audit.title }} [WCAG 2.4.3](https://www.w3.org/WAI/WCAG22/Understanding/label-in-name.html)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This elements content does not match the accessible name

__Visual location:__

![name mismatch](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:



<br>

---

<br>

{% endfor %}
