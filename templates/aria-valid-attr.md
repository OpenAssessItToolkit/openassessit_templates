{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element has an invalid aria attribute.

__Visual location:__

![aria valid attr problem](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

TODO.

{% include 'includes/other-options-w-details.md' %}

---
<br>

{% endfor %}

<br>