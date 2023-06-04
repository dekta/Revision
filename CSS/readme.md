## What is the Box model in CSS? Which CSS properties are a part of it?

- In web development, the box model is a conceptual model that describes how the layout of an HTML element is calculated. Every HTML element can be considered as a rectangular box, with content, padding, border, and margin.
- The box model consists of the following parts:
- Content: The actual content of the HTML element, such as text, images, or video.
- Padding: The space between the content and the element's border. Padding can be used to add space between the content and the border, or to make the content appear larger.
- Border: The line that surrounds the element's content and padding. The border can be customized in terms of its style, width, and color.
- Margin: The space between the border of the element and the adjacent elements. Margin can be used to create space between elements or to separate them.

![CSS-BoxModel](https://www.csssolid.com/images/box-model/css-box-model.png)
 



## What is the z-index? What is the stacking context?
- z-index is a CSS property that determines the stacking order of positioned elements. It specifies the stack level of an element, relative to other elements on the same stacking context. Elements with higher z-index values will appear in front of elements with lower z-index values.
- A stacking context is an HTML element that contains a set of stacked, overlapping elements. Each stacking context has its own stacking order, which is determined by the z-index values of its child elements. The stacking context is created by certain CSS properties, including position: relative, position: absolute, position: fixed, position: sticky, and opacity (when it is less than 1).
- The stacking order of elements can be visualized as a three-dimensional stack, with each element occupying a layer in the stack. The z-index property determines the order of the layers, with higher values appearing in front of lower values.
- A stacking context is an element that contains a set of layers. Within a local stacking context, the z-index values of its children are set relative to that element rather than to the document root. Layers outside of that context — i.e. sibling elements of a local stacking context — can't sit between layers within it. If an element B sits on top of element A, a child element of element A, element C, can never be higher than element B even if element C has a higher z-index than element B.



## Difference between flex and grid? Where to use it?
- Flexbox is one-dimensional, while CSS Grid is two-dimensional.
- Flexbox is best for layouts that involve either rows or columns, while CSS Grid is best for layouts that involve both rows and columns.
- Flexbox is designed for laying out items in a container, while CSS Grid is designed for laying out the container itself.
- Flexbox provides more flexibility in distributing space among items in a container, while CSS Grid provides more control over the placement of items.


## Difference between ***display:none*** and ***visibility:hidden***
- "**display: none**" removes an element from the document flow entirely. This means that the element is not rendered and does not take up any space on the page. Additionally, any child elements of the hidden element are also hidden. If you inspect the HTML code, you won't see the element at all. This is useful when you want to completely remove an element from the page and don't want it to be visible or accessible in any way.
- "**visibility: hidden**", which is often confused with "display: hidden" (which is not a valid property), hides an element while still taking up space on the page. This means that the element is not visible, but its space is still reserved, and any child elements are also still present and hidden. If you inspect the HTML code, you will see the element but it will not be visible on the page. This is useful when you want to hide an element but still want it to occupy its space and be accessible in some way.



## What is the difference between position absolute, relative and fixed?
- **relative**: When an element is positioned as "relative", it is positioned relative to its normal position within the document flow. This means that the element will still take up space in the document flow, and other elements will not be repositioned based on its position. You can use top, right, bottom, and left properties to move it from its original position.
- **absolute**: When an element is positioned as "absolute", it is positioned relative to its nearest positioned ancestor element (i.e., an ancestor element that has a position value of "relative", "absolute", or "fixed"). If there is no positioned ancestor, then the element is positioned relative to the initial containing block (usually the viewport). Unlike "relative", an absolutely positioned element does not take up space in the document flow, and other elements can be positioned relative to it. You can use top, right, bottom, and left properties to specify the position of the element.
- **fixed**: When an element is positioned as "fixed", it is positioned relative to the viewport, and will remain in the same position even if the page is scrolled. This is useful for elements that you want to keep in a fixed position on the screen, such as navigation menus or headers. You can use top, right, bottom, and left properties to specify the position of the element.

- In summary, "relative" positioning is relative to the normal position of the element within the document flow, "absolute" positioning is relative to the nearest positioned ancestor, and "fixed" positioning is relative to the viewport.


### What is !important
- In CSS (Cascading Style Sheets), !important is a keyword that is used to give a style rule more weight than it would normally have in the cascade of styles. When !important is added to a CSS property value, it overrides any previous styles set for that property and makes the new style rule the most important one. This means that the style rule with !important will take precedence over other styles applied to the same element.



## Difference between reset vs normalize CSS?. How do they differ?
Reset CSS: CSS resets aim to remove all built-in browser styling. For example margins, paddings, font-sizes of all elements are reset to be the same. 

Normalize CSS: Normalize CSS aims to make built-in browser styling consistent across browsers. It also corrects bugs for common browser dependencies.


## What is the difference between inline, inline-block, and block?
Block Element: The block elements always start on a new line. They will also take space for an entire row or width. List of block elements are <div>, <p>.

Inline Elements: Inline elements don't start on a new line, they appear on the same line as the content and tags beside them. Some examples of inline elements are <a>, <span> , <strong>, and <img> tags. 

Inline Block Elements: Inline-block elements are similar to inline elements, except they can have padding and margins and set height and width values.



##  What are Pseudo elements and Pseudo classes?
Pseudo-elements allows us to create items that do not normally exist in the document tree, for example ::after.

```CSS
::before
::after
::first-letter
::first-line
::selection
```

In the below example, the color will appear only on the first line of the paragraph.

```CSS
p: :first-line {
	color: #ffOOOO;
	font-variant: small-caps;
}
```

Pseudo-classes select regular elements but under certain conditions like when the user is hovering over the link.

```CSS
:link
:visited
:hover
:active
:focus
```

Example of the pseudo-class, In the below example, the color applies to the anchor tag when it’s hovered.

```CSS
/* mouse over link */
a:hover {
	color: #FFOOFF;
}
```



##  How are the CSS selectors matched against the elements by the browser?
The order of matching selectors goes from right to left of the selector expression. The elements in the DOM are filtered by browsers based on the key selectors and are then traversed up to the parent elements for determining the matches. The speed of determining the elements depends on the length of the chain of selectors. Consider an example:

```CSS
 p span{ 
    color: black;
}
```

Here, the browser first finds all span elements in the DOM and then it traverses to each of its parent elements to check if they are the paragraph p elements.

Once the browser finds all matching span tags having paragraph elements as parent and applies the color of black to the content, the matching process is stopped.


## Can you name the four types of @media properties?
The four types of 
```CSS
@media All{}
@media Screen{}
@media Print{}
@media Speech{}
``` 
properties are:

**All** → It’s the default property. Used for all media-type devices.
**Screen** → Used for computer screen, mobile screen.
**Print** → Used for printers.
**Speech** → Used for screen readers.


## What is progressive rendering? How do you implement progressive rendering in the website?. What are the advantages of it?
Progressive rendering is the name given to techniques used to improve the performance of a webpage (in particular, improve perceived load time) to render content for display as quickly as possible.

We can implement the progressive rendering of the page by loading the **lazy loading of the images**.  We can use *Intersection Observer API* to lazy load the image. The API makes it simple to detect when an element enters the viewport and take an action when it does. Once the image enters the viewport, we will start loading the images.