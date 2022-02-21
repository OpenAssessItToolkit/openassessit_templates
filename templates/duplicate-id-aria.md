## {{ audit.title }} [WCAG 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#parsing)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

<h3> {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }} </h3>

__Visual location:__

![{{ item.node.snippet|striptags }} element with duplicate ID](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

{{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}

{% include 'includes/other-options.md' %}

---

{% endfor %}
