{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

### Add `lang` attribute.

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add a `lang` attribute. For websites in english use `<html lang="en">`. [Other languages references](https://www.w3schools.com/tags/ref_language_codes.asp)

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

-
<br>

{% endfor %}

<br>