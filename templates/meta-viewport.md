{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This `<meta>` tag has attributes that are detrimental to accessibility.

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

If applicable:

1. Change `maximum-scale=1.0` to at least `maximum-scale=5`.

2. Remove the `user-scaleable=no` attribute from the meta tag.

{% include 'includes/other-options-w-details.md' %}

---

{% endfor %}
