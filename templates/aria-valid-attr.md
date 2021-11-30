## {{ audit.title }} [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#parsing)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element has an invalid aria attribute.

__Visual location:__

![aria valid attr problem](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Invalid `role` values could cause problems with assistive technology.

Remove the attribute, correct the misspelling, or [change it to a valid role](https://www.w3.org/WAI/PF/HTML/wiki/RoleAttribute#ARIA_1.0_Pre-Defined_Roles).

{% include 'includes/other-options.md' %}

---

{% endfor %}