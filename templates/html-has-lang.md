## {{ audit.title }} [WCAG 3.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#language-of-page)

{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

### Add `lang` attribute.

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add a `lang` attribute. For websites in english use `<html lang="en">`. [Other languages references](https://www.w3schools.com/tags/ref_language_codes.asp)

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}
