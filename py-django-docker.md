#  Django REST and Docker

notes from [this article](https://wsvincent.com/beginners-guide-to-docker/)

Docker isolates and runs applications no matter the OS

The entire development environment is isolate: programming language, sofware packages, database, etc

No need for virtual environment; works on Linux containers for virtualization.  Also known as containerization

Docker is a way to implement Linux containers

[Download](https://www.docker.com/get-started)

The important takeaways from this tutorial are this:

1. Docker is a way to run Linux containers

2. Containers are a lightweight alternative to Virtual Machines

3. Dockerfile is a list of instructions for creating an image

4. Images are made up of one or more layers

5. Containers are a running instance of an image docker-compose.yml controls how to run the container

6. Containers are stateless and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases (which we didn’t cover here).


