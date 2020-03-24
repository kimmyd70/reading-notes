![CSS header](images/css.png)

Notes re: CSS
(p.s. I'm familiar with css from previous schooling)


CSS is usually in a separate doc, although they can be embedded

Use CSS simplest/most overarching rulesto format the way you want--apply to classes, etc vs every single element

Share style sheets between different pages: advantage to making CSS separate doc

p {font-family: Arial;}
hi {font-family: Arial;
    color: yellow;}
CSS Elements include the 
+ selector (p, h1)
+ declaration (font family...)
+ property (color
+ value (yellow))

Use external CSS with a link
+ type
+ href
+ rel

Use **inline** CSS with style tag on the semantic tag <p style=...>

Use **internal** CSS with style in HEAD same syntax as external style doc p{...}

See p 238 for selectors

![selectors](https://user-images.githubusercontent.com/61428656/75612706-fcde0300-5ada-11ea-9d12-02edcae7ab8a.png)
)

Cascading
+ Last rule: if thow selectors are identical, last takes precedence
+ Specificity: the more specific rule takes precedence
+ ~Add !important after any property value to apply first~ (bad practice)

Inheritance
+ Children inherit property values from parents
+ Force inheritance by using inherit language: {padding: inherit;}

Different browsers may display different css quirks or bugs--simple is better
+ Can use css reset to reset for browser agnostic (from Ryan G--look this up)

Look at syntax on colors Ch11 when needed; limit color palette! KISS.  Look at accessibility color palettes
+ Remember contrast 3:1 (or 7:1) for UI/UX accessibility
