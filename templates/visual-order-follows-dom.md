## {{ audit.title }} [WCAG 1.3.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#meaningful-sequence)

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

[Textise](https://www.textise.net/) is a neat tool for inspecting the natural order of the website. [View this website on Textise](https://www.textise.net/showText.aspx?strURL={{ data.finalUrl|replace('https://', '') }}). If nothing has been done in JS to interfere the natural tab order, looking at that or viewing the source will basically follow the order of the markup.

{% endif -%}

---

