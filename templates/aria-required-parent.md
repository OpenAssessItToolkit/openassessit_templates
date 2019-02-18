{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

<h3> This element's {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}</h3>

__Visual location:__

![aria missing required child roles](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Using this `role` on this child element is harmful because it does not do anything without it's required parent roles. It will confuse assistive technology and the people who rely on it.

If this element's `role` is meant to be helpful, add the required `role` indicated above to its parent.

If this element's `role` is unnecessary, remove it.


{% include 'includes/other-options.md' %}

---
<br>

{% endfor %}

<br>