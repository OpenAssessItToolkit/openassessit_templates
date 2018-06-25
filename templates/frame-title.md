{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

iframe missing `title`:

{% if 'src' in item.node.snippet  %}

{{ item.node.snippet }}

{% else -%}

_Auditor - manually add image or video_

![iframe missing title](https://via.placeholder.com/50x50)

{% endif -%}

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add a descriptive `title` attribute.

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>

Detailed explaination:<br>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<hr>

<br>
{% endfor %}