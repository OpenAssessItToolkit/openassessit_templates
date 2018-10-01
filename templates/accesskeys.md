{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### The {{ item.node.snippet|striptags }}element should not have an `accesskey`.

__Visual location:__
![{{ item.node.snippet|striptags }} element with an access key](assets/{{ generate_img_filename(data.requestedUrl + '/assets', item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Unless this website is an app, remove all `accesskeys` attributes. They can interfere with assistive technology.

<details>
<summary>_Other options:_</summary>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<details>
<summary>_Additional debugging details_</summary>
Path:<br>
<code>{{ item.node.path }}</code><br>
Selector:<br>
<code>{{ item.node.selector }}</code>
</details>

<hr>

<br>
{% endfor %}