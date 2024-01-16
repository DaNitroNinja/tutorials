# GCSE Python - Iteration

## Introduction - Repeating Actions In Code
* Iteration, or looping, enables you to execute a code block repeatedly, streamlining tasks that involve repetition and creating more efficient programs. 
* There are 2 types of loops: the `for` loop and the `while` loop.

Key Concepts
: `for` loop: Used when you know the number of iterations in advance.
: `while` loop: Used when the number of iterations depends on a condition.
: `Indentation`: Vital for defining the code block to be repeated within loops.
: `Loop` control statements: `break` and `continue` allow you to control the loop's flow.

## For Loops
* You can loop through the characters in a string:

```Python
for letter in "hello":
print(letter)  
```
```Python
OUTPUT:
h
e
l
l
o
```

* You can loop through a range of numbers:

```Python
for i in range(5):
print(i)
```
```Python
OUTPUT:
0
1
2
3
4 # Remember that the index of a list begins at 0.
```
* Nested loops: You can even nest loops inside each other for more complex tasks.

## While Loops

Condition: This is the "engine" of the loop. It determines whether the loop continues or stops. As long as the condition is True, the loop body keeps running.

##### Examples of conditions:

* Loop until user enters a specific word:

```Python
word = ""
while word != "exit":
word = input("Enter a word: ")
```

* Loop a certain number of times based on a variable:
```Python
times = 10
while times > 0:
print("Looping: ", times)
times -= 1
```

* `Infinite loops`: Be careful! If the condition never becomes False, your loop might run forever (an infinite loop), causing errors. Always have a way for the condition to eventually become False and stop the loop.
Loop Control Statements:

* `break`: Imagine this as an emergency exit. It breaks out of the loop immediately, regardless of the condition. Use it carefully, as it can skip important iterations.
* `continue`: Think of this as a "next button." It skips the remaining code in the current iteration and moves on to the next one. This can be useful when you want to avoid processing certain elements in the sequence.