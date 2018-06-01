{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

{# <h4><em>{{ node.html|striptags }}</em> is not a descriptive name to a screen reader</h4> #}

{# A screen reader would just read " {{ node.html|striptags }} ". " {{ node.html|striptags }} " does not indicate its purpose, or where it will take the them. #}

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
