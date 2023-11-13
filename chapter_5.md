## Question 1

- ```python
  foo = {}
  ```

## Question 2

- ```python
  bar = {'foo' : 42}
  ```

## Question 3

- The main difference between a dictionary and a list is that a dictionary uses keys to access its elements, while a list uses indices.
Dictionary contains Key - Value pairs.

## Question 4

- It will raise a KeyError since the key `'foo'` does not exist in the dictionary.

## Question 5

- `'cat'` in spam checks if there is a key `'cat'` in the dictionary, while `'cat'` in spam.keys() does the same.

## Question 6

- `cat` in spam checks if there is a key `'cat'` in the dictionary, while `'cat'` in spam.values() checks if `'cat'` is a value in the dictionary.

## Question 7

- ```python
  spam.setdefault('color', 'black')
  ```

## Question 8
```python
import pprint
pp = pprint.PrettyPrinter()
pp.pprint(dictionary_to_pretty_print)
```


### Practice Projects

## Chess Dictionary Validator

```python

def isValidChessBoard(board):

    black_pieces = {'pawn': 0, 'knight': 0, 'bishop': 0, 'rook': 0, 'queen': 0, 'king': 0}
    white_pieces = {'pawn': 0, 'knight': 0, 'bishop': 0, 'rook': 0, 'queen': 0, 'king': 0}


    valid_positions = set(f'{i}{j}' for i in range(1, 9) for j in 'abcdefgh')


    for position, piece in board.items():
        if piece[0] not in ['b', 'w']:
            return False  

        if piece[1:] not in ['pawn', 'knight', 'bishop', 'rook', 'queen', 'king']:
            return False


        if piece[0] == 'b':
            black_pieces[piece[1:]] += 1
        else:
            white_pieces[piece[1:]] += 1


        if position not in valid_positions:
            return False


    if black_pieces != {'pawn': 8, 'knight': 2, 'bishop': 2, 'rook': 2, 'queen': 1, 'king': 1}:
        return False
    if white_pieces != {'pawn': 8, 'knight': 2, 'bishop': 2, 'rook': 2, 'queen': 1, 'king': 1}:
        return False

    if 'bking' not in board.values() or 'wking' not in board.values():
        return False

    return True

chess_board = {'1h': 'bking', '6c': 'wqueen', '2g': 'bbishop', '5h': 'bqueen', '3e': 'wking'}
result = isValidChessBoard(chess_board)
print(result)
```

## Fantasy Game Inventory

```python

def displayInventory(inventory):
    print("Inventory:")
    item_total = 0
    for k, v in inventory.items():
        print(f"{v} {k}")
        item_total += v
    print("Total number of items:", item_total)


stuff = {'rope': 1, 'torch': 6, 'gold coin': 42, 'dagger': 1, 'arrow': 12}
displayInventory(stuff)

```

## List to Inventory function

```python

def displayInventory(inventory):
    print("Inventory:")
    item_total = 0
    for k, v in inventory.items():
        print(f"{v} {k}")
        item_total += v
    print("Total number of items:", item_total)


def addToInventory(inventory, addedItems):
    for item in addedItems:
        inventory[item] = inventory.get(item, 0) + 1
    return inventory


inv = {'gold coin': 42, 'rope': 1}
dragonLoot = ['gold coin', 'dagger', 'gold coin', 'gold coin', 'ruby']
inv = addToInventory(inv, dragonLoot)
displayInventory(inv)

```
