## {{ audit.title }} [WCAG 2.1](https://www.w3.org/WAI/WCAG21/quickref/#keyboard-accessible)

__I need a human!__ Manual Test: {{ audit.title }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

Using the `accesskey` attribute is discouraged because they can interfere with assistive technology. On most websites they are not necessary or helpful. If they do exist, they must be unique.

{% endif -%}

---