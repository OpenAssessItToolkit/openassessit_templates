## {{ audit.title|escape }}

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### Failing element

__Visual location:__

![{{ item.node.snippet|striptags }} not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```
#### Explanation:

{% include 'includes/explanation.md' %}

---
<br>

{% endfor %}