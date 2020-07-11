## EJS Partials

[this Medium article](https://medium.com/@henslejoseph/ejs-partials-f6f102cb7433)

A way to make code snippets that are reusable

Usefull for headers, footers, any common block you want on more than one page.  Example:
```
    <div class="header clearfix">
        <nav>
            <ul class="nav nav-pills pull-right">
                <li role="presentation"><a href="/">Home</a></li>
            </ul>
            <h3 class="text-muted">Node.js Blog</h3>
        </nav>
    </div>

```
Note: The <%- %> tags allow us to output the unescaped content onto the page (notice the -). This is important when using the include() statement since you don’t want EJS to escape your HTML characters like ‘<’, ‘>’, etc…

