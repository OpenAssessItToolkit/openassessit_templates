{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

{% if 'img' in item.node.snippet  %}

### This `<a>` link has no text and its image has no `alt` attribute.

Empty links with no text and an image with no alt text will read _"Link Image"_ to screen reader users. As a result, they will not know what the link does or what is in the image.

__Visual location:__

{# TODO: Grabbing screen shots of specific elements can probably be automated #}
![{{ item.node.snippet|striptags }} not discriptive](https://via.placeholder.com/150x50)

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add an `alt` attribute to image or add invisible screen reader text.

{% else -%}

### This `<a>` link has no text inside.

__Visual location:__

{# TODO: Grabbing screen shots of specific elements can probably be automated #}
![{{ item.node.snippet|striptags }} link that is not discriptive](https://via.placeholder.com/150x50)

__HTML Location__:

```html
{{ item.node.snippet }}
```
Empty links are not read to a screen reader user, as a result, they will have no idea what the link does or where it would take them.

#### Suggested solution:

Remove the empty link or add screen reader only text inside link

{% endif -%}

{% if item.node.snippet|striptags|trim != '' %}

### A link name of _"{{ item.node.snippet|striptags }}"_ is not a descriptive name to a screen reader.

A screen reader user would just hear _"Link {{ item.node.snippet|striptags }} "_. That does not indicate its purpose, or where it will take the them.

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:

If the link already exists, delete the _"{{ item.node.snippet|striptags }}"_ Link. Or add screen reader only text inside the link.

{% endif -%}

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