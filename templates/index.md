# Report {{ data.url }}

{% for cat in data.reportCategories %}
## {{ cat.name }}
{%- for audit in cat.audits -%}
{%- if audit.score < 100 %}
### {{ audit.result.description }}
{% include [audit.audit_template, "audit_result.md"] %}
<hr>
{%- endif %}
{%- endfor -%}
{%- endfor -%}
