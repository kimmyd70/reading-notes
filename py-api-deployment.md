# API Deployment

Django Settings from [this article](https://djangostars.com/blog/configuring-django-settings-best-practices/)

SSH [tutorial](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)

Whitenoise[static files](http://whitenoise.evans.io/en/stable/)

[IaaS-Infrastructure as a Service](https://en.wikipedia.org/wiki/Infrastructure_as_a_service): online services that provide high-level APIs used to dereference various low-level details of underlying network infrastructure

[PaaS-Platform as a Service](https://en.wikipedia.org/wiki/Platform_as_a_service): or platform-based service is a category of cloud computing services that provides a platform allowing customers to develop, run, and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app

[CORS-Cross Origin Resourse Sharing](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing): is a mechanism that allows restricted resources on a web page to be requested from another domain outside the domain from which the first resource was served

______________

Django `settings.py`: set and extend environment settings per project

`settings/local.py` extends basic approach to make settings available to other developers

- Run the project with `python manage.py runserver --settings=settings.local`

- shared tokens/passwords

Use environment variables for best practice

_______________

### 12 Factors 

a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.

As the name suggests, the collection consists of twelve parts:

1. Codebase
2. Dependencies
3. Config
4. Backing services
5. Build, release, run
6. Processes
7. Port binding
8. Concurrency
9. Disposability
10. Dev/prod parity
11. Logs
12. Admin processes

[READ MORE](https://12factor.net/)

_________

Use Django environ 
```
import environ


root = environ.Path(__file__) - 3  # get root of the project
env = environ.Env()
environ.Env.read_env()  # reading .env file

SITE_ROOT = root()

DEBUG = env.bool('DEBUG', default=False)
TEMPLATE_DEBUG = DEBUG

DATABASES = {'default': env.db('DATABASE_URL')}

public_root = root.path('public/')
MEDIA_ROOT = public_root('media')
MEDIA_URL = env.str('MEDIA_URL', default='media/')
STATIC_ROOT = public_root('static')
STATIC_URL = env.str('STATIC_URL', default='static/')

SECRET_KEY = env.str('SECRET_KEY')

CACHES = {'default': env.cache('REDIS_CACHE_URL')}
```

and .env file
```
DEBUG=True

DATABASE_URL=postgres://user:password@db.example.com:5432/production_db?sslmode=require

REDIS_CACHE_URL=redis://user:password@cache.example.com:6379/1

SECRET_KEY=Some-Autogenerated-Secret-Key
```
___________

### Django Settings: Best practices

1. Keep settings in environment variables.

2. Write default values for production configuration (excluding secret keys and tokens).

3. Don’t hardcode sensitive settings, and don’t put them in VCS.

4. Split settings into groups: Django, third-party, project.

5. Follow naming conventions for custom (project) settings.

__________

### SSH

SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet. 

It provides a mechanism for authenticating a remote user, transferring inputs from the client to the host, and relaying the output back to the client.

The significant advantage offered by SSH over its predecessors is the use of encryption to ensure secure transfer of information between the host and the client. Host refers to the remote server you are trying to access, while the client is the computer you are using to access the host. There are three different encryption technologies used by SSH:

1. Symmetrical encryption (shared key): where a secret key is used for both encryption and decryption of a message by both the client and the host

2. Asymmetrical encryption: uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key.

3. Hashing: One-way hashing is another form of cryptography used in Secure Shell Connections. One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that shows no clear trend which can exploited. This makes them practically impossible to reverse.

