{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

iframe missing `title`:

{% if 'src' in item.node.snippet  %}

{{ item.node.snippet }}

{% else -%}

![iframe missing title](assets/{{ generate_img_filename(data.requestedUrl, item.node.selector) }})

{% endif -%}

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add a descriptive `title` attribute.

{% include 'includes/other-options-w-details.md' %}

<hr>

<br>
{% endfor %}