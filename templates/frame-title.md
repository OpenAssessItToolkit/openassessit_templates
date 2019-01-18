{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

iframe missing `title`:

![{{ item.node.snippet|striptags }} missing title](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add a descriptive `title` attribute.

{% include 'includes/other-options-w-details.md' %}

-
<br>

{% endfor %}

<br>