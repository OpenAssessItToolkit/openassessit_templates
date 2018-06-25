{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

__Visual location:__

Image missing `alt` attribute:

{% if ('onclick' or
      'onfocus' or
      'onmousedown' or
      'onmouseup' or
      'onmouseover' or
      'onmouseout') in item.node.snippet  %}

{# If these attributes are on the image it could cause wierd problems. Don't print the image if it has these. #}
_Auditor - manually add the image_

![Image missing alt tag](https://via.placeholder.com/150x50)

{% else -%}

{# try http://jinja.pocoo.org/docs/2.10/templates/#rejectattr #}
{# we don't want the images style attribute to start messing with the markdown #}

{{ item.node.snippet|replace('style', 'data-style')}}

{% endif -%}

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Add alt text.

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>

Detailed explaination:<br>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<hr>

<br>
{% endfor %}