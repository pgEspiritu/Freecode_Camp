# What Are Some Common Error Messages in Python?

When writing Python code, it's common to run into errors. Understanding these errors is key to debugging your code quickly and efficiently. These messages tell you exactly what went wrong, if you know how to read them.

Common Python errors include **SyntaxError**, **NameError**, **TypeError**, **IndexError**, and **AttributeError**. These occur when Python doesn't understand your code, or when your logic doesn't match the data you're working with.

## Examples of Common Python Errors

### SyntaxError

```python
print("Hello, world!"
# SyntaxError: unexpected EOF while parsing
```

This line is missing a closing parenthesis. Python raises a SyntaxError because the code doesn't follow proper syntax rules.

---

### NameError

```python
print(name)
# NameError: name 'name' is not defined
```

---

You're trying to print a variable that hasn't been defined yet. Python raises a NameError when it can't find a variable by that name.

### TypeError

```python
5 + "5"
# TypeError: unsupported operand type(s) for +: 'int' and 'str'
```
  
You can't add an integer and a string together. Python raises a TypeError when you try to perform an operation on incompatible data types.

---

### IndexError

```python
my_list = [1, 2, 3]
print(my_list[5])
# IndexError: list index out of range
```

You're trying to access an index that doesn't exist in the list. Python raises an IndexError when you go out of bounds.

---

### AttributeError

```python
num = 42
num.append(5)
# AttributeError: 'int' object has no attribute 'append'
```

Recognizing common Python error messages helps you fix problems faster. Instead of guessing, read the error message carefully — it often tells you exactly what went wrong and where to look.
