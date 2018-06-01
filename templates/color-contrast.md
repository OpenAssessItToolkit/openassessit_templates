{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

<h4>The "<em>{{ node.html|striptags }}</em>" link has low contrast.</h4>

#####Visual location:

|

#####HTML location:

```html
{{ node.html }}
```

#####Suggested solution:

{{ node.failureSummary }}`

<details>
<summary>_Additional debugging details_</summary>

_Selector path:_ <br>
`{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`
</details>

<hr>
{% endfor -%}
