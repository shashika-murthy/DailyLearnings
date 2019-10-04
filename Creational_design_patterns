# Creational design patterns:

## 1. Prototype:

 This pattern lets you copy existing objects without making your code dependent on their classes.
 The pattern declares a common interface for all objects that support cloning. This interface lets youclone an object without coupling your code to the class of that object. Usually, such an interface contains just a single clone method.

 In simple terms, you can say a prototype is an object that supports cloning. This can be an alternative to subclassing.

 ### Example:
 In real life, like how a mitotic cell divides itself into two identical cells. Here, the original cell acts as a prototype to create a clone of it.

 ### How to identify it?

 The prototype can be easily recognized by a clone or copy methods, etc.

 ### When to use it?

 When you need an object like the one you’ve configured, you just clone a prototype instead of constructing a new object from scratch.
 When your code shouldn’t depend on the concrete classes of objects that you need to copy.

 ### Pros:

 you can clone objects without coupling to their concrete classes.
 you can get rid of repeated initialization code in favor of cloning pre-built prototypes.
 you can produce complex objects more conveniently.

 ### Cons:
 Cloning complex objects that have looping references might be very tricky.


## 2. Factory method

 This pattern provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

 ### Example:
 In real life, how a logistics class can have certain features common to all types of it and Truck/Van logistics can have customised features on top of it. Cargo logistics can have something different and so on.

 ### How to identify it?

 This pattern can be recognized by creation methods, which create objects from concrete classes, but return them as objects of abstract type or interface.

 ### When to use it?

 When you expect your product to grow into different areas or diversify.
 When you don't want to have the entire codebase running into a single class that takes the entire load. It would be a great deal, to add new objects having similar fundamental codebase for running the product.
 When you don't want to end up with pretty nasty code, riddled with conditionals that switch the app’s behavior depending on the class of different objects.
 when you don’t know beforehand the exact types and dependencies of the objects your code should work with.
 When you want to save system resources by reusing existing objects instead of rebuilding them each time

 ### Pros:

 you avoid tight coupling betyouen the creator and the concrete products.
 Single Responsibility Principle. you can move the product creation code into one place in the program, making the code easier to support.
 Open/Closed Principle. you can introduce new types of products into the program without breaking existing client code.

 ### Cons:
 The code may become more complicated since you need to introduce a lot of new subclasses to implement the pattern. 

 ## 3. Object Pool

 This pattern is like first you create a set of objects (a pool), then you acquire & release objects from the pool, instead of constantly creating and releasing them.

 In simple terms, once created object by the client, it is returned back to the pool, when the client will need it again, the object will be retrieved from the pool, but it will not be created again from the beginning because it has already been created, you can also set the number of objects that can be stored in the pool of objects.

 ### Example:
 In real life, how companies dedicate a team of employees for a project during the initial phase itself, instead of allocating resyources and releasing them on the go.

 ### When to use it?
 Not creating costly classes repeatedly, at once created expensive objects are returned back to the pool.
 The frequency of creating further objects is also high.
 The number of objects in use is small.

 ### Pros:
 Overall perfomance efficiency is improved.

 ### Cons:
 In a multi-threaded environment, you have to make your pool thread-safe.
 The object pool which doesn’t reset the states of returned objects is an anti-pattern. The object reset mechanism must be implemented in the Object pool without fail.
