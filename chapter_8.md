## Question 1

- No, PyInputPlus does not come with the Python Standard Library..

## Question 2

- It is often imported with `import pyinputplus as pyip` to make the code shorter and more readable.

## Question 3

- `inputInt()` is used to get an integer input from the user, and it will reject non-integer inputs.
- `inputFloat()` is used to get a floating-point input from the user, and it will reject non-float inputs.

## Question 4

- You can use `inputInt(min=0, max=99)` to ensure that the user enters a whole number between 0 and 99.

## Question 5

- `allowRegexes` and `blockRegexes` can be passed lists of regular expression strings. `allowRegexes` allows inputs that match any of the provided regexes, while `blockRegexes` blocks inputs that match any of the provided regexes.

## Question 6

- If blank input is entered three times, `inputStr(limit=3)` will raise a `pyinputplus.RetryLimitException` since the user exceeded the specified limit of attempts.

## Question 7

- If blank input is entered three times, `inputStr(limit=3, default='hello')` returns the default value `'hello'` after the third attempt without raising an exception.

# Practice Projects

## Sandwich Maker

```python
import pyinputplus as pyip

    cheese_type = None
    if cheese == 'yes':
        cheese_type = pyip.inputMenu(['cheddar', 'Swiss', 'mozzarella'], numbered=True, prompt='Select a cheese type:\n')

    condiments = pyip.inputYesNo(prompt='Do you want mayo, mustard, lettuce, or tomato? (yes/no)\n', allow_none=True)
    
    num_sandwiches = pyip.inputInt(prompt='How many sandwiches do you want? (Enter a number greater than 0)\n', min=1)

    prices = {'wheat': 1.00, 'white': 1.00, 'sourdough': 1.50,
              'chicken': 2.00, 'turkey': 2.00, 'ham': 2.50, 'tofu': 2.50,
              'cheddar': 0.50, 'Swiss': 0.75, 'mozzarella': 1.00}

    total_cost = prices[bread] + prices[protein]
    if cheese_type:
        total_cost += prices[cheese_type]
    if condiments:
        total_cost += 0.25
    total_cost *= num_sandwiches

    print(f'\nTotal cost for {num_sandwiches} sandwich(es): ${total_cost:.2f}')


sandwich_maker()
```

## Multiplication Quiz

```python
import time
import random
import pyinputplus as pyip

def multiplication_quiz():
    score = 0
    num_questions = 10
    time_limit = 8

    for question_num in range(num_questions):
        num1 = random.randint(0, 9)
        num2 = random.randint(0, 9)
        correct_answer = num1 * num2

        print(f"\nQuestion {question_num + 1}: {num1} x {num2} = ?")

        try:
            user_answer = pyip.inputInt(prompt="Your answer: ", allowRegexes=[f'^{correct_answer}$'],
                                        blockRegexes=[('.*', 'Incorrect. Try again.')], timeout=time_limit, limit=3)
            print("Correct!")
            score += 1
        except pyip.TimeoutException:
            print(f"\nTime's up! The correct answer was {correct_answer}. Moving to the next question.")
        except pyip.RetryLimitException:
            print(f"\nOut of attempts. The correct answer was {correct_answer}. Moving to the next question.")

    print(f'\nQuiz complete! Your score: {score}/{num_questions}')

multiplication_quiz()

```