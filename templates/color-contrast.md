{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### The element _"{{ item.node.snippet|striptags }}"_ has low contrast.

__Visual location:__

![Text with low contrast](assets/{{ generate_img_filename(data.requestedUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
{{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}

Find a color with higher contrast.

{% include 'includes/other-options.md' %}

<hr>

<br>
{% endfor %}