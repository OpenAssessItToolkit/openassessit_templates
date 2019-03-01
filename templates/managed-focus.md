## {{ audit.title }} [WCAG 3.2.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#on-input)

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

Pay special attention to popup windows like ads or email signup solicitations. 

{% endif -%}

---
