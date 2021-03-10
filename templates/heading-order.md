## {{ audit.title }} [WCAG 2.4.6](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#headings-and-labels)

__I need a human!__ Manual Test: Are heading elements in a roughly hierarchical way

{% if audit.description %}

{{ audit.description|escape }}

{% endif %}

#### Suggested solution:

Review to ensure headings are use for content that deserves to be a heading. Avoid skipping levels. If unavoidable, they must be roughly hierarchical.

Barely acceptable example (note that H3 is skipped, but the rest are roughly hierarchical):

```html
<h1>The main page heading</h1>
<h2>A heading</h2>
<p>Text about the heading</p>
<h4>A skipped heading</h4>
<p>Text about the heading</p>
```

Non-compliant example (note that the headings are arbitrary and not in an accurate or helpful order):

```html
<h1>The main page heading</h1>
<h6>A heading</h6>
<p>Text about the heading</p>
<h2>A skipped heading</h4>
<p>Text about the heading</p>
```

---
