## Charts.js and Canvas API


[charts.js](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

[charts.js Docs](https://www.chartjs.org/docs/latest/)

[canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)
  
[drawing shapes](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)

[styles and color](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

[drawing text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

+ Checkout the JavaScript plug-in `charts.js`; download and see article 1 for how to make line charts, pie charts, and bar charts

+ `Charts.js` specifics are in article 2

+ These charts work with `<canvas>` HTML elements

+ the `<canvas>` element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. 

+ suggested to use the `canvas` height/width attributes vs CSS to avoid distortion

+ Checkout article 3 for basic `<canvas>`...don't forget the req closing tag

+ `canvas` works on a grid system:
    - Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). 

+ Article 4 has all the syntax for drawing shapes...many attributes similar to Adobe nomenclature (stroke, etc)

+ Article 5 has all the syntax for style and color....many of these attributes are similar to Adobe nomenclature (fill, transparency, rgba, set line caps, etc)

+ Article 6 deals with text where you can set stroke, baseline, font, etc