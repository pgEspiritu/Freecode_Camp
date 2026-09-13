# 📝 How Do You Declare Variables and What Are Naming Conventions to Name Variables?

In Python, variables are like a labelled box for storing and referencing data of different types. To declare variables in Python, you assign a value to an identifier with the assignment (`=`) operator. You don't need to use special keywords like `let` or `const` in JavaScript, or `char` in C#.

In Python, you just write the name of the variable on the left, followed by the assignment operator, and the value you want to assign on the right. Here's an example:

```python
name = 'John Doe'
age = 25
```

In the example above, the variable `name` holds the value `'John Doe'`. This value is a string, which is a series of characters used to represent text. Strings are written with single or double quotes, for example `'Hello'` or `"Hello"`. In future lessons, you'll learn more about working with strings in Python.

---

## ✅ Rules for Naming Variables

1. When naming variables in Python, there are some important rules you should keep in mind:
2. Variable names can only start with a letter or an underscore (`_`), not a number.
3. Variable names can only contain alphanumeric characters (`a-z`, `A-Z`, `0-9`) and underscores (`_`).
4. Variable names are case-sensitive — `age`, `Age`, and `AGE` are all considered unique.
5. Variable names cannot be one of Python's reserved keywords such as `if`, `class`, or `def`.

If you break any of these rules, your Python program will throw a SyntaxError:
```python
5variable_name = 5
# ^
# SyntaxError: invalid syntax
```

---

## 🐍 Common Naming Conventions in Python
- **Snake Case**: Variable names should be in lowercase, with separate words separated by an underscore:
```python
my_variable_name = 'freeCodeCamp'
```

- **Descriptive Names**: Use names that clearly communicate the purpose of the variable. For example:
```python
user_age = 30
```
This is better than simply `age` or abbreviations like `ua`.

- **Avoid Single-Letter Names**: Single-letter variables like x communicate no purpose or meaning:
```python
x = 56  # What do you mean by x?
```
> ⚠️ Exception: Single-letter variables like i, j, k are commonly used in loops.

---

## 💬 Comments in Python

In Python, comments start with a pound symbol (#). The language ignores everything after the # symbol on that line:
```python
# This is a single-line comment
```

Multi-line comments can be created by using consecutive single-line comments:
```python
# This is a
# multi-line
# comment
```
Comments are useful for explaining code, leaving reminders, or clarifying why a line exists.

> ⚠️ Best practice: Don't use comments to explain what variable names mean. Instead, choose descriptive variable names that communicate their purpose and follow the naming rules above.

---

# 🖨️ How Does the Print Function Work?

Every programming language has some way to output data to the terminal with a built-in method, function, property, or keyword. In Python, you can use the `print` function to print data to the terminal. Let's take a closer look at the `print` function so you can start using it with confidence.

---

## 👋 Hello World Example

One of the first things you do when learning any programming language is to write a simple **Hello world!** program. You can do that easily in Python with just the `print` function:

```python
print('Hello world!')  # Hello world!
```

You will learn more about strings and functions in Python in future lessons. For now, just consider strings as a sequence of characters surrounded by either single (`'`) or double (`"`) quotation marks.

In the `print('Hello world!')` example, the string `'Hello world!'` is an argument passed to the print function.

---

## 🖨️ Printing Multiple Values

You can also use the print function to show multiple values, or arguments, at once by separating them with commas. For example:
```python
print('My favorite colors are', 'blue', 'green', 'red')
```

Output:
```sql
My favorite colors are blue green red
```

Python automatically adds a space between each item when you separate them with commas. This is helpful when you want to print several pieces of information together.

---

# 📊 What Are Common Data Types in Python and How Do You Get the Type of a Variable?

Before working with Python variables, it's important to understand **data types**. A data type describes the kind of value a variable holds — for example, a number, a piece of text, or a list of items. Programming languages use data types so they know how to store and work with different kinds of information.

Python is a **dynamically-typed language** like JavaScript, meaning you don't need to explicitly declare types for variables. The language knows what data type a variable is based on what you assign to it.

```python
name = 'John Doe'  # Python knows this is a string
age = 25           # Python knows this is an integer
```

This is in contrast to some statically-typed languages like C#, Java, and C++, where you have to declare types explicitly:

```csharp
string name = 'John Doe';
int age = 25;
```

Dynamic typing in Python makes coding faster and more flexible, but type errors are only detected at runtime, not when the program compiles.

> In Python, type errors appear during execution when a program reaches the problematic line.
> In compiled languages, type errors are caught before the program runs.

---

## 🧮 Common Data Types in Python

Here are the most common data types you’ll use in Python:

1. Integer

A whole number without decimals:
```python
my_integer_var = 10
print('Integer:', my_integer_var)  # Integer: 10
```

2. Float

A number with a decimal point:
```python
my_float_var = 4.50
print('Float:', my_float_var)  # Float: 4.5
```

3. 3. String

A sequence of characters enclosed in single or double quotes:
```python
my_string_var = 'hello'
print('String:', my_string_var)  # String: hello
```

4. 4. Boolean

A true or false value:
```python
my_boolean_var = True
print('Boolean:', my_boolean_var)  # Boolean: True
```

5. Set

An unordered collection of unique elements:
```python
my_set_var = {7, 5, 8}
print('Set:', my_set_var)  # Set: {7, 5, 8}
```

6. Dictionary

A collection of key-value pairs:
```python
my_dictionary_var = {'name': 'Alice', 'age': 25}
print('Dictionary:', my_dictionary_var)  # Dictionary: {'name': 'Alice', 'age': 25}
```

7. Tuple

An immutable ordered collection:
```python
my_tuple_var = (7, 5, 8)
print('Tuple:', my_tuple_var)  # Tuple: (7, 5, 8)
```

8. Range

A sequence of numbers, often used in loops:
```python
my_range_var = range(5)
print('Range:', my_range_var)  # Range: range(0, 5)
```

9. List

An ordered collection that can contain different data types:
```python
my_list = [22, 'Hello world', 3.14, True]
print(my_list)  # [22, 'Hello world', 3.14, True]
```

10. None

A special value that represents the absence of a value:
```python
my_none_var = None
print('None:', my_none_var)  # None: None
```

---

🔍 Getting the Type of a Variable

To get the data type of a variable, use the built-in type() function:
```python
my_var_1 = 'Hello world'
my_var_2 = 21

print(type(my_var_1))  # <class 'str'>
print(type(my_var_2))  # <class 'int'>
```

Full example for all data types:
```python
my_integer_var = 10
print(type(my_integer_var))  # <class 'int'>

my_float_var = 4.50
print(type(my_float_var))  # <class 'float'>

my_string_var = 'hello'
print(type(my_string_var))  # <class 'str'>

my_boolean_var = True
print(type(my_boolean_var))  # <class 'bool'>

my_set_var = {7, 5, 8}
print(type(my_set_var))  # <class 'set'>

my_dictionary_var = {'name': 'Alice', 'age': 25}
print(type(my_dictionary_var))  # <class 'dict'>

my_tuple_var = (7, 5, 8)
print(type(my_tuple_var))  # <class 'tuple'>

my_range_var = range(5)
print(type(my_range_var))  # <class 'range'>

my_list = [22, 'Hello world', 3.14, True]
print(type(my_list))  # <class 'list'>

my_none_var = None
print(type(my_none_var))  # <class 'NoneType'>
```

## ✅ Checking a Variable Type with isinstance()

The isinstance() function checks if a variable matches a specific data type:
```python
isinstance('Hello world', str)  # True
isinstance(True, bool)          # True
isinstance(42, int)             # True
isinstance('John Doe', int)     # False
```
