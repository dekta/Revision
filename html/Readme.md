### What is !important
- In CSS (Cascading Style Sheets), !important is a keyword that is used to give a style rule more weight than it would normally have in the cascade of styles. When !important is added to a CSS property value, it overrides any previous styles set for that property and makes the new style rule the most important one. This means that the style rule with !important will take precedence over other styles applied to the same element.


### What is the box model?
- In web development, the box model is a conceptual model that describes how the layout of an HTML element is calculated. Every HTML element can be considered as a rectangular box, with content, padding, border, and margin.
- The box model consists of the following parts:
- Content: The actual content of the HTML element, such as text, images, or video.
- Padding: The space between the content and the element's border. Padding can be used to add space between the content and the border, or to make the content appear larger.
- Border: The line that surrounds the element's content and padding. The border can be customized in terms of its style, width, and color.
- Margin: The space between the border of the element and the adjacent elements. Margin can be used to create space between elements or to separate them.


## What is the difference between position absolute, relative and fixed?
- relative": When an element is positioned as "relative", it is positioned relative to its normal position within the document flow. This means that the element will still take up space in the document flow, and other elements will not be repositioned based on its position. You can use top, right, bottom, and left properties to move it from its original position.
- "absolute": When an element is positioned as "absolute", it is positioned relative to its nearest positioned ancestor element (i.e., an ancestor element that has a position value of "relative", "absolute", or "fixed"). If there is no positioned ancestor, then the element is positioned relative to the initial containing block (usually the viewport). Unlike "relative", an absolutely positioned element does not take up space in the document flow, and other elements can be positioned relative to it. You can use top, right, bottom, and left properties to specify the position of the element.
- fixed": When an element is positioned as "fixed", it is positioned relative to the viewport, and will remain in the same position even if the page is scrolled. This is useful for elements that you want to keep in a fixed position on the screen, such as navigation menus or headers. You can use top, right, bottom, and left properties to specify the position of the element.

- In summary, "relative" positioning is relative to the normal position of the element within the document flow, "absolute" positioning is relative to the nearest positioned ancestor, and "fixed" positioning is relative to the viewport.



## the difference between display none and display hidden
- "display: none" removes an element from the document flow entirely. This means that the element is not rendered and does not take up any space on the page. Additionally, any child elements of the hidden element are also hidden. If you inspect the HTML code, you won't see the element at all. This is useful when you want to completely remove an element from the page and don't want it to be visible or accessible in any way.
- "visibility: hidden", which is often confused with "display: hidden" (which is not a valid property), hides an element while still taking up space on the page. This means that the element is not visible, but its space is still reserved, and any child elements are also still present and hidden. If you inspect the HTML code, you will see the element but it will not be visible on the page. This is useful when you want to hide an element but still want it to occupy its space and be accessible in some way.



## Difference between flex and grid? Where to use it?
- Flexbox is one-dimensional, while CSS Grid is two-dimensional.
- Flexbox is best for layouts that involve either rows or columns, while CSS Grid is best for layouts that involve both rows and columns.
- Flexbox is designed for laying out items in a container, while CSS Grid is designed for laying out the container itself.
- Flexbox provides more flexibility in distributing space among items in a container, while CSS Grid provides more control over the placement of items.




## What is BEM?
- BEM is a way to name and organize CSS classes that helps make your code easier to understand, maintain, and reuse. It divides your interface into small, reusable parts called "blocks" that can have "elements" and "modifiers" to change their appearance or behavior. Using BEM makes it easier to create consistent and modular code, and helps you understand how different parts of your interface are related.


## What is the z-index? What is the stacking context?
- z-index is a CSS property that determines the stacking order of positioned elements. It specifies the stack level of an element, relative to other elements on the same stacking context. Elements with higher z-index values will appear in front of elements with lower z-index values.
- A stacking context is an HTML element that contains a set of stacked, overlapping elements. Each stacking context has its own stacking order, which is determined by the z-index values of its child elements. The stacking context is created by certain CSS properties, including position: relative, position: absolute, position: fixed, position: sticky, and opacity (when it is less than 1).
- The stacking order of elements can be visualized as a three-dimensional stack, with each element occupying a layer in the stack. The z-index property determines the order of the layers, with higher values appearing in front of lower values.
- A stacking context is an element that contains a set of layers. Within a local stacking context, the z-index values of its children are set relative to that element rather than to the document root. Layers outside of that context — i.e. sibling elements of a local stacking context — can't sit between layers within it. If an element B sits on top of element A, a child element of element A, element C, can never be higher than element B even if element C has a higher z-index than element B.





## Briefly describe the correct usage of the following HTML5 semantic elements: <header>, <article>,<section>, <footer>
- <header> is used to contain introductory and navigational information about a section of the page. This can include the section heading, the author’s name, time and date of publication, table of contents, or other navigational information.

- <article> is meant to house a self-contained composition that can logically be independently recreated outside of the page without losing its meaning. Individual blog posts or news stories are good examples.

- <section> is a flexible container for holding content that shares a common informational theme or purpose.

- <footer> is used to hold information that should appear at the end of a section of content and contain additional information about the section. Author’s name, copyright information, and related links are typical examples of such content.
 
### Division of Tags Based On Their Usage
- Structural Tags: &lt;html>, &lt;head>', &lt;body>, &lt;div>, &lt;span>, &lt;header>, &lt;footer> 
- Text Formatting Tags: &lt;b>, &lt;i>, &lt;u>, &lt;small>, &lt;big>, &lt;strong>, &lt;code>, &lt;cite>
- Multimedia Tags: \<img\>, \<audio\>, \<video\>, \<canvas\>, \<svg\>, \<embed\>
- Input and Form Tags: \<form\>, \<input\>, \<textarea\>, \<legend\>, \<button\>, \<progress\>
- Semantic Tags: \<header\>, \<nav\>, \<main\>, \<article\>, \<section\>, \<footer\>, \<h1\> to \<h6\>
- Interactive Tags: \<a\>, \<button\>, \<input\>, \<select\>, \<textarea\>, \<summary\>, \<canvas\>
- Table Tags: \<table\>, \<thead\>, \<tbody\>, \<tfoot\>, \<tr\>, \<th\>, \<td\>, \<caption\>







