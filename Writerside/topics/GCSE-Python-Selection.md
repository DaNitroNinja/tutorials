# GCSE Python - Selection

## Introduction - Making Decisions in Code

* Selection, or conditional statements, allow your Python programs to make decisions and execute different code blocks based on specific conditions.

Key Concepts:
: `Boolean Expressions`: Expressions that evaluate to either True or False.
: `Comparison Operators`: Used to compare values (e.g., ==, !=, <, >, <=, >=).
: `Logical Operators`: Combine Boolean expressions (e.g., and, or, not).
: `Indentation`: Crucial in Python to define code blocks within conditional statements.

## The if statement
* In python you use the if statement to make decisions based off of variables.
* Here is the syntax for it:
```Python
temperature = int(input("Enter the temperature: "))
if temperature >= 30:
    print("It's a hot day!")
else:
    print("It's not a hot day.")
```
* As you can see, if the temperature meets the criteria, the code flows through the `It's a hot day!` branch
whereas if not then it runs through the `It's not a hot day.` branch.

* This better explains how an if statement works:
```Python
if condition:
    # Code to be executed if condition is True
else:
    # Code to be executed if condition is False
 
```