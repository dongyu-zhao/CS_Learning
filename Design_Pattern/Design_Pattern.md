# Strategy Pattern
### Key Idea:
Use  has-a strategy design instead of  is-a inheritance hierarchy to
### Definition:
* Define a family of different algorithms and encapsulate them individually
* Independently from the client which uses the algorithm
* No code change to Client class itself when adding or changing algorithm, different client use different configuration when setup(initialization)
* Strategy only does one thing, have one operation
### UML:
https://lucid.app/lucidchart/invitations/accept/inv_cd4fd193-19ce-454c-9d33-65df36515d6f
### Problem want to solve:
This is mainly used for very flexible system where inheritance hierarchy can't solve. The problem is: different implementation of the same behavior is kept in one subclass which is hard for others in the same level to re-use
### Example:
Different ducks which has different strategy for bark behavior

# Observer Pattern/Subscribe Pattern
### Key Idea:
Use push instead of poll for subscription.
### Definition:
* 1 to many relationship between an observable/subject and observers
* Once there's a change in observable/subject, it notify all observers
### UML:
https://lucid.app/lucidchart/invitations/accept/inv_4be5a425-5388-4f97-8789-f06b0692eb77?viewport_loc=-449%2C-79%2C2219%2C1077%2C0_0
### Problem want to solve:
Avoid high request from consistently query from all observers.
### Example:
Weather station and many device which subscribe temperature change service

# Decorator Pattern
### Key:
* Wrap an object with the decorator and add some operation to the object using a recursion way
* Decorator both is an object and has an object
* The operation implemented in ConcreteClass return basic functionality, operation implemented in DecorateClass return its subject's functionality plus itself functionality
* Decorator varies in different function extension
* Decorators can be applied any number, any times and any order
* For m decorators, it reduce maximum 2 ^ m classes to m classes
### Definition:
* Attach extra responsibility to an object dynamically
* Provide alternate to expand functionality
### UML:
https://lucid.app/lucidchart/invitations/accept/inv_5f375aa3-912a-4ed1-9f06-b5498b03fbd0?viewport_loc=-11%2C131%2C2219%2C1077%2C0_0
### Problem want to solve:
Dynamically (at run time when initialize) apply different extensions to an object in different use case
### Example:
Java InputStream, BufferInputStream, AudioInputStream

# Factory Pattern
## Factory Method
### Key:
* Define different initialization implementation of a single instance in the same Factory interface/abstract class
* Each ConCreteFactory return only one Instance
### Definition:
Defines an interface that create an instance but let subclass decide which classes is created
### UML:
https://lucid.app/lucidchart/invitations/accept/inv_a871431a-54fe-4afc-a2be-f6120bc9e916?viewport_loc=-91%2C251%2C2219%2C1077%2C0_0
### Problem Want to Solve:
Have an isolated place to define different initialize logic, aim for the better code reuse 
### Example:
Forest simulation
## Abstract Factory
### Key:
* Define different initialization implementation of a family or a bunch of related instances in the same Factory interface/abstract class
* Each ConcreteFactory return multiple instances
* This is applied for situation where only some specific combinations are useful for all related instances.
### Definition:
Provide an interface to create a family of related/dependent instances without specify concrete classes
### Example:
UI combinations for different platform

# Singleton
### Key:
* global static object
* private constructor which mean no way to create new instance
* Initialize the instance when it's first called and get the same object for further reference
### Problem:
* Concern of the global object without any scope. This is dangerous especially for the instance is mutable and might be changed by others which the user might not know.
* You never know whether it needs a second or more instances in the future
* Need some special implementation for being thread-safe

# Command Pattern
### Key:
* It's about the design of the request, not the receiver nor commander.
* Command itself need the execute and unexecute method for easily rollback
* When initialize the command, pass the receiver to the command, and the command should be self independent and complete, so no pass need to pass to run the execute or unexecute method.
### Definition:
Encapsulate commands to an object which let you parameter other objects with different request, queue or log requests
### UML:
https://lucid.app/lucidchart/invitations/accept/inv_d9a54196-4574-4aa9-ac84-0591ba1372aa?viewport_loc=-11%2C-245%2C2219%2C1077%2C0_0
### Problem Want to Solve
Encapsulate the requests and make the rollback easily
### Example
Smart home

