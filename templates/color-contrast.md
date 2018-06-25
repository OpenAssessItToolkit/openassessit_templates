{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### The link _"{{ item.node.snippet|striptags }}"_ has low contrast.

__Visual location:__

{# TODO: Grabbing screen shots of specific elements can probably be automated #}
![{{ item.node.snippet|striptags }} text with low contrast](https://via.placeholder.com/150x50)

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
{{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }}

{# TODO: (Priority) Parse the node explanation to make a visual representation of the contrast and also generate a prefilled out permalink from here to to webaim's color contrast https://webaim.org/resources/contrastchecker/?fcolor=FFFFFF&bcolor=000000 page so people can easily make up thier own new color off of that page. #}

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>

More detailed explanation:<br>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<hr>

<br>
{% endfor %}