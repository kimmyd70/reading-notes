![flexbox pic](images/html.jpg)

# HTML Process & Design, Layout, Structure, & Mark-up

### Layout (see CH 15 for float, flex, postioning, etc)

HTML is used to structure the document into sections and areas.  Ch 15 talks about grid layouts

Semantic tags are new with HTML 5.  They have been added to make code more readable and intuitive.  These are discussed on 433-442.: (bold are new to me)

+ header and footer
+ nav
+ article (text box section)
+ aside (inside article has related but not key info; outside contains content rel to the entire page)
+ section (group stuff together like old div)
+ **hgroup** group together h1-6 elements to appear as one single heading (controversial use)
+ **figure** (images, videos, graphs, diagrams, code samples, supporting text)and contains **figcaption**
+ div = newly used as "other"
+ **a** wrap now allows block and child elements to be used as a link

For old browsers, use this
'header.section.footer.aside.nav.article.figure.figcaption{ display: block;} to force block instead of default inline (IE9 requires more workarounds)

### Process & Design
(steps to develop a site map and wireframe)

First, determine your target audience

Next look at "why" and what your audience is trying to achieve--think about key motivations and specific goals

Look at what info they need and how often they will visit

Review design elements p465-472

### Extra Mark-up

+ "<!-- -->" html comment
+ "/*  */" css comment
+ "//  //" js comment

Remember to start with doctype statement

+ ID attributes:  css #
+ Class attributes: css .

Review ways to set up block v inline 185-186

see **escape characters** 193-194.  Need \ if used in string. "Kim\'s"

Other extra mark-up: div, span, iframe, meta