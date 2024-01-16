# GCSE Python - Variables

## Introduction

* Variables are named containers that store data values.
* Variables are used to store data and do something with it later in the program or to change the flow of the program.

## Naming Variables

* Rules and conventions for naming variables in Python:
    * Start with a letter or underscore (_).
    * Can only contain letters, numbers, and underscores.
    * Case-sensitive (e.g., `name` is different from `Name`).
* Use descriptive and meaningful names to improve code readability.

## Declaring and Assigning Values

* You declare variables by doing what you did in [data types](GCSE-Python-Data-Types.md)
``` Python
    
    my_integer = 0
    my_descriptive_variable = ""
```
* This is assignment
```Python
    my_integer = x + 1
    my_descriptive_variable = my_old_string + "abc"
```
* Declaration is setting up a variable so it can be used throughout the program
* Assignment is assigning a value to a variable so you can use it to be used to calculate something.

## Variable Scope

* Variable scope is the accessibility of a variable within different parts of a program.
* Global variables are created outside a function and can be access within multiple functions.
* Local variables are created inside a function and can only be accessed withing their respective function.

```Python
global_var = 3 # a global var

def main():
    result = AddTheVariables()
    print(result)

def AddTheVariables():
    local_var = 2 # a local var
    result_to_return = global_var + local_var
    return result_to_return # returns the value calculated back to the main function for later use.

if __name__ == "__main__": # This bit of code tells the program to run the main function on start
    main()
```
this outputted:
```Python
5
```
which was expected as it added 3 and 2 together.
