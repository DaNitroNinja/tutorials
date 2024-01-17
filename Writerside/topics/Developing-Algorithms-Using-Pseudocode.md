# Developing Algorithms Using Pseudocode

## Introduction
* Pseudocode is used to write an algorithm as if it were an actual program as it uses similar rules.
* You don't need to be too worried about the syntax or be precise about how the code will do something.
* After all it is just a plan.

## Basic Programming Constructs

The 3 Constructs:
: Sequence
: Selection
: Iteration

### Sequence
Sequence is simply writing a program in the order they need to happen.

```Python
price ← USERINPUT
quantity ← USERINPUT
total ← quantity * price
OUTPUT "The total price is " + TO_STRING(total)
```
The program above would work as it is in the right order, while the program below simply couldn't work as it gets the `USERINPUT` after calculating with blank variables.
```Python
total ← quantity * price
OUTPUT "The total price is " + TO_STRING(total)
price ← USERINPUT
quantity ← USERINPUT
```

### Selection
This has already been covered in the python topic, so it will be brief.

```Python
IF x <= 10 THEN
    y ← y + 10
ELSE IF x <= 20 THEN
    y ← y + 20
ELSE
    OUTPUT "Not a valid number."
ENDIF 
```
* The syntax is slightly different to Python, but if you know one of them, you will understand the other.

### Iteration
This has already been covered in the python topic, so it will be brief.

```Python
# While loop
countdown ← 5
WHILE countdown != 1
    countdown ← countdown - 1
    OUTPUT TO_STRING(countdown)
OUTPUT "Take off!"

#For loop
countdown ← 5
FOR i ← 0 TO countdown
    countdown ← countdown - 1
    OUTPUT TO_STRING(countdown)
OUTPUT "Take off!"

# Repeat until loop
countdown ← 5
REPEAT
    countdown ← countdown - 1
    OUTPUT TO_STRING(countdown)
UNTIL countdown = 1
OUTPUT "Take off!
```

They would all output:
```Python
5
4
3
2
1
Take off!
```
* The only new loop is the `REPEAT UNTIL` loop, which the main difference is that it checks the condition after the code has run.

