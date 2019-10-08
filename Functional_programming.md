# Functional Programming
It is a programming paradigm in which we try to bind everything in pure mathematical functions style - a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

In terms of Swift, functional programming means using lets instead of vars when dealing with data.

## How to do this?
A key practice in functional programming is breaking code down into smaller, **pure functions**, which can be used several times throughout the project. Pure functions are functions that have **no side effects** on the program as a whole, meaning they exist solely to help other functions which do participate in the program.

Lets compare this with the traditional imperative programming and understand how to accomplish this.

## Eg:
If I want just even numbers from an array of data

## Imperative approach:
let numbers = [1, 2, 3, 4, 5]
var evenNumbers = [Int]()

for i in 0..<numbers.count {
    let number = numbers[i]
    if number % 2 == 0 {
        evenNumbers.append(number)
    }
}

## Functional Approach
let evenNumbers = [1, 2, 3, 4, 5].filter { $0 % 2 == 0 }

Similarly, **higher-order functions** like map(), flatmap(), sorted(), forEach() etc methods work. By higher-order, I mean functions that use a closure as a parameter.

## Brief on First-class functions:
First-class functions are treated as first-class variable. The first class variables can be passed to functions as parameter, can be returned from functions or stored in data structures. Higher order functions are the functions that take other functions as arguments and they can also return functions.

## Few terms:
Functors -> something that can implement .map()
Monads -> something that can implement .flatMap()

## Pros:
less prone to bugs and easier to understand than imperative code. Imperative programming is the opposite of functional programming — it’s a paradigm that uses statements that change a program’s state.
