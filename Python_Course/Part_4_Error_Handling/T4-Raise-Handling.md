# What Is the `raise` Statement and How Does It Work?

In Python, the `raise` statement is a powerful tool that allows you to **manually trigger exceptions** in your code. It gives you full control over **when** and **why** errors occur, helping you enforce rules, validate input, and make programs more predictable.

The `raise` statement is used to explicitly throw an exception at any point in your program to signal that an error condition has occurred.

---

## Basic Usage of the `raise` Statement

At its simplest, `raise` can be used to trigger a built-in exception with a custom error message.

```python
def check_age(age):
    if age < 0:
        raise ValueError('Age cannot be negative')
    return age

try:
    check_age(-5)
except ValueError as e:
    print(f'Error: {e}')
```

- raise: Triggers an exception immediately
- ValueError: A built-in exception type
- Custom message: Explains what went wrong

In this example, passing a negative age raises a ValueError, which is then caught and handled.

---

## Re-raising an Existing Exception

The raise keyword can be used without arguments to re-raise the exception currently being handled. This is useful when you want to log an error but still let it propagate upward.

```python
def process_data(data):
    try:
        result = int(data)
        return result * 2
    except ValueError:
        print('Logging: Invalid data received')
        raise  # Re-raises the same exception

try:
    process_data('abc')
except ValueError:
    print('Handled at higher level')

```
- raise (without arguments): Re-throws the current exception
- Allows logging or cleanup without swallowing the error

---

## Creating and Raising Custom Exceptions

You can define your own exception types by creating a class that inherits from Exception (or one of its subclasses).

```python
class InsufficientFundsError(Exception):
    def __init__(self, balance, amount):
        self.balance = balance
        self.amount = amount
        super().__init__(
            f'Insufficient funds: ${balance} available, ${amount} requested'
        )

def withdraw(balance, amount):
    if amount > balance:
        raise InsufficientFundsError(balance, amount)
    return balance - amount

try:
    withdraw(100, 150)
except InsufficientFundsError as e:
    print(f'Transaction failed: {e}')
```
- Custom exceptions make error handling clearer and more meaningful
- Especially useful for enforcing business rules


---

## Exception Chaining with raise ... from

Python allows you to link exceptions together using the from keyword, which helps preserve or suppress the original error context.

```python
def parse_config(filename):
    try:
        with open(filename, 'r') as file:
            data = file.read()
            return int(data)
    except FileNotFoundError:
        raise ValueError('Configuration file is missing') from None
    except ValueError as e:
        raise ValueError('Invalid configuration format') from e
```

Suppressing the Original Exception
```python
raise ValueError('Configuration file is missing') from None
```
- Hides the original exception
- Produces a cleaner traceback

Chaining Exceptions
```python
raise ValueError('Invalid configuration format') from e
```
- Preserves the original error
- Shows a clear cause-and-effect traceback

---

## Using assert as a Shortcut for raise

The assert statement is a shorthand way to raise an AssertionError when a condition is false.

```python
def calculate_square_root(number):
    assert number >= 0, 'Cannot calculate square root of negative number'
    return number ** 0.5

try:
    calculate_square_root(-4)
except AssertionError as e:
    print(f'Assertion failed: {e}')
```
- assert condition, message
- Best used for debugging and internal checks
- Can be disabled in optimized mode (python -O)

---

## Why the raise Statement Matters

The raise statement is essential for writing robust Python programs because it allows you to:

- Enforce validation rules
- Create meaningful and custom error messages
- Control program flow when something goes wrong
- Make debugging easier and errors more predictable

By using raise effectively, you can build applications that fail clearly, safely, and intentionally rather than crashing unexpectedly.
