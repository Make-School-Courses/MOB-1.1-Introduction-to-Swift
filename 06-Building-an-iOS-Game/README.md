# Building an iOS Game

## Lesson Overview

| **Time(min)** | **Activity**                     |
| ------------- | ---------------------------      |
| 5             | Review & Solution of The Grid    |
| 5             | Objectives                       |
| 10            | TT on Actions for the challenge  |
| 30            | Challenge                        |
| 10            | Break                            |
| 5             | TT Finding & Removing Nodes      |
| 15            | Activity on Random Numbers       |
| 25            | Challenge on Moving boxes        |

## Objectives & Competencies
By the end of this lesson, students should be able to:

- Use SKActions to move sprites
- Delete sprites from scenes using `RemoveFromParent`
- Find sprites by their name property
- Work with random numbers in Swift
- Identify & apply the different ways to run actions (block, sequence, repeat)

## Class Materials

Solution to The Grid

```
for col in -1 ... 1 {
  for row in -1 ... 1 {
    // make a box
    // center x + space * col
    // center y + space * row
  }
}
```

Slides: [Building an iOS Game](https://docs.google.com/presentation/d/17AR52Hkqp1Lid4BohnvcHnZJ5cK3w1j7yusMJQkaRKI/edit?usp=sharing)

## Baseline Challenges

[Empty Starter project](https://github.com/Product-College-Labs/Game-Starter-Empty/tree/master)

Using what you already know, complete each step in the image.

![Moving Boxes](assets/movingBoxes.png)

<!--- https://github.com/Product-College-Labs/pop-the-bubble --->

## After Class
- Continue working on Orange Tree

## Resources

- [Apple's documentation on SKActions](https://developer.apple.com/documentation/spritekit/skaction)
- [Article on random numbers](https://learnappmaking.com/random-numbers-swift/)
