{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

<h3> {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }} </h3>

__Visual location:__

![{{ item.node.snippet|striptags }} element with duplicate ID](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

####Suggested solution:

1. Check if the page needs that ID for CSS for visual reasons.
2. Check if the page needs that ID for JS for interactive behaviors.
3. If it needs the IDs edit the dependent code, then remove duplicate IDs from the HTML.

{% include 'includes/other-options-w-details.md' %}

-
<br>

{% endfor %}

<br>