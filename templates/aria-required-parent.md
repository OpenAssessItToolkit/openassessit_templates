## {{ audit.title }}

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

<h3> This element's {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}</h3>

__Visual location:__

![aria missing required child roles](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Explanation:

{% include 'includes/explanation.md' %}

---
<br>

{% endfor %}