{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

HTML:<br>
`{{ node.html }}`

Failure Summary:
{{ node.failureSummary }}

<details><summary>Additional details</summary>
Selector:  `{{ node.target }}`

Path:  {{ node.path }}
</details>

{% endfor -%}
