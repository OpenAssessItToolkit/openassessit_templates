# Report of {{ data.url }}

{% for cat in data.reportCategories %}
## {{ cat.name }}
{%- for audit in cat.audits -%}
{%- if audit.score < 100 or audit.result.notApplicable == false %}
### {{ audit.result.description }}
{% include [audit.audit_template, "audit_result.md"] %}
<br>
<br>
<hr>
{%- endif %}
{%- endfor -%}
{%- endfor -%}
