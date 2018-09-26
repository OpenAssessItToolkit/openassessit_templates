Screen reader only text is text that is read out-loud to a screen reader user, but not displayed on the screen. Most websites already have a class for this called `.element-invisible` or `.sr-only`. If this website does not, add this class to a stylesheet:

```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0,0,0,0);
  border: 0;
}
```

Example usage:

```html
<a class="read-more" href="fancy-cats.html">
    Read more
+    <span class="sr-only"> about fancy cats</span>
  </i>
</a>
```