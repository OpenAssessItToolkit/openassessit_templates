## {{ audit.title }} [WCAG 2.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#keyboard)

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

__Explanation (must watch):__

<iframe width="560" height="315" src="https://www.youtube.com/embed/qYuQLQFy3ss" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

{% endif -%}

---
