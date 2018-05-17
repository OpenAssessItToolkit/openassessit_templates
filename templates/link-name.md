{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

#### INSERT DESCRIPTION OF LINK HERE

INSERT IMAGE HERE

{# TODO: Insert name of the link and provide advice #}

HTML:<br>
`{{ node.html }}`

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
