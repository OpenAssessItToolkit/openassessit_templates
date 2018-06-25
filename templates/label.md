{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element is missing a label

__Visual location:__
{# TODO: Grabbing screen shots of specific elements can probably be automated #}
![ form element with no label](https://via.placeholder.com/150x50)

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add `<label for="something">` to associate the label with that form field. If the element does not have and ID attribute to associate add `id="something"`.
If you wish to visually hide the label add class like `.sr-only` or `.element-invisible` to the `<label>`.

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>

More detailed explanation:<br>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<hr>

<br>
{% endfor %}