# Adapter Pattern
### Key
* It only makes two interface compatible, it actually not change any behavior or add behavior at all
* It just wrap up the client with an interface we owned in case that 1) when in the future we want to change to use another source, we no need to make change directly in the client class, but in the adapter class. 2) the client code is more generous which is better for code reuse.
### Definition:
Converts an interface to another interface
### UML:
https://lucid.app/lucidchart/invitations/accept/inv_f96f877e-c8a7-41d6-940d-7dc97555b961?viewport_loc=-11%2C-397%2C2219%2C1077%2C0_0
### Example
Changeable ThirdParty package

# Facade Pattern
### Key:
* Encapsulate a bunch of classes into one interface to make the code reusable
* Interface provide need to be simple, and hide complex interaction of different classes under it
* Reduce the dependency of the facade interface
### Definition:
serves as a front-facing interface masking more complex underlying or structural code
### UML:
![Example of Facade design pattern in UML.png](https://upload.wikimedia.org/wikipedia/en/5/57/Example_of_Facade_design_pattern_in_UML.png)
### Problem Want to Solve
* Make a complex system easier to use by define a simple interface
* The dependencies on a subsystem should be minimized.
### Example:
computer start

# Proxy Pattern
### Key:
* Proxy is just one layer of the decorator, you could have different decorators implements an abstract decorator, for proxy, it didn't share the same interface, it's a simpler and less various version of the decorator pattern
* Mainly used to control the access
* Unlike adaptor pattern, it didn't change the source interface
* If you have a chained proxy pattern, the order of each proxy do matter, not like the decorator pattern.
### Definition
* Remote: Control interaction of some outside resource
* Virtual: Control access of resources which is expensive to create (like cache)
* Protection: Control access to a resource based on permission
### UML
https://lucid.app/lucidchart/invitations/accept/inv_45ff2464-a923-4ec0-ace7-d111cca453fa?viewport_loc=-11%2C-11%2C2219%2C1108%2C0_0
### Example:
Lazy load

# Bridge Pattern
### Key:
* The aim of this design is to be more flexible for future changing (adding some concrete implementation
* Could combine with adapter pattern to make the implementation vary a lot (to different interfaces)
* For m object As and n object Bs, it reduce maximum m * n classes to m + n classes
* In the structure, it's a more complicated version of strategy pattern, besides different implementations, you could also have different abstractions
### Definition:
Decouple abstraction from implementation so that the two can vary independently
### UML
https://lucid.app/lucidchart/invitations/accept/inv_4b85d44f-07f2-4294-8c9a-fc1a392f9aa1?viewport_loc=-11%2C-11%2C2219%2C1077%2C0_0
### Example:
Website view and resource

# Template Pattern
### Key:
* This utilize inheritance instead of composition, so the template structure should be fixed and unchanged
* Hooks operation can be implemented by this pattern
* This could be replaced by multiple strategy patterns to give more flexible of the template
### Definition:
Define the skeleton of the algorithm and defer the implementation to subclasses which let the subclasses could change different step in the algorithm without changing the interface
### UML
https://lucid.app/lucidchart/invitations/accept/inv_f80a2149-d3c0-4032-bc76-a438c21a26dc?viewport_loc=-11%2C-59%2C2219%2C1077%2C0_0
### Example
hooks operation, poster

# Composite Pattern
### Key:
* Tree hierarchy
* All of the composition an single object share the same functionality
### Definition:
Make composite structures to a tree structure so that single object or composite objects could be treat uniformly.
### UML
https://lucid.app/lucidchart/invitations/accept/inv_16c7f173-4912-4abf-be02-03990ca2796b?viewport_loc=-247%2C288%2C2219%2C1077%2C0_0
### Example
MVC render()

# Iterator Pattern
### Key:
* Support lazy execution
* Support to construct infinte collections
* Treat different collections uniformly in terms of loop
### Definition
Using an iterator to traverse a container and access the container's elements
### UML
![](https://raw.githubusercontent.com/dongyu-zhao/CS_Learning/main/Design_Pattern/Iterator%20Pattern.png)
### Example
Java List, Game weapon equipment

# State Pattern
### Key:
* Finite state machine, different state use different method to transform from each other.
* Each state is treated equally, share the same interface but different in the behavior.
### Definition
Allows an object to alter its behavior when its internal state changes.
### UML
![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/State_Design_Pattern_UML_Class_Diagram.svg/2880px-State_Design_Pattern_UML_Class_Diagram.svg.png)
### Example
Enter subway, Finite state machine
