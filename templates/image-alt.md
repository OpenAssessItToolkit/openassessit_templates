{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

Image missing `alt` attribute:

![Image missing alt tag]({{ generate_img_filename(data.requestedUrl, item.node.selector) }})

{% endif -%}

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add an `alt` attribute with an accurate description to the image or add invisible screen reader text.

<details>
<summary>_Other options:_</summary>
Detailed explaination:<br>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code><br>
Path:<br>
<code>{{ item.node.selector }}</code>
</details>

<hr>

<br>
{% endfor %}