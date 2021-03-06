#  Django Forms

notes from [this article](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)

An HTML Form is a group of one or more fields/widgets on a web page, which can be used to collect information from users for submission to a server. 

Forms are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on.

Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.

Django Forms provides a framework to define forms and fields programmatically to generate the HTML form and handle much of the validation and user interaction.

Remember html:

```
<form action="/team_name_url/" method="post">
    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">
</form>
```
....include an action and a method 

-------------------

Django forms handle:

1. Display the default form the first time it is requested by the user.
    - The form may contain blank fields (e.g. if you're creating a new record), or it may be pre-populated with initial values (e.g. if you are changing a record, or have useful default initial values).
    - The form is referred to as unbound at this point, because it isn't associated with any user-entered data (though it may have initial values).
2. Receive data from a submit request and bind it to the form.
    - Binding data to the form means that the user-entered data and any errors are available when we need to redisplay the form.
3. Clean and validate the data.
    - Cleaning the data performs sanitization of the input (e.g. removing invalid characters that might be used to send malicious content to the server) and converts them into consistent Python types.
    - Validation checks that the values are appropriate for the field (e.g. are in the right date range, aren't too short or too long, etc.)
4. If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
5. If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)
6. Once all actions are complete, redirect the user to another page.

These actions come when you use the `Form` class similar to declaring a `Model`

For example:
```
from django import forms

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")
```

There are many common fields similar to model field classes (see article for list)

There are arguments common to most field types:

- `required`: If True, the field may not be left blank or given a None value. Fields are required by default, so you would set required=False to allow blank values in the form.
- `label`: The label to use when rendering the field in HTML. If a label is not specified, Django will create one from the field name by capitalizing the first letter and replacing underscores with spaces (e.g. Renewal date).
- `label_suffix`: By default, a colon is displayed after the label (e.g. Renewal date:). This argument allows you to specify a different suffix containing other character(s).
- `initial`: The initial value for the field when the form is displayed.
- `widget`: The display widget to use.
- `help_text` (as seen in the example above): Additional text that can be displayed in forms to explain how to use the field.
- `error_messages`: A list of error messages for the field. You can override these with your own messages if needed.
- `validators`: A list of functions that will be called on the field when it is validated.
- `localize`: Enables the localization of form data input (see link for more information).
- `disabled`: The field is displayed but its value cannot be edited if this is True. The default is False.

You can use `clean_<fieldname>()` to easily validate a single field

Using `ModelForm` you can also create a form from a single model you've already coded:
```
from django.forms import ModelForm

from catalog.models import BookInstance

class RenewBookModelForm(ModelForm):
    class Meta:
        model = BookInstance
        fields = ['due_back']
```

******** See the rest of the article for step-by-step form tutorial ********
