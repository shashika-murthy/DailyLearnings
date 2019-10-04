# Structural design patterns:

## 1. Flyweight

As the name suggests, the design pattern is intended to minimize the memory intake for the objects involved in the project.

### How does it do?

Pattern achieves it by sharing parts of object state between multiple objects. In other words, the Flyweight saves RAM by caching the same data used by different objects.

The Flyweight stores a common portion of the state (also called intrinsic state) that belongs to multiple real business entities

### How to identify we have used one?

Flyweight can be recognized by a creation method that returns cached objects instead of creating new.

### Bit More Detail:

The Flyweight Factory creates and manages the Flyweight objects. It ensures that flyweights are shared correctly. When the client requests a flyweight, the factory either returns an existing instance or creates a new one, if it doesn't exist yet. 
Seems like a singleton right? But here's the difference.

1. Singleton is mutable whereas FlyWeight isn't
3. Flyweight is reusing (obviously immutable) instances of a class wherever possible, rather than creating new instances of a class with the same "value", which saves CPU and memory.

Singleton is when there is only ever one instance of a (usually mutable) class. It is often used in multi-threaded environments to facilitate all threads using a single instance and "seeing" the same state.

In simple terms, its like a tableview which reuses the existing cell while requesting new ones.


## 2. Proxy

As the name suggests, the design pattern is intended to provide a substitute or placeholder for another object.

### How does it do?

A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.

It can add additional responsibilities as well 

### Bit More Detail:

There are countless ways proxies can be used like: caching, logging, access control, delayed initialization, etc.

The Proxy pattern suggests that you create a new proxy class with the same interface as an original service object. Then you update your app so that it passes the proxy object to all of the original object’s clients. Upon receiving a request from a client, the proxy creates a real service object and delegates all the work to it.

### Example:
Credit cards used as a proxy for cash while doing payments.

### Pros:
You can control the service object without clients knowing about it.
You can manage the lifecycle of the service object when clients don’t care about it.
The proxy works even if the service object isn’t ready or is not available.
Open/Closed Principle. You can introduce new proxies without changing the service or clients.

### Cons:
The code may become more complicated since you need to introduce a lot of new classes.
The response from the service might get delayed.

### Differences with similar patterns:

**Adapter** provides a different interface to the wrapped object, Proxy provides it with the same interface, and Decorator provides it with an enhanced interface.

**Facade** is similar to Proxy in that both buffer a complex entity and initialize it on its own. Unlike Facade, Proxy has the same interface as its service object, which makes them interchangeable.

**Decorator** and Proxy have similar structures, but very different intents. Both patterns are built on the composition principle, where one object is supposed to delegate some of the work to another. The difference is that a Proxy usually manages the life cycle of its service object on its own, whereas the composition of Decorators is always controlled by the client.


## 3. Private class data


The Private Class Data Patterns approach is to remove exposure of data by securing it within a class maintaining the data’s state. In a nutshell, the Private Class Data Pattern encapsulates class data initialization.
This is basically used in Java, not in swift.
