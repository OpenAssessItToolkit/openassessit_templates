## {{ audit.title }} [WCAG 1.3.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#info-and-relationships)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

<h3> This element's {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }} </h3>

__Visual location:__

![aria missing required children roles](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Using this `role` on this parent element is harmful because it does not do anything without it's required child roles. It will confuse assistive technology and the people who rely on it.

If this element's `role` is meant to be helpful, add the required `role` indicated above to its children.

If this element's `role` is unnecessary, remove it.


{% include 'includes/other-options.md' %}

---

{% endfor %}
