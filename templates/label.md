{{ audit.result.helpText }}

{# Score: {{ audit.result.score }} #}
{%- if audit.result.displayValue %}
Display value: {{ audit.result.displayValue }}
{% endif %}

{% for node in audit.full_audit.extendedInfo.value.nodes %}

####Form field missing label:<br>

#####Visual location:

-

#####HTML location:

```html
{{ node.html }}
```

#####Suggested solution:

Add `<label for="something">` to associate the label with that form field. If the element does not have and ID attribute to associate add `id="something"`.<br>
If you wish to visually hide the label add class like `.sr-only` or `.element-invisible` to the `<label>`.

<sub>For more options see 'Additional debugging details' below.</sub>

<details>
<summary>__Additional debugging details__</summary>

_Selector path:_ <br> `{{ node.target }}`
`{{ node.target }}`

_DOM path:_ <br>
`{{ node.path }}`

_Summary:_ <br>
{{ node.failureSummary }}
</details>
<hr>
{% endfor -%}
