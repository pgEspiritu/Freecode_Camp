# 🧩 What Are Lambda Functions and How Do They Work?

In Python, you’re used to defining functions using the `def` keyword, like this:

```python
def square(num):
    return num ** 2

print(square(4))  # 16
```
> But when working with higher-order functions like map() or filter(), you can use anonymous inline functions, called lambda functions.

---

## ⚡ Basic Lambda Syntax

A lambda function is written in a single line:


```python
lambda num: num ** 2
```

- Anonymous: No function name is required
- Expression only: Can only contain a single expression, not statements
- Commonly used in functions like map(), filter(), and sorted()

---

### 🔹 Example: Using Lambda with filter()

```python
numbers = [1, 2, 3, 4, 5]

even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # [2, 4]
```

Here:
- lambda x: x % 2 == 0 is an anonymous function
- filter() applies this function to each element in numbers
- Only elements that return True are included in the new list

---

## ⚠️ Best Practices

❌ Avoid assigning lambda to a variable unnecessarily

```python
numbers = [1, 2, 3, 4, 5]

square = lambda x: x ** 2
squared_numbers = list(map(square, numbers))
print(squared_numbers)  # [1, 4, 9, 16, 25]
```
- This defeats the purpose of using an anonymous function

- Better to use a regular function for readability:
```python
def square(num):
    return num ** 2

numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(square, numbers))
print(squared_numbers)  # [1, 4, 9, 16, 25]
```

❌ Avoid overly complicated lambda expressions

```python
result = (lambda x: (x**2 + 2*x - 1) if x > 0 else (x**3 - x + 4))(3)
print(result)  # 14
```
- While this works, it is hard to read

- Better approach: use a regular function
```python
def calculate_expression(x):
    if x > 0:
        return x**2 + 2*x - 1
    else:
        return x**3 - x + 4

print(calculate_expression(3))  # 14
```

---

## ✅ When to Use Lambda Functions
- Good for short, single-line expressions
- Perfect for inline usage with map(), filter(), and sorted()
- Avoid complex logic or readability issues

Regular functions are better for:
- Multi-line expressions
- Complex logic
- Code that needs to be reused or named

Lambda functions and regular functions each have their use cases. Using the right one improves both readability and maintainability of your Python programs
