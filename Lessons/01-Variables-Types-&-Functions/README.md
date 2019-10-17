# Variables, Types & Functions

## Minute-by-Minute

| **Time(min)** | **Activity**               |
| ------------- | ---------------------------|
| 10            | Intro to course            |
| 5             | Learning Objectives        |
| 15            | Variables, Constants, Types|
| 30            | Playground on Variables    |
| 10            | Break                      |
| 10            | TT on Functions            |
| 30            | Playground on Functions    |
| 5             | Wrap up                    |

## Learning Objectives

By the end of this lesson, students should be able to:

1. Identify and create variables & constants
1. Identify and define types in Swift
1. Formulate and use functions to encapsulate code with parameters and return values
1. Identify and write comments in code

## Swift Intro

Swift is a programming language to write software for phones, wearables, desktops, servers, and much more. It was released in June 2014 by Apple. The language is a combination of years of Apple engineering development and the contribution of an open-source community.

Swift is beginner friendly, safe, fast, interactive and optimized for performance and development.

## Playgrounds

To learn a lot of the course content we will be using Playgrounds. It will be easy and fast to experiment without having to set up an app in Xcode. Xcode is the environment where we build apps.

### Playground sections

- Source editor: where we write code
- Results sidebar: shows results of code
- Execution control: manual or automatic
- Activity viewer: shows status of the playground
- Panel controls: toggle them on or off from the screen

## Comments

Before we start writing code, it's important to know how you can document what you do. This is helpful for people who will later work with your code, or just you in the future. We can write comments to help us know *why* we wrote some code and this will be ignored by the compiler.

```swift
// This is a single line comment
```

```swift
/* This is a comment that can
   span over many lines.
   Like this.
 */
 ```

## Print to console

It's also useful to see what our code is doing. For this we use print statements. The results will print in the debug area or console.

```swift
print("Hello, you are ready to write some Swift")
```

## Constants

When we handle data in our code, we can give it a name and a type. This makes it easier to reference it later and manipulate it.

```swift
let months: Int = 12
```

This is a constant. We declare a constant using `let` followed by the name we want to give that data, here it's `months`. We also set it's type to `Int` and assigned a value of 12. What comes after the colon is called a *type annotation*, you use this to be clear about the kind of values the constant can store.

The type **Int** can store integers.

```swift
let average: Double = 8.88
```

The type **Double** can store decimals with high precision.
The type **Float** can store decimals with less precision but takes up less memory.

Once we've declared a constant we can't change it's data. So this makes them useful for values that we know they won't change. If by mistake you try to change the value of a constant, Xcode will throw an error message to let you know.

```swift
Cannot assign to value: 'number' is a 'let' constant
```

## Variables

What if we need to change the value? For example if we are tracking our bank account balance. Then we use Variables.

```swift
var accountBalance: Double = 8000.80
```

It's very similar as a constant, but we declare it with the keyword `var`.

Constants are useful in cases when we know our data can change.

### Naming

Choose names for your variables and constants that reflect what they are. This will help as documentation and to make your code readable.

|     Good     |      Bad      |
|:------------:|:-------------:|
| numberOfPets |      np       |
| username     |     usrnm     |
| borderColor  |     temp      |

In Swift is common to use **camel case**.

- Start with lower case
- If the name has more than one word, start the next words with uppercase
- If there is an abbreviation, use the same case for it

## In Class Activity

In this playground we review the concepts learned so far, experiment using arithmetic operations and also learn about a new type: Strings.

[Variables - Swift Playgrounds](https://github.com/MakeSchool-Tutorials/Intro-Variables-Swift-Playground/archive/swift4.zip)

## Type casting

There can be times when we have data of a certain type but need to convert it to another.

```swift
var integer: Int = 20
var decimal: Double = 8.5

integer = Int(decimal)
```
With these we say we want to convert from the original type, Double, to the new type, Int.

## Type inference

Every time we declare a new variable or constant we add a type annotation. If we do not include it and still assign a value, the Swift compiler can deduce the type. This is called *type inference*

```swift
let inferredInt = 20
```

We can find something like this and assume that the compiler knows it's an Int. We can double check this by holding down the **Option key  ⌥** and clicking on the variable or constant name. Then we should see a popover telling us the inferred type.

Sometimes we need a variable to be a certain type even when assigning something different. Let's say we have this:

```swift
let needADouble = 8
```

This would be assigned as an Int by the compiler. Here are several ways to fix it:

```swift
let nowADouble = Double(8)
let nowADouble : Double = 8
let nowADouble = 8 as Double
```
## Other types

```swift
let char: Character = "a"
let string: String = "a string"
let cheesecakeLover: Bool = true
let coordinates: (Int, Int) = (1, 2)
```
This last example is a **tuple**. A tuple is a type that represents data made up  of more than one value of any type. Since a tuple has several values, there's a special way to accessing them:

```swift
let xCoordinate = coordinates.0  // 1
let yCoordinate = coordinates.1  // 2
```

Here's a variation that let's you add names to better reference the data.

```swift
let coordinates = (x: 1, y: 2)

let xCoordinate = coordinates.x  // 1
let yCoordinate = coordinates.y  // 2
```

## Functions

## In Class Activity

1. [Functions - Swift Playgrounds](https://github.com/soggybag/Draw-Mac)

## Wrap Up

- Complete the exercises on Repl.it for Variables, Types & Functions

## Additional Resources

- [About Swift](https://docs.swift.org/swift-book/index.html)
- [Apple's documentation on Variables & Constants](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)
- [Video on Types in Swift](https://www.youtube.com/watch?v=BlXrMgmvNBI)
- [Article explaining Functions](https://learnappmaking.com/swift-functions-how-to/)
