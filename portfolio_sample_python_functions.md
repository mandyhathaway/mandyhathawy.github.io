# Understanding Functions in Python

## Overview

Functions are reusable blocks of code that perform specific tasks. They help you organize your code, avoid repetition, and make your programs easier to understand and maintain.

This guide explains what functions are, why they're useful, and how to create and use them in Python.

---

## What is a Function?

A function is a named section of code that you can run (or "call") whenever you need it. Think of it like a recipe: you write the instructions once, then follow those same instructions whenever you want to make that dish.

### Why Use Functions?

Functions solve several common programming challenges:

- **Avoid repetition**: Write code once, use it many times
- **Organize code**: Break large programs into smaller, manageable pieces
- **Improve readability**: Give meaningful names to blocks of code
- **Simplify testing**: Test individual functions separately
- **Enable reuse**: Share functions across different programs

---

## Basic Function Syntax

Here's the basic structure of a Python function:

```python
def function_name():
    # Code to execute
    print("Hello from inside the function!")
```

Let's break down each part:

- **`def`**: A keyword that tells Python you're defining a function
- **`function_name`**: The name you choose for your function (use descriptive names)
- **`()`**: Parentheses that can hold parameters (explained below)
- **`:`**: A colon that marks the start of the function body
- **Indented code**: The instructions that run when you call the function

### Calling a Function

To use (or "call") a function, write its name followed by parentheses:

```python
def greet():
    print("Hello, world!")

# Call the function
greet()
```

**Output:**
```
Hello, world!
```

---

## Parameters and Arguments

Functions become more powerful when they can accept input values called **parameters**.

### Defining Parameters

Parameters are variables you define inside the parentheses:

```python
def greet(name):
    print(f"Hello, {name}!")
```

When you call this function, you provide an **argument** (the actual value):

```python
greet("Alice")  # Output: Hello, Alice!
greet("Bob")    # Output: Hello, Bob!
```

### Multiple Parameters

Functions can accept multiple parameters, separated by commas:

```python
def introduce(name, age):
    print(f"My name is {name} and I am {age} years old.")

introduce("Alice", 25)  # Output: My name is Alice and I am 25 years old.
```

### Default Parameter Values

You can provide default values for parameters. If no argument is provided when calling the function, the default value is used:

```python
def greet(name="friend"):
    print(f"Hello, {name}!")

greet()          # Output: Hello, friend!
greet("Alice")   # Output: Hello, Alice!
```

---

## Return Values

Functions can send values back to the code that called them using the `return` keyword.

### Basic Return Statement

```python
def add(a, b):
    result = a + b
    return result

sum = add(5, 3)
print(sum)  # Output: 8
```

### Why Return Values Matter

Without `return`, a function performs actions but doesn't give you a value to use:

```python
# Function without return
def add_no_return(a, b):
    result = a + b
    print(result)

# Function with return
def add_with_return(a, b):
    result = a + b
    return result

# Using the functions
add_no_return(5, 3)        # Prints 8, but you can't use the value
sum = add_with_return(5, 3)  # Returns 8, which you can store and use
print(sum * 2)             # Output: 16
```

### Returning Multiple Values

Python functions can return multiple values as a tuple:

```python
def get_dimensions():
    width = 100
    height = 50
    return width, height

w, h = get_dimensions()
print(f"Width: {w}, Height: {h}")  # Output: Width: 100, Height: 50
```

---

## Scope: Where Variables Live

Variables created inside a function only exist within that function. This concept is called **scope**.

### Local vs Global Scope

```python
# Global variable
message = "I'm global"

def my_function():
    # Local variable
    inner_message = "I'm local"
    print(message)        # Can access global variable
    print(inner_message)  # Can access local variable

my_function()
# print(inner_message)  # ERROR: inner_message doesn't exist outside the function
```

### Best Practice

Avoid relying on global variables inside functions. Instead, pass values as parameters:

```python
# Better approach
def greet(message):
    print(message)

greeting = "Hello, world!"
greet(greeting)
```

---

## Common Use Cases

### 1. Calculations

```python
def calculate_area(length, width):
    """Calculate the area of a rectangle."""
    return length * width

area = calculate_area(10, 5)
print(f"Area: {area}")  # Output: Area: 50
```

### 2. Data Validation

```python
def is_valid_age(age):
    """Check if age is within valid range."""
    return 0 <= age <= 120

print(is_valid_age(25))   # Output: True
print(is_valid_age(-5))   # Output: False
print(is_valid_age(150))  # Output: False
```

### 3. String Formatting

```python
def format_name(first, last):
    """Format a full name properly."""
    return f"{first.title()} {last.title()}"

print(format_name("alice", "smith"))  # Output: Alice Smith
```

### 4. List Processing

```python
def get_even_numbers(numbers):
    """Return only even numbers from a list."""
    evens = []
    for num in numbers:
        if num % 2 == 0:
            evens.append(num)
    return evens

numbers = [1, 2, 3, 4, 5, 6]
print(get_even_numbers(numbers))  # Output: [2, 4, 6]
```

---

## Documentation Strings (Docstrings)

Professional Python code includes documentation strings that explain what functions do:

```python
def calculate_discount(price, discount_percent):
    """
    Calculate the final price after applying a discount.
    
    Parameters:
    price (float): The original price
    discount_percent (float): The discount percentage (0-100)
    
    Returns:
    float: The discounted price
    """
    discount_amount = price * (discount_percent / 100)
    return price - discount_amount
```

Docstrings appear as the first statement in a function and use triple quotes (`"""`).

---

## Common Mistakes and How to Avoid Them

### Mistake 1: Forgetting Parentheses

```python
def greet():
    print("Hello!")

# Wrong - this references the function but doesn't call it
greet

# Correct - parentheses actually call the function
greet()
```

### Mistake 2: Not Returning a Value

```python
# Wrong - function prints but doesn't return
def add(a, b):
    print(a + b)

result = add(5, 3)  # result is None, not 8

# Correct - function returns the value
def add(a, b):
    return a + b

result = add(5, 3)  # result is 8
```

### Mistake 3: Wrong Number of Arguments

```python
def greet(name, age):
    print(f"Hello {name}, you are {age}")

# Wrong - missing an argument
greet("Alice")  # ERROR: missing 1 required argument: 'age'

# Correct
greet("Alice", 25)
```

---

## Practice Exercises

Try creating these functions to reinforce your understanding:

1. **Temperature Converter**: Write a function that converts Celsius to Fahrenheit
   - Formula: F = (C × 9/5) + 32
   
2. **Password Validator**: Write a function that checks if a password is at least 8 characters long

3. **List Average**: Write a function that takes a list of numbers and returns their average

4. **Name Reverser**: Write a function that takes a full name ("First Last") and returns it reversed ("Last, First")

---

## Next Steps

Now that you understand functions, you can:

- Learn about **lambda functions** (anonymous, single-line functions)
- Explore **recursive functions** (functions that call themselves)
- Study **decorators** (functions that modify other functions)
- Investigate **built-in functions** like `len()`, `max()`, `sorted()`

---

## Additional Resources

- [Python Official Documentation: Defining Functions](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
- [Real Python: Defining Your Own Python Function](https://realpython.com/defining-your-own-python-function/)
- [W3Schools: Python Functions](https://www.w3schools.com/python/python_functions.asp)

---

**Document Information:**
- **Author:** Mandy Hathaway
- **Last Updated:** February 2026
- **Audience:** Python beginners
- **Prerequisites:** Basic understanding of Python syntax and variables
