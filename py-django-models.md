# Django Models

Models from [this article](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

- The definition of the model is independent of the underlying database 

- Once you've chosen what database you want to use, you don't need to talk to it directly at all

- You just write your model structure and other code, and Django handles all the dirty work of communicating with the database for you

- When designing your models it makes sense to have separate models for every "object" (a group of related information)

- You might also want to use models to represent selection-list options (e.g. like a drop down list of choices), rather than hard coding the choices into the website itself — this is recommended when all the options aren't known up front or may change

- Once we've decided on our models and field, we need to think about the relationships. Django allows you to define relationships that are one to one (OneToOneField), one to many (ForeignKey) and many to many (ManyToManyField)

- Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata

Example:
```
from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
```

### Fields
- A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables

- Each database record (row) will consist of one of each field value. 

****** See the article for common field arguments and field types ********

### Metadata
- You can declare model-level metadata for your Model by declaring class Meta

- One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type

****** See the article for common uses of and formats for metadata ********

### Methods
- Minimally, in every model you should define the standard Python class method `__str__()` to return a human-readable string for each object

-  This string is used to represent individual records in the administration site (and anywhere else you need to refer to a model instance)

- Often this will return a title or name field from the model.

****** See the article for method uses and formats  ********

### Using Model Classes
- Once you've defined your model classes you can use them to create, update, or delete records, and to run queries to get all records or particular subsets of records like:    

    - creating records
    - modifying records
    - searching for records
    
****** See the article for a full example of models and how they interact ********
___________________
_________________________
Admin from [this article](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)
__________________________

- The Django admin application can use your models to automatically build a site area that you can use to create, view, update, and delete records

- This can save you a lot of time during development, making it very easy to test your models and get a feel for whether you have the right data 

- The admin application can also be useful for managing data in production, depending on the type of website

- The Django project recommends it only for internal data management (i.e. just for use by admins, or people internal to your organization), as the model-centric approach is not necessarily the best possible interface for all users, and exposes a lot of unnecessary detail about the models 

- Admin steps to consider:
    - registering models
    - creating superuser
    - logging in/using the site
    - other advanced configurations listed in this article


****** See the article for a full discussion of admin applications ********

__________________________
[Beginner's Guide 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html)
_____________________
______________________
- Django is a Web framework written in Python. A Web framework is a software that supports the development of dynamic Web sites, applications, and services. 

- It provides a set of tools and functionalities such as security features, database access, sessions, template processing, URL routing, internationalization, localization, and much more.

- Supports Python libraries like those in the [Python Package Index](https://pypi.org/)

_______________________
[Beginner's Guide 2](https://simpleisbetterthancomplex.com/series/2017/09/11/a-complete-beginners-guide-to-django-part-2.html)
_______________________
