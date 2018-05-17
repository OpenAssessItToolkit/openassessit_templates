{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

Image missing alt tag:<br>
{{ node.html }}

_HTML:_ <br>
`{{ node.html }}`

<details>
<summary>__Additional debugging details__</summary>

_Selector path:_ <br> `{{ node.target }}`
`{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`

_Summary:_ <br>
{{ node.failureSummary }}
</details>
<hr>
{% endfor -%}
