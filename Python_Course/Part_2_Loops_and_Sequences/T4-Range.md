# 🔢 What Are Ranges and How Can You Use Them in a Loop?

The `range()` function is used to generate a sequence of integers in Python. It is commonly used with loops, especially `for` loops.

---

## 🧩 Basic Syntax

```python
range(start, stop, step)
```
- start (optional): The starting number (default is 0)
- stop (required): The number where the sequence stops (not included)
- step (optional): The increment (default is 1)

---

## ▶️ Basic Example

```python
for num in range(3):
    print(num)
```

✅ Output

```text
0
1
2
```
> The number 3 is not included because the stop value is non-inclusive.

---

## 🚦 Using the start Argument

If you want to start from a number other than 0, specify the start value:

```python
for num in range(1, 5):
    print(num)
```

✅ Output
```text
1
2
3
4
```

---

## ➕ Using the step Argument

By default, numbers increase by 1. You can change this using the step argument.

Example: Even Numbers from 2 to 10
```python
for num in range(2, 11, 2):
    print(num)
```

✅ Output
```text
2
4
6
8
10
```

---

## ❌ Missing Arguments Error

The range() function requires at least one argument. If none are provided, Python raises an error:

```python
range()
```

⚠️ Error
```text
TypeError: range expected at least 1 argument, got 0
```

---

## ❌ Float Values Are Not Allowed

The range() function only accepts integers. Passing a float will cause an error:

```python
range(1.5, 10)
```

⚠️ Error
```text
TypeError: 'float' object cannot be interpreted as an integer
```

---

## 🔽 Decrementing with a Negative Step

You can count backwards by using a negative step value:

```python
for num in range(40, 0, -10):
    print(num)
```

✅ Output
```text
40
30
20
10
```

---

## 📋 Creating a List from range()

You can convert a range into a list using the list() constructor:

```python
numbers = list(range(2, 11, 2))
print(numbers)
```

✅ Output
```text
[2, 4, 6, 8, 10]
```

---

## 🎯 Summary

- range() generates a sequence of integers
- The stop value is always excluded
- Only integers are allowed
- Very useful for loops and iteration
- Commonly combined with for loops
