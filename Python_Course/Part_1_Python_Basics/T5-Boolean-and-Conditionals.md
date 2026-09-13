# ⚡ How Do Conditional Statements and Logical Operators Work?

Conditional statements, or **conditionals**, let you control the flow of your program based on whether certain conditions are `True` or `False`.

Before we dive in, let's review **comparison operators**, which allow you to compare values and return a boolean.

---

## 🔹 Comparison Operators in Python

| Operator | Name                  | Description                                         |
|----------|----------------------|-----------------------------------------------------|
| `==`     | Equal                | Checks if two values are equal                     |
| `!=`     | Not equal            | Checks if two values are not equal                 |
| `>`      | Greater than         | Checks if the left value is greater than the right |
| `<`      | Less than            | Checks if the left value is less than the right    |
| `>=`     | Greater than or equal| Checks if the left value is greater than or equal |
| `<=`     | Less than or equal   | Checks if the left value is less than or equal    |

### Examples:

```python
print(3 > 4)  # False
print(3 < 4)  # True
print(3 == 4) # False
print(4 == 4) # True
print(3 != 4) # True
print(3 >= 4) # False
print(3 <= 4) # True
```
These operators are often used in conditionals to control program flow.

---

## 🔹 The if Statement

The most basic conditional is the if statement.
```python
if condition:
    pass  # Code executes if condition is True
```
- condition evaluates to True or False.
- The body of the if statement is defined by indentation.
- pass is a placeholder that does nothing, useful for empty blocks.

Example:
```python
age = 18

if age >= 18:
    print('You are an adult')  # You are an adult
```
> ⚠️ Python requires indentation for code blocks. Failing to indent raises an IndentationError:

```python
age = 18

if age >= 18:
print('You are an adult')  # IndentationError
```
> Recommended indentation: 4 spaces.

---

## 🔹 The else Clause

Use else to execute code when the if condition is False.
```python
age = 12

if age >= 18:
    print('You are an adult')
else:
    print('You are not an adult yet')  # You are not an adult yet
```

---

## 🔹 The elif Clause (Else If)

Use elif to check multiple conditions:
```python
age = 12

if age >= 18:
    print('You are an adult')
elif age >= 13:
    print('You are a teenager')
else:
    print('You are a child')  # You are a child
```

- You can use multiple elif statements for multiple ranges:
```python
age = 2

if age >= 65:
    print('You are a senior citizen')
elif age >= 30:
    print('You are an adult in your prime')
elif age >= 18:
    print('You are a young adult')
elif age >= 13:
    print('You are a teenager')
elif age >= 3:
    print('You are a young child')
else:
    print('You are a toddler or an infant')  # You are a toddler or an infant
```

---

# ⚡ What Are Truthy and Falsy Values, and How Do Boolean Operators and Short-Circuiting Work?

In the previous lesson, you learned how to use comparison operators and conditional statements to control program flow.  

Sometimes you need to **compare multiple values at once**, which can lead to nested conditionals:

```python
is_citizen = True
age = 25

if is_citizen:
    if age >= 18:
        print('You are eligible to vote')  # You are eligible to vote
else:
    print('You are not eligible to vote')
```
> The above checks if is_citizen is True, then evaluates age >= 18. Python prints "You are eligible to vote."

Nested ifs can be simplified with Boolean operators.

---

## 🔹 Truthy and Falsy Values

In Python, every value has an inherent boolean value:
- Truthy → evaluates to True
- Falsy → evaluates to False

Common falsy values:
- None
- False
- 0 (integer)
- 0.0 (float)
- "" (empty string)
> Everything else, like non-zero numbers or non-empty strings, is truthy.

You can check using bool():
```python
print(bool(False))   # False
print(bool(0))       # False
print(bool(''))      # False

print(bool(True))    # True
print(bool(1))       # True
print(bool('Hello')) # True
```

---

## 🔹 Boolean Operators

Python provides three Boolean (logical) operators:
- and
- or
- not

---

### 1️⃣ The `**and**` Operator
- Returns the first falsy operand, or the last operand if all are truthy.
- Both operands must be truthy for the expression to evaluate as truthy.
- Supports short-circuiting: stops evaluating as soon as the result is known.
```python
is_citizen = True
age = 25

print(is_citizen and age)  # 25
```

Using `**and**` in conditionals:
```python
if is_citizen and age >= 18:
    print('You are eligible to vote')  # You are eligible to vote
else:
    print('You are not eligible to vote')
```

---

### 2️⃣ The or Operator
- Returns the first truthy operand, or the last operand if all are falsy.
- Evaluates to truthy if at least one operand is truthy.
- Supports short-circuiting.
```python
age = 19
is_employed = False

print(age or is_employed)  # 19
```

Using `**or**` in conditionals:
```python
age = 19
is_student = True

if age < 18 or is_student:
    print('You are eligible for a student discount')  # You are eligible for a student discount
else:
    print('You are not eligible for a student discount')
```

---

### 3️⃣ The not Operator
- Unary operator → inverts the boolean value.
- Converts truthy → False and falsy → True.
```python
print(not '')       # True
print(not 'Hello')  # False
print(not 0)        # True
print(not 1)        # False
print(not False)    # True
print(not True)     # False
```

Example in a conditional:
```python
is_admin = False

if not is_admin:
    print('Access denied for non-administrators.')  # Access denied for non-administrators.
else:
    print('Welcome, Administrator!')
```
> not is_admin converts False → True, so the "Access denied..." message is printed.
