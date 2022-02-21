## {{ audit.title }} [WCAG 1.1.1](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#non-text-content)

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

Image missing `alt` attribute:

![Image missing alt tag](assets/{{ generate_img_filename(data.finalUrl, item.node.selector, item.node.lhId) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add an `alt` attribute with an accurate description to the image or add invisible screen reader text.

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}
