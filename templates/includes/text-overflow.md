


## Text Spacing [WCAG 1.4.12](https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html)

The intent of this Success Criterion (SC) is to ensure that when people override author specified text spacing to improve their reading experience, content is still readable and operable. 

[See example at bottom here](https://dequeuniversity.com/resources/wcag2.1/1.4.12-text-spacing#:~:text=Bad%20example%3A%20Text%20overflows%20container%20when%20respaced)

This SC does not dictate that authors must set all their content to the specified metrics. Rather, it specifies that an author's content has the ability to be set to those metrics without loss of content or functionality. 

In short, some people who are dyslexic use custom local stylesheets to override the website's default font settings.  

This usually happens when a static `height` or `max-height` is set.

If the user changes their font size, none of the content should be hidden.  Unless there is a way to view more of the content via a "Show more" button.

This content is in an iframe. If a user implements a custom local stylesheet override it would only apply to parts of the website, it would not continue into the iframe.

#### Suggested solution:

Option 1: 

Use an ellipsis to abbreviate the content, so it is not hidden.

Then use the recommended font "text spacing" settings as default so you don't have to do anything else.

1. Line height (line spacing) to at least 1.5 times the font size;
1. Spacing following paragraphs to at least 2 times the font size;
1. Letter spacing (tracking) to at least 0.12 times the font size;
1. Word spacing to at least 0.16 times the font size.

```css
p, div, h1,h2,h3,h4,h5 {
  line-height: 1.5;
  letter-spacing: 0.12em;
  word-spacing: 0.16em;
}
p {
  padding-bottom: 2;
}
```

Option 2:

Add a "View more" button that will expand the area so it can be fully read.

Option 3:

Make all the content in the boxes stretch to the full height necessary to show all the text. You may be able to keep the boxes the same height using CSS flexbox or some type of grid system.



<br>

---

<br>

END