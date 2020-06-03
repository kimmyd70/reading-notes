## JQuery
------
JavaScript and jQuery book by Jon Duckett pages 293-301, 306-331 and 354-357

skim 332-335, 302-305

+ powerful library that gives simpler syntax at [JQuery](http://jquery.org)

+ use JQuery for selecting elements, performing tasks, and handling events

+ find elements using css-style selectors `$('li.hot)` and do something using JQuery methods `$('li.hot').addClass('complete');`

+ similar to DOM manipulation
+ different in:
    - cross-browser so no concerns about behavior
    - simple and more accurate selection of elements
    - event handling with one method
    - methods affect ALL the selected elements without looping
    - methods available for popular tasks
    - one selection can have multiple methods acting upon it
    - can select multiple elements such as `$('li')`
+ JQuery selection + returned object = JQuery "matched set"

+ the object stores a reference to the corresponding node in the DOM

+ Caching and object stores a reference to the object in a variable

+ If multiple objects are returned, JQuery methods "automatically" loop through all

+ You can chain several methods to one selector separated by `'.'`

+ JQuery.ready makes sure the page is ready for the code -- not necessary when script is before the `</body>` tag but can be a precaution in case someone moves the script

```
$(document).ready(function() {
    //script here
});
```

+ Methods get and set data

+ see P 314 for `ul` vs `li` behavior of each:
    - `.html()` returns the first element inside the matched set with IT'S descendants (or use `.each()` for all)

    - `.text()` returns the text of every element in the selection

!!! See p 315-331 for common ways to update/change elements, attributes, and css properties

!!! See p 326-331 for event handling using JQuery

!!! See p 302-303 for selecting elements and 304-305 for methods!!!

!! if loading from a CDN, use a fallback `document.write()` to ensure it loads in edge cases !!

``` 
<script src = "//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"> </script>

<script>
window.JQuery || document.write ('<script src = "js/jquery-1.10.2.js"></script>)
</script>
```
+ put scripts before the closing `</body>`
to help page load faster because the DOM has already loaded  by the time it executes


