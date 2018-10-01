{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

iframe missing `title`:

{% if 'src' in item.node.snippet  %}

{{ item.node.snippet }}

{% else -%}

![iframe missing title]({{ generate_img_filename(data.requestedUrl, item.node.selector) }})

{% endif -%}

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add a descriptive `title` attribute.

<details>
<summary>_Other options:_</summary>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<details>
<summary>_Additional debugging details_</summary>
Path:<br>
<code>{{ item.node.path }}</code><br>
Selector:<br>
<code>{{ item.node.selector }}</code>
</details>

<hr>

<br>
{% endfor %}