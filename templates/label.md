{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element is missing a label

__Visual location:__
![Element missing label]({{ data.requestedUrl|regex_replace('[^0-9a-zA-Z]+', '') }}{{ item.node.selector|regex_replace('[^0-9a-zA-Z]+', '') }}.png)

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add `<label for="something">` to associate the label with that form field. If the form element does not have an ID attribute to associate add `id="something"`.
If you wish to visually hide the label then add a class like `.sr-only` or `.element-invisible` to the `<label>`.

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