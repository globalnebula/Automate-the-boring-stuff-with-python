## Question 1

- True and False

## Question 2

- and, or, not

## Question 3

- and
  - True and True = True
  - True and False = False
  - False and True = False
  - False and False = False

  or
  - True or True = True
  - True or False = True
  - False or True = True
  - False or False = False

  not
  - not True = False
  - not False = True

## Question 4

- (5 > 4) and (3 == 5) = False
- not (5 > 4) = False
- (5 > 4) or (3 == 5) = True
- not ((5 > 4) or (3 == 5)) = False
- (True and True) and (True == False) = False
- (not False) or (not True) = True

## Question 5

- ==, !=, >, <, >=, <=

## Question 6

- The equal to operator (==) is used to compare values for equality.
- The assignment operator (=) is used to assign a value to a variable.

## Question 7

- A condition is a statement that has a boolean output; True or False. It is used to control the flow of a program, allowing different code to be executed based on whether the condition is True or False.

## Question 8

- 1. INITIALISATION or DECLARATION
 `spam = 0`

- 2. 
  CONDITIONAL BLOCK
  ```python
  if spam == 10:
      print('eggs')
      if spam > 5:
          print('bacon')
      else:
          print('ham')
      print('spam')
  ```
- 3.
  OUTPUT BLOCK
  ```python
  print('spam')
  ```

## Question 9

```python
if spam == 1:
    print('Hello')
elif spam == 2:
    print('Howdy')
else:
    print('Greetings!')
```

## Question 10

`Ctrl + c` can be used to break of out of an infinitely executing loop or program.

## Question 11

   - break is used to exit a loop before the loop ends or prematurely.
   - continue is used to skip the rest of the code inside a loop and move to the next iteration.

## Question 12

   - range(10): Generates numbers from 0 to 9.  (0,1,2,3,4,5,6,7,8,9)
   - range(0, 10): Same as above, but specifying the start point.   (0,1,2,3,4,5,6,7,8,9)
   - range(0, 10, 1): Same as above, but specifying the starting point and the common difference. (0,1,2,3,4,5,6,7,8,9)

## Question 13

    - For Loop

    ```python

for i in range(1, 11):
    print(i)
    ```

   - While Loop

   ```python
        i = 1  
        while i <= 10:
            print(i)
            i += 1
    ```
## Question 14

    ```python

    import spam
    spam.bacon()
    ```

## Extra Credit

- round(): Rounds a floating-point number to the nearest integer or a specified number of decimals.
        Example: round(3.14159, 2) returns 3.14.

- abs(): Returns the absolute value of a number.
        Example: abs(-5) returns 5.