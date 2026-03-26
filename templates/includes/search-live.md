## Changes in search results must be announced to screen readers [WCAG 3.2.2](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#on-input) [WCAG 4.1.3](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-21/#413-status-messages-aa) 

When a screen reader initiates a search they need to be notified of changes to the page.

__FROM: <https://dci.dkso.dhe.duke.edu/blogs>__

__Visual location:__

![blog search live](assets/blog-search-live.png)

__HTML location:__

```html
<header>
    <p>1 - 12 of 202 posts</p>
</header>
```

When a search happens, we need it to announce that it happened in some way to screen readers so they know if the search was successful.

#### Suggested solution:

Add a `role="status"` attribute around an element that have search changes.


<br>

---

<br>

END