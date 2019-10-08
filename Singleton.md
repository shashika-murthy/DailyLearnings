# Singleton 

It is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.

## Why is it needed? 
to control access to some shared resource—for example, a database or a file.
Use the Singleton pattern when you need stricter control over global variables.

## Implementation:

1.Make the default constructor private, to prevent other objects from using the new operator with the Singleton class.

2. Create a static creation method that acts as a constructor. Under the hood, this method calls the private constructor to create an object and saves it in a static field. All following calls to this method return the cached object.

## Benefits:
1. The Singleton pattern lets you access some object from anywhere in the program. However, it also protects that instance from being overwritten by other code.
2. You can be sure that a class has only a single instance.
3. The singleton object is initialized only when it’s requested for the first time.

## Drawbacks:
1. The pattern requires special treatment in a multithreaded environment so that multiple threads won’t create a singleton object several times.
2. It may be difficult to unit test the client code of the Singleton because many test frameworks rely on inheritance when producing mock objects. Since the constructor of the singleton class is private and overriding static methods is impossible in most languages, you will need to think of a creative way to mock the singleton

## Real world analogy:
The government is an excellent example of the Singleton pattern. A country can have only one official government. Regardless of the personal identities of the individuals who form governments, the title, “The Government of X”, is a global point of access that identifies the group of people in charge.

## Relation with other patterns:
**Flyweight** would resemble Singleton if you somehow managed to reduce all shared states of the objects to just one flyweight object. But there are two fundamental differences between these patterns.

There should be only one Singleton instance, whereas a Flyweight class can have multiple instances with different intrinsic states.
The Singleton object can be mutable. Flyweight objects are immutable.

**Abstract Factories, Builders** and **Prototypes** can all be implemented as Singletons.
