## {{ audit.title }} [WCAG 2.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#keyboard) [WCAG 2.4.3](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#focus-order)

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

Pay special attention to menus. For example, the focus indicator should not be lost while tabbing through a menu.

{% endif -%}

---
