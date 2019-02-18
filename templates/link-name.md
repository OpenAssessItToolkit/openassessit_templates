{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

{% if (item.node.snippet|striptags == '') and ('img ' in item.node.snippet) and ('alt' not in item.node.snippet)  %}

### This `<a>` link has no text and its image has no `alt` attribute.

Empty links with no text and an image with no alt text may read _"Link Image"_ to screen reader users. As a result, they will not know what the link does or what is in the image.

__Visual location:__

![{{ item.node.snippet|striptags }} not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add an `alt` attribute to image.

{% elif (item.node.snippet|striptags == '') and ('img ' not in item.node.snippet)  %}

### This `<a>` link has no text inside.

__Visual location:__

![{{ item.node.snippet|striptags }} not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML Location__:

```html
{{ item.node.snippet }}
```
Empty links are not read to a screen reader user, as a result, they will have no idea what the link does or where it would take them.

#### Suggested solution:

Remove the empty link.



{% elif (item.node.snippet|striptags|trim != '') and ('img ' not in item.node.snippet) and ('alt=' not in item.node.snippet) %}

### A link name of _"{{ item.node.snippet|striptags }}"_ might not a descriptive name to a screen reader.

A screen reader user might just hear _"Link {{ item.node.snippet|striptags }} "_. If that clearly indicates its purpose and where it will take the them, it is ok.  If it is vauge like, "Read more" or "Learn more", it won't make sense out of context and it must be changed.

__Visual location:__

![{{ item.node.snippet|striptags }} not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Ask does this link name make sense if no context is provided? If yes, this can be ignored.  If no, check if the link already exists in another context, delete the _"{{ item.node.snippet|striptags }}"_ Link. Or add screen reader only text inside the link.



{% elif ('learn more' in item.node.snippet|striptags|trim ) or ('read more' in item.node.snippet|striptags|trim ) %}

### For a screen reader user, 'Learn more' or 'Read more' does not describe what the link does or where it will take them.

A screen reader user might just hear _"Link {{ item.node.snippet|striptags }} "_. If that clearly indicates its purpose and where it will take the them, it is ok.  If it is vauge like, "Read more" or "Learn more", it won't make sense out of context and it must be changed.

__Visual location:__

![{{ item.node.snippet|striptags }} not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:

If it is vauge like, "Read more" or "Learn more", it won't make sense out of context and it must be changed. Or add invisible screen reader text.



{% else -%}

### I need a human! I'm not sure, but this link might not have a descriptive name to a screen reader.

If the link text and/or the image's alt text clearly indicate the links purpose and where it will take the them, the link is fine.

__Visual location:__

![{{ item.node.snippet|striptags }} not descriptive](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

#### HTML location:

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Ask does this link name make sense if no context is provided? If yes, this can be ignored.  If no, maybe the link is not necessary.  Check if the link already exists in another context. Or add screen reader only text inside the link.

{% endif -%}

{% include 'includes/other-options-w-details.md' %}

---
<br>

{% endfor %}

### FYI: What is 'invisible screen reader only' text?

{% include 'includes/link-name--sr-only--solution.md' %}

-
<br>