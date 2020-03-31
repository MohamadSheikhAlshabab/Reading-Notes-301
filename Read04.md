# Read-04:

--------

## RegEx:
 - __capturing group__: Groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
   - Example
(ha)+
hahaha haa hah!
    - Creates a capturing group that can be referenced via the specified name.
 
 -----------
 
 - __character set__: Match any character in the set.
   - [aeiou]
glib jocks vex dwarves!

   - __Range__: Matches a character having a character code between the two specified characters inclusive.
   - Example
[g-s]
abcdefghijklmnopqrstuvwxyz

----------

- __Dot__: Matches any character except linebreaks. Equivalent to [^\n\r].
  - Example
.
glib jocks vex dwarves!

--------

- __match any__: An alternative is [^], but it is not supported in all browsers.
  - Example
[\s\S]
glib jocks vex dwarves!

-----------

- __Word__: Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters). 
  Equivalent to [A-Za-z0-9_]
  - Example
\w
bonjour, mon frère

---------

- __not word__: Matches any character that is not a word character (alphanumeric & underscore). Equivalent to [^A-Za-z0-9_].
  - Matches any character that is not a word character (alphanumeric & underscore). Equivalent to [^A-Za-z0-9_]
__________
- __digit__: Matches any digit character (0-9). Equivalent to [0-9].
  - Example
\d
+1-(444)-555-1234
____________
- __not digit__ Matches any character that is not a digit character (0-9). Equivalent to [^0-9].
  - Example
\D
+1-(444)-555-1234

______________
- __whiteSpace__: Matches any whitespace character (spaces, tabs, line breaks).
  -Example
\s
glib jocks vex dwarves!

______________
- __no white Space__:Matches any character that is not a whitespace character (spaces, tabs, line breaks).
  - Example
\S
glib jocks vex dwarves!
_____________
- __unicode category__ :Matches a character in the specified unicode category. For example, \p{Ll} will match any lowercase letter.
  - Requires the u flag.
_______________

- __not unicode category__ : Matches any character that is not in the specified unicode category.
__________

- __unicode script__: Matches any character in the specified unicode script. For example, \p{Arabic} will match characters in the Arabic script.
___________
- __not unicode script__: Matches any character that is not in the specified unicode script.

_______________

## A Complete Guide to Grid:

- __display__: Defines the element as a grid container and establishes a new grid formatting context for its contents.
  - grid – generates a block-level grid 
  - inline-grid – generates an inline-level grid
  
  _______
- grid-column-start
- grid-column-end
- grid-row-start
= grid-row-end  
  - Values:

  - <line> – can be a number to refer to a numbered grid line, or a name to refer to a named grid line
  - span <number> – the item will span across the provided number of grid tracks
  - span <name> – the item will span across until it hits the next line with the provided name
  - auto – indicates auto-placement, an automatic span, or a default span of one
  - EX: .item-a {
  grid-column-start: 2;
  grid-column-end: five;
  grid-row-start: row1-start;
  grid-row-end: 3;
}
  - ![link](https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row-start-end-01.svg)
  - EX: .item-b {
  grid-column-start: 1;
  grid-column-end: span col4-start;
  grid-row-start: 2;
  grid-row-end: span 2;
}
 - ![link](https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row-start-end-02.svg)
 ______________
 - grid-template-columns
 - grid-template-rows
   - Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size,
     and the space between them represents the grid line.
   - Values:

<track-size> – can be a length, a percentage, or a fraction of the free space in the grid (using the fr unit)
<line-name> – an arbitrary name of your choosing
___________
- grid-area : Gives an item a name so that it can be referenced by a template created with the grid-template-areas property.
 Alternatively, this property can be used as an even shorter shorthand for grid-row-start + grid-column-start + grid-row-end + grid-column-end.
  - Values:

<name> – a name of your choosing
<row-start> / <column-start> / <row-end> / <column-end> – can be numbers or named lines
_________________
 - grid-template-areas : 
  - Defines a grid template by referencing the names of the grid areas which are specified with the grid-area property. 
   Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell.
   The syntax itself provides a visualization of the structure of the grid.
  - Values:

<grid-area-name> – the name of a grid area specified with grid-area
. – a period signifies an empty grid cell
none – no grid areas are defined
_______________
- justify-self: Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis).
This value applies to a grid item inside a single cell.
- Values:

