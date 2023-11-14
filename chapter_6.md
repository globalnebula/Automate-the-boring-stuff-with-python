## Question 1

- Escape characters allow us to use characters which are otherwise not allowed to use in strings. For example, 
```python
print('Here another single quote can be used like this \'.')
```

## Question 2

- `\n` represents a newline and `\t` represents tab.


## Question 3

- To include a backslash character in a string, use a double backslash `\\`.


## Question 4

- The single quote character in `"Howl's Moving Castle"` isn't a problem because the string is enclosed in double quotes. Mixing single and double quotes is allowed in Python strings.

## Question 5

- To write a string with newlines without using `\n`, you can use triple-quotes (`'''` or `"""`) to create multiline strings.

## Question 6

  -  `'Hello, world!'[1]:` 'e'
  -  `'Hello, world!'[0:5]:` 'Hello'
  -  `'Hello, world!'[:5]:` 'Hello'
  -  `'Hello, world!'[3:]:` 'lo, world!'

## Question 7

  -  `'Hello'.upper():` 'HELLO'
  -  `'Hello'.upper().isupper():` True
  -  `'Hello'.upper().lower():` 'hello'

## Question 8

 - ```python
  'Remember, remember, the fifth of November.'.split()
   ``` 
 - `['Remember,', 'remember,', 'the', 'fifth', 'of', 'November.']`

 - ```python
  '-'.join('There can be only one.'.split())
   ```
 - `'There-can-be-only-one.'`

## Question 9

 - String methods for justification:

    - `Right-justify: rjust(width, fillchar=' ')`
    - `Left-justify: ljust(width, fillchar=' ')`
    - `Center: center(width, fillchar=' ')`

## Question 10
 
 - To trim whitespace characters from the beginning or end of a string, you can use the `strip()` method.

## Practice Projects

### Table Printer

```python
def printTable(tableData):
    colWidths = [0] * len(tableData)

    for i in range(len(tableData)):
        for j in range(len(tableData[i])):
            colWidths[i] = max(colWidths[i], len(tableData[i][j]))

    for j in range(len(tableData[0])):
        for i in range(len(tableData)):
            print(tableData[i][j].rjust(colWidths[i]), end=' ')
        print()


tableData = [['apples', 'oranges', 'cherries', 'banana'],
             ['Alice', 'Bob', 'Carol', 'David'],
             ['dogs', 'cats', 'moose', 'goose']]

printTable(tableData)

```

### Zombie Dice Bots

```python



```