{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

{# TODO: (Priority) Parse the item.node.snippet results to indicate exactly what is wrong, is it the value?, is it missing a value?, is it a missing inner image alt tag?, is it missing inner text to provide specific Suggested solution #}

### This `button` or `input` has no `value` attribute or it contains no inner text to indicate its purpose

__Visual location:__

{# TODO: Grabbing screen shots of specific elements can probably be automated #}
![button is not discriptive](https://via.placeholder.com/150x50)

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:

There are many ways to fix this issue:

{# TODO: Parse the snippet to detect exactly what is missing. Is is the value? missing text? etc. to provide specific advice on each situation. #}
{{ item.node.explanation|escape|replace('  ', '<br>') }}

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>

</details>

<hr>

<br>
{% endfor %}