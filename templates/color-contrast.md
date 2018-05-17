{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

HTML:<br>
`{{ node.html }}`

Summary:<br>
{{ node.failureSummary }}

<details>
<summary>Additional debugging details</summary>
Selector path: `{{ node.target }}`

DOM path:  {{ node.path }}
</details>
<hr>
{% endfor -%}
