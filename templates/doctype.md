## {{ audit.title }} [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#compatible)

{{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

{% endif -%}

{{ explanation }}

An invalid or missing `doctype` also makes it difficult or impossible to verify if the rest of the code is valid. Less validation errors results in more robust code that will work more predictably on a wide variety of devices, browser, and assistive technologies.

#### Suggested solution:

Use a valid 'doctype' as the first line of the HTML. [List of valid doctypes](https://www.w3.org/QA/2002/04/valid-dtd-list.html).

---

