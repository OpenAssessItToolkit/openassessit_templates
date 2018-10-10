## The Carousels Are Not Keyboard Accessible

### Slideshows/ Carousels are not screenreader accessible.

Keyboard accessibility is one of the most important aspects of web accessibility. Many users with motor impairments or lack fine muscle controls also rely on a keyboard. Blind users also typically use a keyboard for navigation. [Learn more](https://webaim.org/techniques/keyboard/)

__What are carousels?__
Carousels show a collection of items one at a time. They are also known as “slideshows” and “sliders”. Typical uses of carousels include scrolling news headlines, featured articles on home pages, and image galleries.

__Requirements to make a carousel compliant__

- Users must be able to pause carousel movement because it can be too fast or distracting, making text hard to read.
- All functionality, including navigating between carousel items, must be operable by keyboard.
- Changes to carousel items must be communicated to all users, including screen reader users.
- It must contain next and back buttons.
- It must contain indicators on how many slides exist.

Note: The usefulness of using carousels to convey information is disputed from a usability perspective because their content can be hard to discover. 


#### Suggested solution:

It looks like the website is using the Owl Carousel in a few places.  There are some projects that can enhance the accessibility of the Owl Carousel to make it compliant. Please try to implement the following fixes to remediate the issues.

<https://github.com/rtrvrtg/owlcarousel2-a11ylayer>

<https://codepen.io/AlexRebula/pen/yOjVvY>