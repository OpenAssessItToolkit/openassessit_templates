## {{ audit.title }} [WCAG 2.4.4](https://www.w3.org/WAI/WCAG22/quickref/?versions=2.1&showtechniques=413#link-purpose-in-context)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### The element _"{{ item.node.snippet|striptags }}"_ is near a link with the same purpose

__Visual location:__

![Link with same purpose](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})


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
