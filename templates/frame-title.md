{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

INSERT IMAGE HERE:

HTML:<br>
`{{ node.html }}`

Summary:<br>
{{ node.failureSummary }}

<details>
<summary>__Additional debugging details__</summary>

_Selector path:_ <br> `{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`
</details>
<hr>
{% endfor -%}
