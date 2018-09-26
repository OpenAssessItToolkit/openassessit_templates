{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### Meta refresh issue

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Remove the `{{ item.node.snippet }}` tag from the header.

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