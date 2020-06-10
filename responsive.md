## Responsive Web Design
(or....this aligns with how I was taught)

[this article for Grid](https://medium.com/samsung-internet-dev/common-responsive-layouts-with-css-grid-and-some-without-245a862f48df)

+ `grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));`

+ `object-fit: cover;`

+ The Holy Grail Layout (with no set heights!) 
    ```
    body {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    height: 100vh;  
    }
    ```
+ This will create a 3 by 3 grid with fixed width columns either side and a center row that stretches to fill the space left after the top and bottom rows take up their content’s space. Setting the header and footer to grid-column: span 3; will make them take up an entire row each. In the above example I’ve used flexbox and flex-direction: column; at small screen sizes. The main element can then be set to flex: 1; which will cause it to stretch to fill the height of the window. The lovely thing about this method is that not only does it easily allow scrolling of the page if the window height is short, but it also doesn’t require us to set a height on any of the internal elements, meaning that they can contain any content without causing problems to the layout/design.

[this article for general](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)

RWD has become more important now that people browse on smaller screens.

RWD, in my opinion, should take the place of developing mobile-only websites if a company has need for both mobile and desktop.  

The user shouldn't be subjected to a vastly different experience on mobile, but should see a pared-down version of the full site.

RWD is easily achieved with `@media` queries in CSS.

CSS3 introduced additional viewport language that makes RWD easier

![viewport in CSS3](./images/rel-viewport.png)

Hard media query breakpoints and column/container grid structures have been replaced with FLEX (you know this, Kim) and ...

![break point discussion](./images/breakpoints.png)