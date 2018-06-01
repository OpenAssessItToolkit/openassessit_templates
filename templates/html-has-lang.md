{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

#####HTML location:

```html
{{ node.html }}
```
#####Suggested solution:

Add language attribute:
`<html lang="en">`

<hr>
{% endfor -%}
