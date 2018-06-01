{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

#### INSERT DESCRIPTION OF BUTTON HERE

{# TODO: Insert name of the button and provide advice #}

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

_DOM path:_ <br>
`{{ node.path }}`

_Summary:_ <br>
{{ node.failureSummary }}
</details>
<hr>
{% endfor -%}
