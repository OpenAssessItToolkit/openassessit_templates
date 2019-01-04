{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element's role is not valid.

__Visual location:__

![aria role is not valid](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

This `role` does not exist. It will confuse assistive technology and the people who rely on it.

[See this list of valid aria roles](https://www.w3.org/WAI/PF/HTML/wiki/RoleAttribute#ARIA_1.0_Pre-Defined_Roles). Replace it with a valid appropriate role.


{% include 'includes/other-options.md' %}

<hr>

<br>
{% endfor %}