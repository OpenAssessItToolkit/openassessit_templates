
__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

Pay special attention to popup windows like ads or email signup solicitations. 

<br>

{% endif -%}

<br>