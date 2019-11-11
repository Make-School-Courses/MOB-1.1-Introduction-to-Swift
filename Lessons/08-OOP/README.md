<!-- Run this slideshow via the following command: -->
<!-- reveal-md README.md -w -->

<!-- .slide: class="header" -->
# Object Oriented Programming with Swift

## [Slides](https://make-school-courses.github.io/MOB-1.1-Introduction-to-Swift/Slides/08-OOP/README.html ':ignore')

<!-- > -->

## Agenda

- OOP
- Classes
- Inheritance
- Initializers
- Activity

<!-- > -->

## OOP

OOP is a programming paradigm that represents the concept of objects that have attributes to describe them and can perform certain procedures known as methods.

When you learn about it you can read and write code easier and you will have a better understanding on how Swift works.

<!-- > -->

## Classes

Classes are reference types and can be used to support traditional OOP.

They introduce inheritance, overriding and polymorphism. These features require we know about initialization, class hierarchies, and other aspects.

<!-- v -->

- Using classes we can model data.
- Initializers allow us to set the initial state of a class.
- Variables and Constants that live in the scope of the class are referred to as *instance variables*
- The *self* keyword used in class is used to refer to the current instance.

<!-- v -->

```swift
class Person {
    // Instance variable
    let name: String

    // Initializer, setting instance variables of Person
    init(name: String) {
        self.name = name
    }
}
```

<!-- v -->

### Creating an instance

Creating a person is called creating and instance of the class `Person`

```swift
let eddy = Person(name: "Eduardo")
```

<!-- v -->

### Scope

Classes encapsulate variables and functions.

Variables that live at the top level of the class are **global** to the class. That means they can be accessed by functions in the class.

```swift
class Person {
  var firstName: String

  init(firstName: String) {
    self.firstName = firstName
    let favColor = "Purple"
  }

  func sayHello() {
      // Cant access favColor because its in a different function and not global
      print("Hi, I'm \(self.firstName)")
      // Can access firstName because its an instance variable and scoped to the class
  }
}
```

<!-- > -->

### Inheritance

```swift
class BandMember: Person {
  var songs: [String] = []

  func performedSong(_ song: String) {
    songs.append(song)
  }
}
```

We indicate inheritance by writing the name of the class, colon, and the name of the class being inherited.

A Singer is a subclass of Person and automatically gets the properties and methods in the Person class.

<!-- v -->

```swift
let adriana = Person(firstName: "Adriana")
let elton = BandMember(firstName: "Elton")

adriana.firstName
elton.firstName  
elton.performedSong("I'm still standing")
```

A class that inherits from another class is known as a **subclass** or **derived class**, and the class from which it inherits is known as a **superclass** or **base class**.

<!-- v -->

### Rules for inheritance

- A Swift class can inherit from *only one other class*
- No limit to the depth of subclassing, we can subclass from a class that is also a subclass.

```swift
class Person {
...
}

class BandMember: Person {
...
}

class Singer: BandMember {
...
}
```

<aside class="notes">
A chain of subclasses is called a class hierarchy. Here the hierarchy would be BandMember -> Singer -> Person.
</aside>

<!-- > -->

## Override

```swift
class BandMember: Person {
  var songs: [String] = []
  var instrument: String!

  func performedSong(_ song: String) {
    songs.append(song)
  }

  override func sayHello(){
    print("Hi, I'm \(firstName), I'm in a band.")
  }
}
```

Subclasses can override methods defined in their superclass.

<!-- > -->

## Super

```swift
class Singer: BandMember {
    override func performedSong(_ song: String) {
      super.performedSong(song)
        if shouldRest {
            print("Sang \(song)")
            print("Ask the band for a break.")

        }else{
            print("Sang \(song)")

        }
    }

    override func sayHello(){
      print("Hi, I'm \(firstName), I also sing.")
    }

    var shouldRest: Bool { // read-only computed property
        return self.songs.count >= 3
    }
}
```
The super keyword is similar to self, but it will invoke the method in the nearest implementing superclass. Here it will execute the method as defined in the BandMember class.

Also, here we are using a computed property. It calculates a value rather than storing one.

<!-- > -->

## Initializers

Initializers are special methods we call to create a new instance. They omit the func keyword and even a name. Instead, they use init.

<!-- v -->

### Default/Designated initializer

Designated initializers are the primary initializers for a class. A designated initializer fully initializes all properties introduced by that class and calls an appropriate superclass initializer to continue the initialization process up the superclass chain.

```swift
class Person {
  var firstName: String

  init(firstName: String) {
    self.firstName = firstName
  }
}
```

<!-- v -->

A designated initializer must call the initializers from its immediate superclass.

```swift
class BandMember: Person {
  var songs: [String] = []
  var instrument: String!

  init(firstName: String, instrument: String) {
    super.init(firstName: firstName)
    self.instrument = instrument
  }
  ...
}
```

<!-- v -->

### Convenience initializer

Convenience initializers must call the designated initializer for its class.

```swift
class BandMember: Person {
  var songs: [String] = []
  var instrument: String?

  convenience init( firstName: String, instrument: String) {
    self.init(firstName: firstName)
    self.instrument = instrument
  }

  ...
}
```

<!-- v -->

### Required initializer

```swift
class Person {
  var firstName: String

  required init(firstName: String) {
    self.firstName = firstName
  }
}
```

<!-- > -->

## Hotel activity

[Instructions](/hotel.md)

<!-- > -->

## Final classes

If we have a class that we don't want to subclass ever, we use the `final` keyword.

When we declare a class as being final, no other class can inherit from it. This means they can’t override your methods in order to change your behavior.

```swift
final class Person {
  ...
}
```

<!--
[OOP Playgrounds](https://github.com/Product-College-Labs/object-oriented-programming-in-swift/archive/master.zip)
-->

<!-- > -->

## Challenge

<!--
[OOP Challenges](https://github.com/MakeSchool-Tutorials/Intro-Object-Oriented-Programming-Playground/archive/master.zip)
-->

- Bubble Pop Game Challenges. Use OOP to improve your game.

[Instructions](/challenge.md)

<!-- > -->

## After Class
1. POP Repl.it
1. Research about Instance vs Type methods
1. Look up what static properties are

<!-- > -->

## Additional Resources
1. [Documentation for Properties](https://docs.swift.org/swift-book/LanguageGuide/Properties.html)