start – aligns the grid item to be flush with the start edge of the cell
end – aligns the grid item to be flush with the end edge of the cell
center – aligns the grid item in the center of the cell
stretch – fills the whole width of the cell (this is the default)
___________
- grid-template:
  - A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.
  - Values:

none – sets all three properties to their initial values
<grid-template-rows> / <grid-template-columns> – sets grid-template-columns and grid-template-rows to the specified values, respectively, and sets grid-template-areas to none
___________
- align-self:
  - Aligns a grid item inside a cell along the block (column) axis (as opposed to justify-self which aligns along the inline (row) axis). This value applies to the content inside a single grid item.
  - Values:

start – aligns the grid item to be flush with the start edge of the cell
end – aligns the grid item to be flush with the end edge of the cell
center – aligns the grid item in the center of the cell
stretch – fills the whole height of the cell (this is the default)
_________
- grid-column-gap
- grid-row-gap
   - Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.
   - Values:

<line-size> – a length value
_________________
 - grid-gap
   - A shorthand for grid-row-gap and grid-column-gap
   - Values:

<grid-row-gap> <grid-column-gap> – length values
_______________
- place-self
  - place-self sets both the align-self and justify-self properties in a single declaration.
  - Values:

auto – The “default” alignment for the layout mode.
<align-self> / <justify-self> – The first value sets align-self, the second value justify-self. If the second value is omitted, the first value is assigned to both properties.
____________
- justify-items :
  - Aligns grid items along the inline (row) axis (as opposed to align-items which aligns along the block (column) axis). This value applies to all grid items inside the container.
  - Values:

start – aligns items to be flush with the start edge of their cell
end – aligns items to be flush with the end edge of their cell
center – aligns items in the center of their cell
stretch – fills the whole width of the cell (this is the default)
___________
- align-items
  - Aligns grid items along the block (column) axis (as opposed to justify-items which aligns along the inline (row) axis). This value applies to all grid items inside the container.
  - Values:

start – aligns items to be flush with the start edge of their cell
end – aligns items to be flush with the end edge of their cell
center – aligns items in the center of their cell
stretch – fills the whole height of the cell (this is the default)
_________________

- place-items 
  - place-items sets both the align-items and justify-items properties in a single declaration.
  - Values:

<align-items> / <justify-items> – The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.
________________
- justify-content
   - Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the inline (row) axis (as opposed to align-content which aligns the grid along the block (column) axis).
   - Values:

start – aligns the grid to be flush with the start edge of the grid container
end – aligns the grid to be flush with the end edge of the grid container
center – aligns the grid in the center of the grid container
stretch – resizes the grid items to allow the grid to fill the full width of the grid container
space-around – places an even amount of space between each grid item, with half-sized spaces on the far ends
space-between – places an even amount of space between each grid item, with no space at the far ends
space-evenly – places an even amount of space between each grid item, including the far ends
_____________
- align-content 
  - Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the block (column) axis (as opposed to justify-content which aligns the grid along the inline (row) axis).
  - Values:

start – aligns the grid to be flush with the start edge of the grid container
end – aligns the grid to be flush with the end edge of the grid container
center – aligns the grid in the center of the grid container
stretch – resizes the grid items to allow the grid to fill the full height of the grid container
space-around – places an even amount of space between each grid item, with half-sized spaces on the far ends
space-between – places an even amount of space between each grid item, with no space at the far ends
space-evenly – places an even amount of space between each grid item, including the far ends
_____________
- grid
   - A shorthand for setting all of the following properties in a single declaration: grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow (Note: You can only specify the explicit or the implicit grid properties in a single grid declaration).
   - Values:

 none – sets all sub-properties to their initial values.
 <grid-template> – works the same as the grid-template shorthand.
 <grid-template-rows> / [ auto-flow && dense? ] <grid-auto-columns>? – sets grid-template-rows to the specified value. If the auto-flow keyword is to the right of the slash, it sets grid-auto-flow to column. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-columns is omitted, it is set to auto.
 [ auto-flow && dense? ] <grid-auto-rows>? / <grid-template-columns> – sets grid-template-columns to the specified value. If the auto-flow keyword is to the left of the slash, it sets grid-auto-flow to row. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-rows is omitted, it is set to auto.

 
