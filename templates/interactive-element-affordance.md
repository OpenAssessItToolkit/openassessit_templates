## {{ audit.title }}  [WCAG 1.4.1](https://www.w3.org/WAI/WCAG21/quickref/#use-of-color) [WCAG 1.3.3](https://www.w3.org/WAI/WCAG21/quickref/#sensory-characteristics)


__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

Pay special attention to buttons and links.  For example, links and buttons should have obvious :hover and :focus states that meet WCAG 2.0 AA contrast requirements.

__Explanation (must watch):__

<iframe width="560" height="315" src="https://www.youtube.com/embed/JJ6rMXgVDZY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Suggested solution:

Add a hover state.  _They don't need to be the ones suggested below._ They do need to be [distinguishable](https://cloudfour.com/thinks/designing-button-states/). 


{% endif -%}

---

