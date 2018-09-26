{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

<h4>This {{ node.failureSummary|replace('Fix any of the following:', '')}} here</h4>

_Summary:_
{{ node.failureSummary }}

#####Visual location:

|

#####HTML location:

```html
{{ node.html }}
```
#####Suggested solution:

<br>

<details>
<summary>_Other options:_</summary>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<details>
<summary>_Additional debugging details_</summary>
Path:<br>
<code>{{ item.node.path }}</code><br>
Selector:<br>
<code>{{ item.node.selector }}</code>
</details>
<hr>
{% endfor -%}
