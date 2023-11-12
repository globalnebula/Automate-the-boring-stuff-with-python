## Question 1
- Operators: *, -, /, +
- Values: 'hello', -88.8, 5

## Question 2
- Variable: spam
- String: 'spam'

## Question 3
- Integer, Floating-point number, String

## Question 4
- An expression is made up of values combined with operators. All expressions evaluate to a single value.

## Question 5
- An expression is a combination of values and operators that can be evaluated to produce a result. A statement is a complete line of code that performs some action. An assignment statement, like `spam = 10`, is a statement.

## Question 6
- The variable `bacon` contains the value 20 after the code runs. However, the expression `bacon + 1` doesn't modify the value of `bacon` unless you assign it back. So, `bacon` remains 20.

## Question 7
- 'spam' + 'spamspam' evaluates to 'spamspamspam'
- 'spam' * 3 evaluates to 'spamspamspam'

## Question 8
- `eggs` is a valid variable name because it starts with a letter. `100` is invalid because it starts with a number.

## Question 9
- Integer: `int()`
- Floating-point number: `float()`
- String: `str()`

## Question 10
- The expression causes an error because you are trying to concatenate a string ('I have eaten ') with an integer (99). To fix it, convert 99 to a string by keeping single quotations for 99 like this `'99'`.

   ```python
   'I have eaten ' + '99' + ' burritos.'
   ```
## Extra Credit

### `len()` Function

- The `len()` function is used to get the length (the number of items) of an object.
- Example:
  ```python
  my_list = [1, 2, 3, 4, 5]
  length = len(my_list)
  print(length)  # Output: 5

### `round()` Function

- the `round()` function is used to round a floating-point number to the nearest integer or to a specified number of decimals.
- Example:
  ```python
  x = round(3.14159)
  print(x)
  ```