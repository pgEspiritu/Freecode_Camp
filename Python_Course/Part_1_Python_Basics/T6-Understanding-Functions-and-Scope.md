# 🛠 How Do Functions Work in Python?

Functions are **reusable pieces of code** that run when you call them. Many programming languages come with built-in functions, and Python is no exception.  

We've already covered some built-in functions like `print()` in previous lessons.

---

## 🔹 Built-in Functions Example

### `input()` Function
Prompts the user for input:

```python
name = input('What is your name?')  # User types "Kolade" and presses Enter
print('Hello', name)                 # Output: Hello Kolade
```

### `int()` Function
Converts numbers, booleans, or numeric strings into an integer:

```python
print(int(3.14))    # 3
print(int('42'))    # 42
print(int(True))    # 1
print(int(False))   # 0
```

---

## 🔹 Creating Your Own Functions

Use the def keyword followed by:
- Function name
- Parentheses () (for parameters)
- Colon :
- Indented code block (the function body)

---

Example: Simple Function
```python
def hello():
    print('Hello World')

hello()  # Hello World
```
> Notice the indentation before print(). Python relies on indentation to define code blocks.

Example: Function with Parameters
```python
def calculate_sum(a, b):
    print(a + b)

calculate_sum(3, 1)  # 4
```
- a and b are parameters (placeholders).
- When calling the function, you pass arguments (actual values).
```python
calculate_sum()  
# TypeError: calculate_sum() missing 2 required positional arguments: 'a' and 'b'
```

---

## 🔹 Using return in Functions

Without `return`, a function returns None by default:
```python
def calculate_sum(a, b):
    print(a + b)

my_sum = calculate_sum(3, 1)  # 4
print(my_sum)                 # None
```

Using `return` to get a value back:
```python
def calculate_sum(a, b):
    return a + b

my_sum = calculate_sum(3, 1)
print(my_sum)  # 4
```
> Now the sum is returned and stored in my_sum.

---

# 🌐 What Is Scope in Python and How Does It Work?

In Python, **scope** determines where you can access a variable. It controls the **lifetime** of a variable and how it is resolved in different parts of the code.

Python uses the **LEGB rule** to determine scope:

- **L**ocal scope: Variables defined in functions or classes.  
- **E**nclosing scope: Variables in enclosing or nested functions.  
- **G**lobal scope: Variables defined at the top level of the module or file.  
- **B**uilt-in scope: Reserved names in Python for predefined functions, modules, keywords, and objects.

---

## 🔹 Local Scope

Variables declared inside a function or class can only be accessed **within that function or class**.

```python
def my_func():
    my_var = 10
    print(my_var)

my_func()  # 10
print(my_var)  # NameError: name 'my_var' is not defined
```

---

## 🔹 Enclosing Scope

A nested function can access variables from its enclosing function, but outer functions cannot access variables of inner functions.
```python
def outer_func():
    msg = 'Hello there!'

    def inner_func():
        print(msg)

    inner_func()

outer_func()  # Hello there!
```

Variables defined in the inner function are not accessible in the outer function:
```python
def outer_func():
    msg = 'Hello there!'
    print(res)  # NameError

    def inner_func():
        res = 'How are you?'
        print(msg)

    inner_func()

outer_func()
```

You can fix this with nonlocal:
```python
def outer_func():
    msg = 'Hello there!'
    res = ""  # Declare res in enclosing scope

    def inner_func():
        nonlocal res  # Modify enclosing variable
        res = 'How are you?'
        print(msg)

    inner_func()
    print(res)  # Accessible and modified

outer_func()

# Output:
# Hello there!
# How are you?
```

---

## 🔹 Global Scope

Variables declared outside any function or class are accessible anywhere in the program:
```python
my_var = 100

def show_var():
    print(my_var)

show_var()  # 100
print(my_var)  # 100
```

You can also make a local variable `global` with the global keyword:
```python
my_var_1 = 7

def show_vars():
    global my_var_2
    my_var_2 = 10
    print(my_var_1)
    print(my_var_2)

show_vars()  # 7 10
print(my_var_2)  # 10
```

Or modify a global variable:
```python
my_var = 10  # Global

def change_var():
    global my_var
    my_var = 20

change_var()
print(my_var)  # 20
```

---

## 🔹 Built-in Scope

Python has a set of built-in functions, modules, and keywords available anywhere in your program:
```python
print(str(45))           # '45'
print(type(3.14))        # <class 'float'>
print(isinstance(3, str)) # False
```
