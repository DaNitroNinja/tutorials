# GCSE Python - Operators

## Introduction

* Operators are symbols that perform operations on values.

Operators are classified into:
: Arithmetic operators
: Comparison operators
: Logical operators
: Assignment operators

## Arithmetic Operators

* Arithmetic operators `(+, -, *, /, //, %)` are used to add values together and combine variables.
```Python
total = 3 + 5
num_var = 3 * 5
print (total)
print(num_var)
print(10 % 2)
print(10 // 2)
```
would output
```Python
8 # addition
15 # multiplication
5 # integer division
0 # remainder
```

## Comparison Operators

* They compare two values and return a Boolean result (True or False) indicating their relationship.

Types
: `==` (Equal to)
: `!=` (Not equal to)
: `<` (Less than)
: `>` (Greater than)
: `<=` (Less than or equal to)
: `>=` (Greater than or equal to)

Use in python programs (Skip to Selection?[Yes!](GCSE-Python-Selection.md))
```Python
if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")
```

```Python
5 == 5    # True
7 != 3    # True
10 < 20   # True
5 >= 5    # True
"apple" == "banana"  # False
```

## Logical Operators

* They combine multiple boolean expressions to create more complex conditions.

Types
: `and`: Returns True if both operands are True.
: `or`: Returns True if at least one operand is True.
: `not`: Reverses the truth value of a Boolean expression.


Use in combining conditions:
```Python
if grade >= 90 and attendance >= 95:
    print("You are a great student!.")
```

```Python
True and False   # False
True or False    # True
not True         # False
```

## Operator Precedence

* Operator precedence is the order in which operators are evaluated in expressions.
* Use BIDMAS when doing operations in your programs. It is important as you might end up with a value that you don't want.
