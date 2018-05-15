{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

Impact: {{ node.impact }}

HTML: `{{ node.html }}`

Failure Summary: {{ node.failureSummary }}

<sup>Path: {{ node.path }}</sup>

{% endfor -%}
