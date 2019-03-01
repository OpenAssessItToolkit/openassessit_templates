## {{ audit.title }} [WCAG 2.4.6](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#headings-and-labels)

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

{% endif -%}

---
