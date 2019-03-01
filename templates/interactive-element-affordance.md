
__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

Pay special attention to buttons and links.  For example, links and buttons should have obvious :hover and :focus states that meet WCAG 2.0 AA contrast requirements.

{% endif -%}

---

