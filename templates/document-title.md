## {{ audit.title }} [WCAG 2.4.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#page-titled)

{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}



__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add an accuate `<title>` in the `<head>` of the document.

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}
