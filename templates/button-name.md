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

#### Suggested solution:

There are many ways to fix this issue:

{{ item.node.explanation|escape|replace('  ', '<br>') }}

{% include 'includes/other-options.md' %}

---
<br>

{% endfor %}

<br>