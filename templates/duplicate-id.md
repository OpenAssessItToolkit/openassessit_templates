{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

#####Visual location:

|

#####HTML location:

```html
{{ node.html }}
```

#####Suggested solution:

1. Check if the page needs that ID for CSS for visual reasons.
2. Check if the page needs that ID for JS for interactive behaviours.
3. If it needs the IDs edit the dependent code, then remove duplicate IDs from the HTML.

<details>
<summary>__Additional debugging details__</summary>

_Selector path:_ <br> `{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`
</details>
<hr>
{% endfor -%}
