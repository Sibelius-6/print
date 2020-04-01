title: SYDE 522 - Machine Intelligence
---

Taught by [Hamid R. Tizhoosh](https://uwaterloo.ca/systems-design-engineering/profile/tizhoosh).

# Lec 2
*What is intelligence?*

Dictionary => "the act or state of knowing" -> intelligence = knowledge.

*Is that so?*

"the excercise of understanding" -> intelligence = understanding

*Understanding what? How does understanding happen? Where does understanding happen?*

-> intelligence = learning &ne; knowledge acquisition

Knowledge is stored in "memory". [Static]

Learning is happen<b>ing</b> in the brain. [dynamic]

* intelligence is permanent adjustment of knowledge?
* Brain has different functionalities
    * -> memory
    * -> learning

```
             Humans  <--|--> Machines
          __________________________________
Thoughts  | reason     | rational decisions |--> AGI
--------  | --------------------------------|
Actions   | act        | rational actions   |--> AI
          |____________|____________________|
```


## Turing Test

Two rooms A B. A judge can ask questions.

MIQ ~ t<sub>guess</sub>

where t<sub>guess</sub> = time that judge needs to find out which room is the computer.

*Can machines think?*

*Is this the question that the Turing Test tries to answer?*

-> His prediction: By 2000, a computer has 30% to fool a human for five minutes?

## "John Searle"

![Chinese Room Argument](https://miro.medium.com/max/348/0*zA6_zLOjyt0zDeQG)

*Does this person understand Chinese?*

***Does the room understand Chinese?***

## Tic-Tac-Toe
Version 1: Look-Up Table  [Answer for each situation is hard-coded]

Version 2:
- A: Attempt to place two marks in row
- B: If opponent has two marks in a row, then place a mark in the third position.

Version 3: Represent the **state**(understanding) of the game
- Current board position?
- next legal moves?

Use an evaluation funciton.
- Rate the next move! (how likely to win?)
- Look-ahead of possible opponent's move!


```
<-----Stupid ----------------------- intelligence----->
Version 1                   2                         3
```

AI = Function Approximation

We need "data" for any approximation

Linear Regression.

AI = Operation ingelligently on data to extract the relationship between in- and outputs.
* -> Training data for learning.
* -> testing data for validation.

## Problems
1. Not enough data -> Augmentation
2. Too much data -> Dimensionality reduction
