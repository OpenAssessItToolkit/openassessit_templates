## {{ audit.title }} [WCAG 4.1.2](https://www.w3.org/WAI/WCAG22/quickref/?versions=2.1#name-role-value)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### The element _"{{ item.node.snippet|striptags }}" is using an invalid ARIA `role` in its context

__Visual location:__

![element with bad aria role](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

{{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}

{% include 'includes/other-options.md' %}

<br>

---

<br>

{% endfor %}
