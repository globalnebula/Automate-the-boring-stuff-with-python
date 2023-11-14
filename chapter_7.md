## Question 1

- the function that creates Regex objects is `re.compile`.

## Question 2

- Raw strings are string having `r` as the prefix and are often used to avoid unintentional escaping of backslashes. Usually backslashes are used to escape certain special characters but raw string help us to use them as literal characters.

## Question 3

- The `search()` method returns an object if the pattern is found and `None` if there is no such pattern.

## Question 4

- You can use the `group()` method of the Match object to get the actual strings that match the pattern. `group(0)` returns the entire match, and additional groups are accessed with `group(1)`, `group(2)` etc.

## Question 5

- Group 0 covers the entire match. Group 1 covers the first set of three digits, and Group 2 covers the second set of three digits followed by a hyphen and four digits.

## Question 6

- To match actual parentheses and period characters, you can use a backslash `\` before them. Period :- `\.`
      Parenthesis :- `\( \)`

## Question 7

- If the regular expression has no groups, findall() returns a list of strings.

## Question 8

- The `|` character in regular expressions signifies an OR operation. It allows you to match either the pattern on its left or the pattern on its right.

## Question 9

- It makes the preceding character or group optional (matches 0 or 1 occurrence).
  
- In non-greedy mode, it makes the `*, +, or {}` quantifiers non-greedy.

## Question 10

- The `+` character matches one or more occurrences of the preceding character or group.

- The `*` character matches zero or more occurrences of the preceding character or group.

## Question 11

- `{3}` matches exactly 3 occurrences of the preceding character or group.
- `{3,5}` matches between 3 and 5 occurrences of the preceding character or group.

## Question 12

- `\d` matches any digit (equivalent to [0-9]).

- `\w` matches any word character (alphanumeric + underscore).

- `\s` matches any whitespace character (spaces, tabs, newlines).

## Question 13

This captial shortstand characters do exact opposite of the small shortstand character.
- `\D` matches any non-digit character.
- `\W` matches any non-word character.
- `\S` matches any non-whitespace character.

## Question 14

- `.*` is a greedy match that matches as much as possible.
- `.*?` is a non greedy or lazy match that matches as much little as possible.

## Question 15

The character class to match all numbers and lowercase letters is `[a-z0-9]`

## Question 16

You can make a regular expression case-insensitive by using the `re.IGNORECASE`.

## Question 17

- The . character normally matches any character except a newline (\n).
- If re.DOTALL is passed as the second argument to re.compile(), the . character matches any character, including a newline.

## Question 18

- It will return `'X drummers, X pipers, five rings, X hens'`.

## Question 19

- Passing `re.VERBOSE` as the second argument to `re.compile()` allows you to write more readable regular expressions by ignoring whitespace and adding comments.

## Question 20

- `r'\d{1,3}(,\d{3})*$'`

## Question 21

- `r'^[A-Z][a-zA-Z]* Watanabe$'`

## Question 22

- `r'^(Alice|Bob|Carol) (eats|pets|throws) (apples|cats|baseballs)\.$'`. We should further use `re.IGNORECASE` to allow case insensitivity.

### Practice Projects

## Date detection
```python
import re

def date_detection(date_string):
    date_regex = re.compile(r'^(0[1-9]|[12][0-9]|3[01])/(0[1-9]|1[0-2])/(100[0-9]|1[0-9]{3}|[2-9][0-9]{3})$')
    
    match = date_regex.match(date_string)
    
    if match:
        day, month, year = match.groups()
        print(f"Valid date: {day}/{month}/{year}")
    else:
        print("Invalid date")


date_detection('31/02/2020')
date_detection('29/02/2020')
date_detection('31/04/2021')
```

## Strong Password

```python
import re

def strong_password_detection(password):
    password_regex = re.compile(r'^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$')
    
    if password_regex.match(password):
        print("Strong password")
    else:
        print("Weak password")

strong_password_detection('Abcd1234')
strong_password_detection('abc123')  

```

## Regex version of strip() method

```python
import re

def regex_strip(s, chars=None):
    if chars:
        return re.sub(f'^[{re.escape(chars)}]+|[{re.escape(chars)}]+$', '', s)
    else:
        return re.sub(r'^\s+|\s+$', '', s)

text = "    Hello, world!    "
print(f'Original: "{text}"')
print(f'Stripped: "{regex_strip(text)}"')
print(f'Stripped with "oH": "{regex_strip(text, "oH")}"')

```