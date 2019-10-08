# Dependency Injection

## Objective:

To introduce loosely coupled code making it easier to test the code. Basuc idea is instead of creating the dependency internally, an object can receive it from the outside.

Basically there are 3 types in this.
1. Property injection
2. Constructor injection
3. Method injection.

Consider this example where a view model has created its own dependency on the object.

// screenshot or code block

Let's see how we can inject the depencies in ways that can be explained in just a line.

## 1. Property injection

How to do -> Don't initialize the property, make it an optional and initialize it from outside the object and you are good to go.

## 2. Constructor injection

How to do -> Don't initialize the property, add a designated constructor for the property of the class and you are good to go.

## 3. Method injection

How to do -> As the name suggests, inject the dependency into whichever method you want to and you are good to go.


# Closures

Typically, closures are self-contained blocks of functionality that can be passed around and used in your code

Closures(Swift) == Blocks(C) == Lambdas(Others)

It can capture and store references to any constants and variables from the context in which it is defined. This is known as closing over those constants and variables. Hence, the name "CLOSURE".

Closures take one of three forms:

Global functions are closures that have a name and do not capture any values.
Nested functions are closures that have a name and can capture values from their enclosing function.
Closure expressions are unnamed closures written in a lightweight syntax that can capture values from their surrounding context.

### Syntax 

Closure expression syntax has the following general form:

{ (parameters) -> return type in
    statements
}

The parameters in closure expression syntax can be in-out parameters, but they can’t have a default value. Variadic parameters can be used if you name the variadic parameter. Tuples can also be used as parameter types and return types.
Eg:
reversedNames = names.sorted(by: { (s1: String, s2: String) -> Bool in
    return s1 > s2
})

### Type inference

Swift can infer the types of the closure's parameters and the type of the value it returns if the closure is passed as an argument to a method.

Simplified Eg:
reversedNames = names.sorted(by: { s1, s2 in return s1 > s2 } )

Single-expression closures can implicitly return the result of their single expression by omitting the return keyword from their declaration

More Simplified Eg:
reversedNames = names.sorted(by: { s1, s2 in s1 > s2 } )

Swift automatically provides shorthand argument names to inline closures, which can be used to refer to the values of the closure’s arguments by the names $0, $1, $2, and so on.

Shortened Eg:
reversedNames = names.sorted(by: { $0 > $1 } )
Here, $0 and $1 refer to the closure’s first and second String arguments.

There is even shorter way to write the closure expression above by using operators.

More Shortened Eg:
reversedNames = names.sorted(by: >)

### Trailing Closure

A trailing closure is written after the function call’s parentheses, even though it is still an argument to the function. When you use the trailing closure syntax, you don’t write the argument label for the closure as part of the function call.

func someFunctionThatTakesAClosure(closure: () -> Void) {
    // function body goes here
}

// Here's how you call this function without using a trailing closure:

someFunctionThatTakesAClosure(closure: {
    // closure's body goes here
})

// Here's how you call this function with a trailing closure instead:

someFunctionThatTakesAClosure() {
    // trailing closure's body goes here
}

### Reference types

After all this, One important thing is that closures are reference types.
Whenever you assign a function or a closure to a constant or a variable, you are actually setting that constant or variable to be a reference to the function or closure. If you assign a closure to two different constants or variables, both of those constants or variables refer to the same closure.

### Escaping closures

A closure is said to escape a function when the closure is passed as an argument to the function, but is called after the function returns. When you declare a function that takes a closure as one of its parameters, you can write @escaping before the parameter’s type to indicate that the closure is allowed to escape.
Common use case for this is completion handlers in functions that start an asynchronous operation.

### Autoclosures

An autoclosure is a closure that is automatically created to wrap an expression that’s being passed as an argument to a function. It doesn’t take any arguments, and when it’s called, it returns the value of the expression that’s wrapped inside of it.

Eg:
var customersInLine = ["Chris", "Alex", "Ewa", "Barry", "Daniella"]
print(customersInLine.count)
// Prints "5"

let customerProvider = { customersInLine.remove(at: 0) }
print(customersInLine.count)
// Prints "5"

print("Now serving \(customerProvider())!")
// Prints "Now serving Chris!"
print(customersInLine.count)
// Prints "4"
