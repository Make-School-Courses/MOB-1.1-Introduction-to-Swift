<!-- Run this slideshow via the following command: -->
<!-- reveal-md README.md -w -->

<!-- .slide: class="header" -->

# Protocols

## [Slides](https://make-school-courses.github.io/MOB-1.1-Introduction-to-Swift/Slides/09-POP/README.html ':ignore')

<!-- > -->

## Agenda

- Intro to Protocols
- Protocols vs Inheritance
- Protocols in the Swift Standard Library
- Break
- Extensions
- Final project specifications

<!-- > -->

## Learning Objectives

- Create and use Protocols
- Distinguish between Protocol Conformance and Inheritance
- Use protocols to describe properties and behaviors of a conforming type
- Identify common protocols in the Swift Standard Library
- Work with extensions

<!-- > -->

## What are we trying to solve?

<p class="fragment fade-in">We start with class inheritance.</p>
<p class="fragment fade-in">We realize we need more functionality in one class from two other classes.</p>
<p class="fragment fade-in">We need multiple inheritance. Not supported 😟</p>
<p class="fragment fade-in">Passing around classes can cause unexpected behavior. We want to avoid this as much.</p>
<p class="fragment fade-in">Tight coupling.</p>

<!-- > -->

## Protocol

Protocols are another type in Swift. 🙃

But **they don't create any instances**. Instead, they **define a blueprint** of methods, properties, and other requirements that other types need to implement.

A protocol can be adopted by a class, structure, or enumeration.

Any type that satisfies the requirements of a protocol is said to **conform** to that protocol.

<!-- v -->

**Protocols are similar to contracts.**

A contract is a guarantee that some terms will be satisfied. ✍🏼

Anything on the contract becomes a set of obligations to whoever gets it.

<!-- whiteboard mini diagram -->

<!-- v -->

```swift
protocol FullName {
  var fullName: String {get}
  func printToConsole()
}
```

<aside class="notes">
This protocol indicates that any class, struct or enum that conforms to it, needs a property called fullName. And it is get only. This means we can only read it after we give an initial value.

We can declare methods in a protocol but notice we don't define any implementation for them. A protocol makes no assumption about the implementation details of any type that conforms to it.
</aside>

<!-- v -->

```swift
struct Person: FullName{
    var fullName: String
    func printToConsole() {
        print(fullName)
    }
}

var author = Person(fullName: "Haruki Murakami")

struct Person: FullName{
    var firstName: String
    var lastName: String
    var fullName: String {
      return "\(firstName) \(lastName)"
    }
    func printToConsole() {
        print(fullName)
    }
}

var author = Person(firstName: "Haruki", lastName: "Murakami")
```

<aside class="notes">
Conforming to a protocol looks like class inheritance but it isn’t. Structs and enumerations can also conform to protocols with this syntax.

If a class inherits from another and also conforms to a protocol, all can be separated by commas and the inheritance comes first.
</aside>

<!-- > -->

## Mini challenge

Create a protocol `Perimeter` that defines a read-only property `perimeter` of type `Double`.

<!-- > -->

## Mini challenge

Implement `Perimeter` with structs representing `Square`, and `Circle`.

<!-- > -->

## Mini challenge

Add a circle and a square to an array, print their perimeters.

<!-- > -->

## Walkthrough

[Walkthrough](https://github.com/Product-College-Labs/protocols-introduction-ios/archive/master.zip)

<!-- > -->

## Mini challenge

1. Create a model of a car, it should have:
  - max speed
  - number of wheels
  - doors
  - model  

<!-- v -->

2. Generalize the car, create a model for a vehicle which will represent all vehicles, a truck, motorcycle & bus are vehicles

3. Create a model(struct or class or enum) an instances of each a truck, motorcycle and bus.

<!-- > -->

## Jigsaw activity 🧩

Swift uses protocols extensively. We won't learn every single aspect of the Swift standard library, it makes no difference in our code's performance. But we can benefit from being familiar with several commonly used protocols.

In groups of X, get together to research about one of the following protocols. **One per group.**

- Sequence Protocol
- Collection Protocol
- Equatable Protocol
- Hashable Protocol
- CaseIterable Protocol

<!-- v -->

Make sure everyone understands how they work and **individually prepare an example in a playground**. (it can be the same for everyone in the group).

Also **make sure you can explain in words what it does, it might be helpful to have notes.**

It will be thanks to your contribution that others can learn about what you researched.

<!-- v -->

- Now split the group. Go and find people who did the other protocols.

- We should have groups with people who know about all of them combined.

- Take turns to have each person explain their protocol and show the example.

- By the end of the activity you should be familiarized with all 4 protocols thanks to your peers. 😀

<!-- > -->

Any questions?

<!-- > -->

## Mini challenge

Given the Artist struct below, implement the Equatable protocol. You'll define what makes two instances equal.

```swift
// Used by Artist to determine style of Artist
enum Style: String {
    case impressionism
    case surrealism
    case cubism
    case popArt
}

struct Artist {
    let name: String
    let style: Style
    let yearBorn: Int
}

// Example instances of Artists, use for testing your equatable
let monet = Artist(name: "Monet", style: .impressionism, yearBorn: 1840)
let dali = Artist(name: "Salvador Dali", style: .surrealism, yearBorn: 1904)
let andy = Artist(name: "Andy Warhol", style: .popArt, yearBorn: 1928)

```

<!-- > -->

## Benefits observed

What are some benefits you've seen so far about using protocols?

<section>
  <p class="fragment fade-in">Behavior similar to multiple-inheritance</p>
	<p class="fragment fade-in">Adopted by classes, structs & enums</p>
	<p class="fragment fade-up">Value types = less risk</p>
</section>

<!-- > -->

## Extensions

Extensions add new functionality to an existing class, structure, enumeration, or protocol type.

- Add computed instance properties and computed type properties
- Define methods
- Provide new initializers
- Make an existing type conform to a protocol

<!-- v -->

Protocols can be extended to provide methods, initializers, and computed property implementations to conforming types.

This allows us to define behavior on protocols themselves, rather than in each type’s individual conformance.

<!-- v -->

```swift
extension FullName {
    func printUppercase(){
        print(fullName.uppercased())
    }
}

var me = Person(fullName: "Adriana Gonzalez")
me.printUppercase()
```

<!-- v -->

### Providing default functionality

extension FullName {
    func printToConsole(){
        print(fullName)
    }
}

var me = Person(fullName: "Adriana Gonzalez")
me.printToConsole()

<!-- Demo what happens if we delete the implementation of the method in the struct. And also if the extensions prints something different. When it overrides? -->

<!-- > -->

### Food for thought

How to know when to use a subclass and an extension?

<!-- > -->

## After class

Begin your final project. Follow the instructions [here](https://github.com/Make-School-Courses/MOB-1.1-Introduction-to-Swift/blob/master/Assignments/FinalProject.md).

<!-- > -->

## External resources

[CaseIterable](https://developer.apple.com/documentation/swift/caseiterable)
[Iterator](https://developer.apple.com/documentation/swift/iteratorprotocol)
[Protocols](https://docs.swift.org/swift-book/LanguageGuide/Protocols.html)
[Protocols - article](https://medium.com/ios-os-x-development/how-protocol-oriented-programming-in-swift-saved-my-day-75737a6af022)
[Extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html)
[Protocols](https://docs.swift.org/swift-book/LanguageGuide/Protocols.html#ID521)
[StackOverFlow answer](https://stackoverflow.com/questions/38827265/class-extension-vs-subclassing-in-swift)
