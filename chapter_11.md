## Question 1

-   ```python
   assert isinstance(spam, int) and spam < 10, "AssertionError: spam should be an integer less than 10"
   ```

## Question 2

```python
assert eggs.lower() != bacon.lower(), "AssertionError: eggs and bacon should have different case-insensitive strings"
```

## Question 3

```python
assert False, "AssertionError: This assert statement always triggers"
```

## Question 4

```python
import logging
logging.basicConfig(level=logging.DEBUG)
```

## Question 5

```python
import logging
logging.basicConfig(filename='programLog.txt', level=logging.DEBUG)
```

## Question 6

  - Five logging levels:
     - DEBUG
     - INFO
     - WARNING
     - ERROR
     - CRITICAL

## Question 7

- To disbale all logging messages

```python
logging.disable(logging.CRITICAL)
```

## Question 8

- Logging messages can be easily disabled without removing the code.
- Logging provides different levels, making it easier to filter and manage messages.
- Logging supports writing messages to files, in addition to the console.

## Question 9

- Step Over: Executes the current line of code and stops at the next line.
- Step In: Steps into a function or method called on the current line.
- Step Out: Executes the remaining lines of the current function or method and stops at the line after the function call.

## Question 10

- The debugger will stop when it encounters a breakpoint or reaches the end of the program.

## Question 11

- A breakpoint is a point in the code where the debugger will pause and allow the user to interactively inspect the program's state.

## Question 12

- To set a breakpoint in Mu, click on the line number in the left margin where you want to set the breakpoint.


### Practice Problems

## Debugging Coin Toss
```python
import random

guess = ''
while guess not in ('heads', 'tails'):
    print('Guess the coin toss! Enter heads or tails:')
    guess = input()
toss = random.choice(['heads', 'tails'])
if toss == guess:
    print('You got it!')
else:
    print('Nope! Guess again!')
    guess = input()
    if toss == guess:
        print('You got it!')
    else:
        print('Nope. You are really bad at this game.')
```