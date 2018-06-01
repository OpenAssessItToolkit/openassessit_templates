{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

<h4>The {{ node.failureSummary|replace('Fix any of the following:', '')}}</h4>

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
<summary>__Additional debugging details__</summary>

_Selector path:_ <br> `{{ node.target }}`
`{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`

</details>
<hr>
{% endfor -%}
