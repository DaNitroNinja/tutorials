# GCSE Python - Data Types

## Introduction

* Data types are a type of data item that define what is being stored to the computer.
* Data types are important as they allow your program to figure out what is being stored in a variable.

## Common Data Types in GCSE AQA

Examples
: Integers (whole numbers)
: Real numbers (decimal numbers)
: Strings (text)
: Booleans (True or False)

## Representing Data Types in Python

* Declare data types by writing a decimal point or "" for a string.
``` Python
# Example of data types

age = 25  # Integer
price = 19.99  # Real number
name = "Alice"  # String
is_valid = True  # Boolean
toys = ["car", "game", "chess"]
```


## Type Conversion

* Type conversion is the process of converting a data type to a different data type like an int to a string.
* You might need to turn a string into a list to be able to see whether a specific character is present or not.
``` Python
number_string = "123"
number_int = int(number_string)  # Convert string to integer
```
or
``` Python
my_sentence = "The dog jumped over the fence"
my_sentence_list = my_sentence.split()

print(my_sentence_list)
```
which will output
``` Python
['The', 'dog', 'jumped', 'over', 'the', 'fence']
```

