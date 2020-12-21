## Dependency Injection

notes from [this article]()

>In software engineering, dependency injection is a technique whereby one object (or static method) supplies the dependencies of another object. A dependency is an object that can be used (a service).

For example: When class A uses some functionality of class B, then its said that class A has a dependency of class B.

Transferring the task of creating the object to someone else and directly using the dependency is called `dependency injection`.

Dependencies can be injected at runtime rather than at compile time.

There are basically three types of dependency injection:
1. Constructor injection: the dependencies are provided through a class constructor.

2. Setter injection: the client exposes a setter method that the injector uses to inject the dependency.

3. Interface injection: the dependency provides an injector method that will inject the dependency into any client passed to it. Clients must implement an interface that exposes a setter method that accepts the dependency.

If there is any change in objects, then DI looks into it and it should not concern the class using those objects. This way if the objects change in the future, then its DI’s responsibility to provide the appropriate objects to the class.

>The DI manages creation of the objects, knowing which classes require those objects, and provide them all those objects

SOLID Principles of OOP (R.C. Martin):

- Single responsibility
- Open–closed
- Liskov substitution
- Interface segregation
- Dependency inversion

Dependency Injection fits the 5th principle in that
>A class should be built on abstraction (not hard-coded). It should not configure its dependencies statically but should be configured by some other class from outside

| Advantages  | Disadvantages |
| ----------- | ----------- |
| Helps in Unit testing | Complex to learn |
|Reduces boiler plate code is reduced  | Many compile time errors are pushed to run-time |
|Easier application extension|  Can hinder use of IDE automation |
|Enables loose coupling used in application programming|   Can lead to management issues| 
3rd party libraries available | |
