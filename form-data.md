## Sending Form Data

[this article](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)

- The `<form>` element defines how data is sent between client and server.  The attributes give specifics

    - action:  if left blank, data is sent to the same page the form is present on

    - action can also be a link to another page (like with our book_app)

    - method: defines how data is sent using GET or POST (only)

    - GET appends the data to the URL in key/value pairs.  Data access is in `request.query`

    - POST is used to talk to the server and request data.  Data access is in the `request.body`

    - You can use the Network area of the console to see responses (and errors) from your form and what Headers are used.

    This article has links to securing a web application
    ```
    Server-side website programming first steps

    The Open Web Application Security Project (OWASP)

    Web Security by Mozilla
    ```

    This article has links to some very useful deep dives into topics like:
    ```
    Your first form

    How to structure a web form

    Basic native form controls

    The HTML5 input types

    Other form controls

    Styling web forms

    Advanced form styling

    UI pseudo-classes

    Client-side form validation

    Sending form data

    ```