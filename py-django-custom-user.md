# Django Custom User

reading notes from [this articl](https://learndjango.com/tutorials/django-custom-user-model)

Django ships with a built-in [User model](https://docs.djangoproject.com/en/3.1/ref/contrib/auth/#django.contrib.auth.models.User) for authentication and if you'd like a basic tutorial on how to implement log in, log out, sign up and so on see the [Django Login and Logout tutorial](https://learndjango.com/tutorials/django-login-and-logout-tutorial) for more.

However, for a real-world project, the official Django documentation highly recommends using a custom user model instead. This provides far more flexibility down the line so, as a general rule, always use a custom user model for all new Django projects.

_______________________

IMPORTANT:  create project but do not run migrate until AFTER creating custom user 

______________________

### AbstractUser vs AbstractBaseUser

Use AbstractUser: subclass of AbstractBaseUser with more default configuration

### Custom User Model

4 steps: 

***** See the article for specific `settings.py` changes *****

1. update config/settings.py

2. create a new CustomUser model

3. create new UserCreation and UserChangeForm

4. update the admin

__________

### Create Superuser

helpful to login into admin and test log in/out

____________


*** See the article for updates to `templates`, `views`, `URLs`

_________

Once the custom user model is configured you can easily and at any time add additional fields to it

__________

Check out [DjangoX](https://github.com/wsvincent/djangox), which is an open-source Django starter framework that includes a custom user model, email/password by default instead of username/email/password, social authentication, and more.

______________

Check out [Substituting a custom user mode](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#auth-custom-user)

Also checkout the videos listed in this assignment:

[Create Custom User](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)

[Abstract User, Profiles, and Signals](https://www.youtube.com/watch?v=EudKs1HPUfE)
