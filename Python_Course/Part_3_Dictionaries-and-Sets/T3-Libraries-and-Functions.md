# 📚 What Is the Python Standard Library, and How Do You Import a Module?

In software development, a **library** is like a toolbox for developers.

Instead of implementing everything from scratch, a library provides **pre-written and reusable code**, such as functions, classes, and data structures that you can use in your projects.

---

## 🧰 The Python Standard Library

Python comes with an extensive **standard library** made up of built-in modules. These modules are standardized, well-tested solutions for many common programming tasks, such as:

- Interacting with the operating system
- Working with files
- Networking
- Handling dates and time
- Performing mathematical operations
- Using regular expressions
- Testing and debugging code

Some popular built-in modules include:

- **math** – advanced mathematical operations  
- **random** – random number generation  
- **re** – regular expressions  
- **datetime** – working with dates and times  

---

## 📦 Importing a Module

To access the contents of a module, you use an **import statement**. Import statements are usually placed at the top of a Python file.

### Basic Import

```python
import module_name
```

Example:

```python
import math
```

To use a function from the module, use dot notation:

```python
math.sqrt(36)
```

---

## ✏️ Importing with an Alias

You can assign an alias to a module using as. This is useful for shortening long module names or avoiding naming conflicts.

```python
import module_name as module_alias
```

Example:

```python
import math as m
m.sqrt(36)
```

---

## 🎯 Importing Specific Items from a Module

If you only need certain functions or classes, you can import them directly:

```python
from module_name import name1, name2
```

Example:

```python
from math import radians, sin, cos
```

from math import radians, sin, cos

```python
angle_degrees = 40
angle_radians = radians(angle_degrees)

sine_value = sin(angle_radians)
cos_value = cos(angle_radians)

print(sine_value) # 0.6427876096865393
print(cos_value)  # 0.766044443118978
```

Importing with Aliases

```python
from module_name import name1 as alias1, name2 as alias2
```

---

## ⚠️ Importing Everything from a Module

You can import all public names from a module using an asterisk:

```python
from module_name import *
```

Example:

```python
from math import *
print(sqrt(36))  # 6.0
print(pow(5, 2)) # 25.0
print(exp(1))    # 2.718281828459045
```
🚫 This is generally discouraged because:
- It can cause name conflicts
- It makes code harder to read and debug

---

## 🧮 Importing Constants and Classes

Importing a Constant

```python
import math
print(math.pi)
```

Importing and Using a Class

```python
import datetime

birthday = datetime.date(1959, 7, 15)
print(birthday.day)    # 15
print(birthday.month)  # 7
print(birthday.year)   # 1959
```

---

## 🚦 The __name__ == "__main__" Idiom

Python scripts often include this conditional:

```python
if __name__ == "__main__":
    # Code
```

What Does It Mean?
- __name__ is a special built-in variable
- If a Python file is run directly, __name__ is set to "__main__"
- If the file is imported as a module, __name__ is set to the module name

This allows a file to:
- Run code when executed directly
- Avoid running that code when imported into another script
