{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}

__Visual location:__

![{{ item.node.snippet|striptags }} element with duplicate ID](https://via.placeholder.com/150x50)

__HTML location:__

```html
{{ item.node.snippet }}
```

####Suggested solution:

1. Check if the page needs that ID for CSS for visual reasons.
2. Check if the page needs that ID for JS for interactive behaviors.
3. If it needs the IDs edit the dependent code, then remove duplicate IDs from the HTML.

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>
</details>

<hr>

<br>
{% endfor %}