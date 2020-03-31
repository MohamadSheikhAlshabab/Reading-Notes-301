# Read-03:
---------

## Javascript Templating

 - Javascript Templating is a fast and powerful technology for presenting client-side presentation templates with Javascript
   using the JSON data source.

- __Mustache__:

![link](https://miro.medium.com/max/1400/1*P9q0tkeaRY2l1JOXaVKAig.png)
- is a logic-less template syntax. It can be used for HTML, config files, source code — anything. It works by expanding tags 
in a template using values provided in a hash or object.

- Mustache-Express
 To install:
With Yarn:
$ yarn add mustache-express
or with NPM:
$ npm install mustache --save

- Configure mustache-express in your server.js/app.js/index.js file:
![link](https://miro.medium.com/max/1400/1*ES10lxr7tdRFVEKcRAgLEw.png)
- Create a views folder and add some html view templates (e.g. hello.html):
![link](https://miro.medium.com/max/494/1*zwYE8a5rvAVZcBl9v1oqfA.png)
- ![link](https://miro.medium.com/max/1400/1*FRcL9NQHI7Cvi2ELLmzJGQ.png)
- Final output:
![link](https://miro.medium.com/max/1400/1*YaJ1vtsuwRMhfi8parlHOA.png)
-------------
## A Complete Guide to Flexbox

- __display__
  - This defines a flex container; inline or block depending on the given value. 
  - It enables a flex context for all its direct children.
  - .container {
  display: flex; /* or inline-flex */
}


- By default, flex items are laid out in the source order. However, 
 the order property controls the order in which they appear in the flex container.
  - .item {
  order: <integer>; /* default is 0 */
 }
  - ![link](https://css-tricks.com/wp-content/uploads/2018/10/order.svg)


- __Flexbox__
 is (aside from optional wrapping) a single-direction layout concept.
  - .container {
   flex-direction: row | row-reverse | column | column-reverse;
 }
  - ![link](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

  - row (default): left to right in ltr; right to left in rtl
row-reverse: right to left in ltr; left to right in rtl
column: same as row but top to bottom
column-reverse: same as row-reverse but bottom to top

- __flex-grow__
  - This defines the ability for a flex item to grow if necessary. 
  - It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.
  - .item {
  flex-grow: <number>; /* default 0 */
 }
  - ![link](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)
 
 - __flex-wrap__
   - By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.
   - .container{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
   - nowrap (default): all flex items will be on one line
wrap: flex items will wrap onto multiple lines, from top to bottom.
wrap-reverse: flex items will wrap onto multiple lines from bottom to top.
   - ![link}(https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

- __flex-shrink__
  -This defines the ability for a flex item to shrink if necessary.
  - .item {
  flex-shrink: <number>; /* default 1 */
}

- __flex-basis__
   - This defines the default size of an element before the remaining space is distributed.
   -  It can be a length or a keyword (auto ,main-size ,content )
   - .item {
  flex-basis: <length> | auto; /* default auto */
}

- __flex-flow__
  - This is a shorthand for the flex-direction and flex-wrap properties,
  which together define the flex container’s main and cross axes. 
  The default value is row nowrap.
  - flex-flow: <‘flex-direction’> || <‘flex-wrap’>
 
- __justify-content__ 
  - This defines the alignment along the main axis.
  - .container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe;
}
  - flex-start (default): items are packed toward the start of the flex-direction.
flex-end: items are packed toward the end of the flex-direction.
start: items are packed toward the start of the writing-mode direction.
end: items are packed toward the end of the writing-mode direction.
left: items are packed toward left edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
right: items are packed toward right edge of the container, unless that doesn’t make sense with the flex-direction, then it behaves like start.
center: items are centered along the line
space-between: items are evenly distributed in the line; first item is on the start line, last item on the end line
space-around: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
space-evenly: items are distributed so that the spacing between any two items (and the space to the edges) is equal.
 - ![link](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)
 
- __align-self__
   - This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.
   - .item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
   - Note that float, clear and vertical-align have no effect on a flex item.
   - ![link](https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg)
   
 - __align-items__
    - This defines the default behavior for how flex items are laid out along the cross axis on the current line.
    - .container {
  align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe;
}
   - stretch (default): stretch to fill the container (still respect min-width/max-width)
flex-start / start / self-start: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the flex-direction rules or the writing-mode rules.
flex-end / end / self-end: items are placed at the end of the cross axis. The difference again is subtle and is about respecting flex-direction rules vs. writing-mode rules.
center: items are centered in the cross-axis
baseline: items are aligned such as their baselines align
   - ![link](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)
   
 - __align-content__
    - This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.
    - .container {
  align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;
}
    - flex-start / start: items packed to the start of the container. The (more supported) flex-start honors the flex-direction while start honors the writing-mode direction.
flex-end / end: items packed to the end of the container. The (more support) flex-end honors the flex-direction while end honors the writing-mode direction.
center: items centered in the container
space-between: items evenly distributed; the first line is at the start of the container while the last one is at the end
space-around: items evenly distributed with equal space around each line
space-evenly: items are evenly distributed with equal space around them
stretch (default): lines stretch to take up the remaining space
   - ![link](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)
   
--------
