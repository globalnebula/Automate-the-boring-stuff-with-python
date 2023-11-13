## Question 1

- `[]` represents an empty list.

## Question 2

- To assign the value 'hello' as the third value in a list stored in a variable named `spam`, you can do the following:
  ```python
  spam[2] = 'hello'
  ```

## Question 3

 - Given spam = ['a', 'b', 'c', 'd']

   spam[int(int('3' * 2) // 11)] evaluates to 'd'.

## Question 4

 - spam[-1] evaluates to 'd'.

## Question 5

 - spam[:2] evaluates to ['a', 'b'].

## Question 6

 - bacon.index('cat') evaluates to 1.

## Question 7

 - bacon.append(99) makes the list value in bacon look like [3.14, 'cat', 11, 'cat', True, 99].

## Question 8

 - bacon.remove('cat') makes the list value in bacon look like [3.14, 11, 'cat', True, 99].

## Question 9

 - Operators for list concatenation: +
 - Operator for list replication: *

## Question 10

 - The append() method adds a value to the end of the list. The insert() method adds a value at a specific index in the list.

## Question 11

 - Two ways to remove values from a list:
   Using the remove() method by specifying the value to be removed.Using the del statement by specifying the index of the value to be removed.

## Question 12

 - List values and string values both support indexing, slicing, and iteration.

## Question 13

 - Lists are mutable, meaning their values can be changed. Tuples are immutable, meaning their values cannot be changed.

## Question 14

 - To type the tuple value with the integer value 42, you can use parentheses: (42,).

## Question 15

 - To get the tuple form of a list value, you can use the tuple() function. To get the list form of a tuple value, you can use the list() function.

## Question 16

 - Variables that “contain” list values actually contain references to lists.

## Question 17

 - copy.copy() creates a shallow copy of a list, meaning it copies the top-level elements, but not the nested elements.
   copy.deepcopy() creates a deep copy, copying both the top-level and nested elements.

### Practice Projects

## Comma Code
   ```python
    def commaCode(x):
    result = ''
    for i in range(len(x)):
        if i == len(x) - 2:
            result += x[i] + ' and ' + x[i+1]
            break
        elif len(x) == 1:
            result += x[i]
            break
        else:
            result += x[i] + ', '
    return result

s = list(input().split())
result = commaCode(s)
print(result)

   ```

## Coin Flip Streaks

```python
import random

numberOfStreaks = 0

for experimentNumber in range(10000):

    coin_flips = ['H' if random.choice([0, 1]) == 0 else 'T' for _ in range(100)]
    flips = ''.join(coin_flips)

    for i in range(len(flips) - 5):
        if flips[i:i + 6] == 'HHHHHH' or flips[i:i + 6] == 'TTTTTT':
            numberOfStreaks += 1
            break

result = numberOfStreaks / 100

print(f'Chance of streak: {result}')


```

## Character Picture Grid

```python

grid = [['.', '.', '.', '.', '.', '.'],
        ['.', 'O', 'O', '.', '.', '.'],
        ['O', 'O', 'O', 'O', '.', '.'],
        ['O', 'O', 'O', 'O', 'O', '.'],
        ['.', 'O', 'O', 'O', 'O', 'O'],
        ['O', 'O', 'O', 'O', 'O', '.'],
        ['O', 'O', 'O', 'O', '.', '.'],
        ['.', 'O', 'O', '.', '.', '.'],
        ['.', '.', '.', '.', '.', '.']]

for y in range(len(grid[0])):
    for x in range(len(grid)):
        print(grid[x][y], end='')
    print()

```