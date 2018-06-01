{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

####`iframe` missing `<title>` element

#####Visual location:

{{ node.html }}

#####HTML location:

```html
{{ node.html }}
```

#####Suggested solution:

{{ node.failureSummary }}

<details>
<summary>__Additional debugging details__</summary>

_Selector path:_ <br> `{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`
</details>
<hr>
{% endfor -%}
