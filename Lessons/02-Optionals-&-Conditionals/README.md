<!-- Run this slideshow via the following command: -->
<!-- reveal-md README.md -w -->


<!-- .slide: class="header" -->
# Optionals and Conditionals

<!-- > -->

## Agenda

- Learning Objectives
- Conditionals
- Activity on Conditionals
- Break
- Optionals
- Activity on Optionals
- Wrap Up

<!-- > -->

## Learning Objectives

By the end of this lesson, students should be able to:

1. Use conditional statements in Swift
1. Identify and use optionals in Swift code
1. Understand the importance of optional binding
1. List & apply ways for unwrapping an optional value

<!-- > -->

## Initial Exercise

Questions from the Repl.its?

Progress on challenges from last class?

<!-- > -->

## Conditionals

Swift has several constructs to handle control flow in a program. Using comparison operators and the type Boolean we can manipulate the flow of our apps.

<!-- v -->

### Comparison operators


|          |                           |
|:--------:|:-------------------------:|
|   >=     | greater than or equal to  |
|   >      | greater than              |
|   <=     | less than or equal to     |
|   <      | less than                 |
|   !=     | not equal to              |
|   ==     | equal to                  |
|   &&     | and                       |
|   ||     | or                        |

<aside class="notes">
*and* and *or* will let us combine operators

*and* used to check if both conditions are true

*or* used to check if at least one condition is true
</aside>

<!-- v -->

(4 < 8 && 6 > 8) || 1 < 2

<aside class="notes">
quick check: is this true or false?
</aside>

<!-- > -->

## if Statement

The most common way to control the flow of a program.

Allows the program to execute the block **only** if the condition is true.

```swift
if "some" != "sum" {
  print("These are not the same word.")
}
```

<aside class="notes">
If the condition is true, then the statement will execute the code between the braces. If the condition is false, it will skip the block of code.
</aside>

<!-- v -->

### else Clause

Extending the if statement

```swift
let color = "purple"

if color == "red" || color == "green" || color == "blue" {
  print("This is a primary color")
} else {
  print("This is not a primary color")
}
```

<aside class="notes">
We can extend an if statement to have code run in case the condition is false.
</aside>

<!-- v -->

### else if Clause

```swift
let studentCount = 35
var message = ""

if studentCount < 5 {
  message = "Class won't run"
} else if studentCount < 25{
  message = "Class will run"
} else if studentCount < 30 {
  message = "Class is packed"
} else {
  message = "We need another section"
}
print(message)
```

Nested if statements test multiple conditions one by one until a condition is true. Only the code associated with that first true condition is executed, regardless of whether subsequent else-if conditions are true. Order matters!

<aside class="notes">
Sometimes we want to check one condition after another. We use the else-if clause to nest an if statement in the else clause of a previous if statement.
</aside>


<!-- v -->

Note: the last else clause is optional. We might not always need it.

<!-- v -->

### Small prompt

Having:

```swift
let a = 5
let b = 10

let min: Int
let max: Int
```

Write code that will save the smaller number in *min* and the greater number in *max*.

<!-- v -->

### Ternary operator

```swift
(<CONDITION>) ? <TRUE VALUE> : <FALSE VALUE>
```

```swift
a < b ? a : b
a > b ? a : b
```
<aside class="notes">
The ternary operator takes a condition and returns one of two values, depending on whether the condition was true or false.
</aside>

<!-- > -->

## In Class Activity
[Conditionals - Repl.it](https://repl.it/classroom/invite/YcGNSq7)

<!-- > -->

## Optionals

<!-- > -->

Slides:

[Optionals & conditionals](https://docs.google.com/presentation/d/1mGFfmfmUR36PVpOQDSGlCvTjjpBmR6MMiWG8SmKZkAE/edit?usp=sharing)

## In Class Activities

1. [Conditionals - Swift Playgrounds](assets/conditionals.zip)
1. [Optionals - Swift Playgrounds - Chapter 4 on Optionals](https://github.com/MakeSchool-Tutorials/Swift-Language-Playgrounds/archive/swift4.zip)
1. [Another playground on optionals](https://github.com/MakeSchool-Tutorials/Intro-Optionals-Dictionaries-Playground)

## After Class

- Check out the toggle function that you can apply to booleans directly.

## Additional Resources

- [Article on Optionals](https://hackernoon.com/swift-optionals-explained-simply-e109a4297298)
- [Explaining the guard statement](https://thatthinginswift.com/guard-statement-swift/)
