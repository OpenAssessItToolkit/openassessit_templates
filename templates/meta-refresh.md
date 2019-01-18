{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### Meta refresh issue

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Remove the `{{ item.node.snippet }}` tag from the header.

{% include 'includes/other-options-w-details.md' %}

-
<br>

{% endfor %}

<br>