{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This `<meta>` tag has attributes that are detrimental to accessibility.

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

1. Remove the `user-scaleable=no` attribute from the meta tag.
2. If applicable, change `maximum-scale=1.0` to `maximum-scale=5`.

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