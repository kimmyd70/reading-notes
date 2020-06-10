##  CSS Grid

[Grid Garden](https://cssgridgarden.com/)

[CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)--good reference!

+ Determines a grid item’s location within the grid by referring to specific grid lines. `grid-column-start/grid-row-start` is the line where the item begins, and `grid-column-end/grid-row-end` is the line where the item ends

+ Values:

    - `<line>` can be a number to refer to a numbered grid line, or a name to refer to a named grid line

    - `span <number>` – the item will span across the provided number of grid tracks

    - `span <name>` – the item will span across until it hits the next line with the provided name

    - `auto` – indicates auto-placement, an automatic span, or a default span of one

+ shorthand for setting grid: `<grid-template-rows> / <grid-template-columns>`

+ Other useful: 
column-gap
row-gap
grid-column-gap
grid-row-gap

+ Can use `justify-self` and `align-self`

+ Shorthand: `place-self: align justify` (or single for both)

+ Also: `justify-items, align-items, place-items` or `justify-content, align-content, place-content`

+ When sizing rows and columns, you can use all the lengths you are used to, like px, rem, %, etc, but you also have keywords like min-content, max-content, auto, and perhaps the most useful, fractional units. grid-template-columns: 200px 1fr 2fr min-content;

+ You also have access to a function which can help set boundaries for otherwise flexible units. For example to set a column to be 1fr, but shrink no further than 200px: grid-template-columns: 1fr minmax(200px, 1fr);

+ There is repeat() function, which saves some typing, like making 10 columns: grid-template-columns: repeat(10, 1fr);

+ Combining all of these things can be extremely powerful, like grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));