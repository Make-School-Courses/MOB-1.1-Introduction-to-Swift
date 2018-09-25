# Introduction to OOP

## Lesson Overview

| **Time(min)** | **Activity**                  |
| ------------- | ---------------------------   |
| 5             | Intro & Objectives            |
| 15            | TT on OOP (What, why, how)    |
| 30            | Playground OOP (Chapters 1-4) |
| 10            | Break                         |
| 10            | TT Subclassing & Inheritance  |
| 35            | Playground OOP (Chapters 5-8) |
| 5             | Wrap up & Q&A                 |

## Objectives & Competencies
By the end of this lesson, students should be able to:

- Define a class
- Create an instance of a class
- Define properties and type on a class
- Define methods on a class
- Distinguish between a function and a method
- Distinguish between a variable and a property
- Distinguish between Static vs Class methods
- Define and create a subclass of an existing class
- Identify and define `self` in a class

## Class Materials
Slides: [OOP in Games](https://docs.google.com/presentation/d/1RKt5hiE30_opdI9euTtXJJ3oeFtIb4dTJ-a6ETlw0Z8/edit?usp=sharing)

[OOP Playgrounds](https://github.com/Product-College-Labs/object-oriented-programming-in-swift/archive/master.zip)
<!-- https://github.com/Product-College-Labs/object-oriented-programming-in-swift.git -->

## Baseline Challenges

[OOP Challenges](https://github.com/MakeSchool-Tutorials/Intro-Object-Oriented-Programming-Playground/archive/master.zip)
<!-- https://github.com/MakeSchool-Tutorials/Intro-Object-Oriented-Programming-Playground.git -->

- Bubble Pop Game Challenges. Use OOP to improve your game. 
  - Your doing a lot of work in the GameScene it would be good to move some of this into another file.
    - Make a class Box. It should handle the following
      - Set the size of the box
      - set the color of the box
      - set the name of the box
      - Stretch goals 
        - Position the box 
        - Animate and remove box
  - Stretch goals 
    - Make a class for score label
      - It should set all the default properties of the label 
      - It should have a method that updates the score it displays
      - When the score changes the label counts up to the new value
    - It would be cool if some points appeared at the location of a box that was tapped. This should show the points scored and animate up the screen, fade out, and remove itself. **Make this a class!**
    - Make a particle system that appears at the location of a bubble when it has been tapped. This particle 
    should remove itself after a short animation. 
      - Make a sub class SKEmitterNode

**Note**

The Playgrounds contains a link to the material for the Walkthrough on OOP and the challenges for students in the same git repository. When downloaded/cloned you get access to both Playgrounds.
