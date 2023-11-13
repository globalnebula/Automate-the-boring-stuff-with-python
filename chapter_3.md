## Question 1

- Functions are advantageous in programs because they promote code reusability, modularization, and abstraction. They allow you to break down your code into smaller, manageable pieces that can be reused across different parts of your program.

## Question 2

- The code in a function executes when the function is called.

## Question 3

- The `def` statement creates a function.

## Question 4

- A function is a block of code that performs a specific task and may take parameters. A function call is the act of invoking that function to execute its code.

## Question 5

- There is one global scope in a Python program. The number of local scopes depends on the number of functions, and each function creates its own local scope.

## Question 6

- Variables in a local scope cease to exist when the function call returns.

## Question 7

- A return value is the value that a function call gives the output or the evaluated answer to. Yes, a return value can be part of an expression.

## Question 8

- If a function does not have a return statement, the return value of a call to that function is `None`.

## Question 9

- To force a variable in a function to refer to the global variable, you can use the `global` keyword. For example:
  ```python
  def my_function():
      global x
      x = 10

## Question 10

 - The data type of None is NoneType.

## Question 11

 - It imports the module name "allyourpetsnamederic".

## Question 12
 
 - ```python
   import spam
   
   bacon.spam()
   ```

## Question 13

 - We need to use the `try and except` code block in the function to avoid crashing for unecesssary errors.

## Question 14

 - In the`try` clause you put a code that might raise and exception, and in the `except` clause you write the code to handle that exception.


### Practice Projects

```python

def collatz(number):
    if number%2==0:
        result = number//2
    else:
        result = 3*number+1

    return result

print(collatz(10))
```