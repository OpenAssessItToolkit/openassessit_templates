{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

Image missing alt tag:
{{ node.html }}

HTML:<br>
`{{ node.html }}`

<details>
<summary>Additional debugging details</summary>
Selector path: `{{ node.target }}`

DOM path:  {{ node.path }}

Summary:  {{ node.failureSummary }}
</details>
<hr>
{% endfor -%}
