# Path and File Handling Practice Questions

## Question 1

- A relative path is relative to the current working directory.

## Question 2

- An absolute path starts with the root directory or drive.

## Question 3

- On Windows, `Path('C:/Users') / 'Al'` evaluates to `C:\Users\Al`.

## Question 4

- `'C:/Users' / 'Al'` would result in an error on Windows because the `/` operator is not supported for string concatenation. You should use `os.path.join` or `Path` for path manipulation.

## Question 5

- `os.getcwd()` returns the current working directory, and `os.chdir()` changes the current working directory.

## Question 6

- The `.` folder represents the current directory, and the `..` folder represents the parent directory.

## Question 7

- In `C:\bacon\eggs\spam.txt`, the dir name is `C:\bacon\eggs`, and the base name is `spam.txt`.

## Question 8

- The three "mode" arguments for the `open()` function are:
  - `'r'`: Read mode.
  - `'w'`: Write mode (creates a new file or truncates an existing file).
  - `'a'`: Append mode (writes to the end of the file).

## Question 9

- If an existing file is opened in write mode (`'w'`), it will be truncated, and its content will be erased.

## Question 10

- The `read()` method reads the entire file as a single string, while the `readlines()` method reads the file line by line and returns a list of lines.

## Question 11

- A shelf value resembles a dictionary data structure.


## Practice proojects

## Madlibs Program

```python
import re

def mad_libs(text):
    placeholders = ['ADJECTIVE', 'NOUN', 'ADVERB', 'VERB']

    for placeholder in placeholders:
        replacement = input(f"Enter a {placeholder.lower()}: ")
        text = re.sub(placeholder, replacement, text, count=1)

    return text

with open('mad_libs_template.txt', 'r') as file:
    template_text = file.read()

mad_libs_result = mad_libs(template_text)

print("\nGenerated Mad Libs Story:\n", mad_libs_result)

with open('mad_libs_result.txt', 'w') as result_file:
    result_file.write(mad_libs_result)
```

## Regex Search

```python
import os
import re

def regex_search(folder_path, regex_pattern):
    for filename in os.listdir(folder_path):
        if filename.endswith('.txt'):
            file_path = os.path.join(folder_path, filename)

            with open(file_path, 'r') as file:
                for line_number, line in enumerate(file, start=1):
                    if re.search(regex_pattern, line):
                        print(f"{file_path}, Line {line_number}: {line.strip()}")

folder_path = input("Enter the folder path: ")
regex_pattern = input("Enter the regex pattern: ")
regex_search(folder_path, regex_pattern)

```

## MultiClipBoard

```python
import shelve
import pyperclip
import sys

mcbShelf = shelve.open('mcb')

if len(sys.argv) == 3 and sys.argv[1].lower() == 'save':
    mcbShelf[sys.argv[2]] = pyperclip.paste()
elif len(sys.argv) == 2:

    if sys.argv[1].lower() == 'list':
        pyperclip.copy(str(list(mcbShelf.keys())))
    elif sys.argv[1] in mcbShelf:
        pyperclip.copy(mcbShelf[sys.argv[1]])
    elif sys.argv[1].lower() == 'delete':

        print("Deleting keyword:", sys.argv[2])
        del mcbShelf[sys.argv[2]]
    elif sys.argv[1].lower() == 'deleteall':

        print("Deleting all keywords.")
        mcbShelf.clear()

mcbShelf.close()
```