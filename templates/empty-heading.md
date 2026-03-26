## {{ audit.title }} [WCAG 2.4.6](https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels.html)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This heading contains no text

__Visual location:__

![empty heading](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Remove the empty heading or add text to the heading

<br>

---

<br>

{% endfor %}