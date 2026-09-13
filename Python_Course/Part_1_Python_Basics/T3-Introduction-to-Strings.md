# 🔤 What Are Strings and What Is String Immutability?

A **string** is a sequence of characters surrounded by either single or double quotation marks. In some programming languages, characters surrounded by single quotes are treated differently than characters surrounded by double quotes, but in Python, they're treated equally. You can use either when working with strings.  

### Examples of Strings

```python
my_str_1 = 'Hello'
my_str_2 = "World"
```

### Multi-line Strings

You can use triple quotes (single or double) for multi-line strings:
```python
my_str_3 = """Multiline
string"""
my_str_4 = '''Another
multiline
string'''
```

---

### Handling Quotes Inside Strings

If your string contains single or double quotation marks, you have two options:

1. Use the opposite kind of quotes:
```python
msg = "It's a sunny day"
quote = 'She said, "Hello World!"'
```

2. Escape the quotes with a backslash (\):
```python
msg = 'It\'s a sunny day'
quote = "She said, \"Hello!\""
```

### Checking if a Character or Substring Exists

Python provides the in operator, which returns a boolean indicating whether a character or substring exists in the string:

```python
my_str = 'Hello world'

print('Hello' in my_str)  # True
print('hey' in my_str)    # False
print('hi' in my_str)     # False
print('e' in my_str)      # True
print('f' in my_str)      # False
```

---

### String Length and Indexing

You can get the length of a string with the built-in len() function:
```python
my_str = 'Hello world'
print(len(my_str))  # 11
```

Each character in a string has a zero-based index:
```python
my_str = "Hello world"

print(my_str[0])  # H
print(my_str[6])  # w
```

Python also supports negative indexing, where -1 is the last character, -2 is the second-to-last, and so on:
```python
my_str = 'Hello world'
print(my_str[-1])  # d
print(my_str[-2])  # l
```

---

## String Immutability

In Python, strings are immutable, which means once a string is created, it cannot be modified. You can reassign a variable to a new string, but you cannot change the original string:

```python
# Reassignment is allowed
greeting = 'hi'
greeting = 'hello'
print(greeting)  # hello

# Direct modification is NOT allowed
greeting = 'hi'
greeting[0] = 'H'  # TypeError: 'str' object does not support item assignment
```

---

# 🔗 What Are String Concatenation and String Interpolation?

When working with strings, combining different pieces of text together is a common operation you'll often encounter.

---

## ➕ String Concatenation

In Python, you can combine multiple strings together using the **plus (`+`) operator**. This process is called **string concatenation**.

```python
my_str_1 = 'Hello'
my_str_2 = "World"

str_plus_str = my_str_1 + ' ' + my_str_2
print(str_plus_str)  # Hello World
```

> ⚠️ Note: This only works with strings. If you try to concatenate a string with a number, you'll get a TypeError:

```python
name = 'John Doe'
age = 26

name_and_age = name + age
print(name_and_age)  # TypeError: can only concatenate str (not "int") to str
```

Python does not automatically convert other data types like integers into strings when concatenating. To fix this, use the str() function:

```python
name = 'John Doe'
age = 26

name_and_age = name + str(age)
print(name_and_age)  # John Doe26
```

You can also use the augmented assignment operator (+=) for concatenation and assignment in one step:

```python
name = 'John Doe'
age = 26

name_and_age = name  # Start with the name
name_and_age += str(age)  # Append the age as string

print(name_and_age)  # John Doe26
```

---

## 🖋️ String Interpolation (f-Strings)

String interpolation is the process of inserting variables and expressions into a string. Python provides f-strings (formatted string literals) for this purpose.
- F-strings start with f (or F) before the quotes.
- Variables or expressions are embedded inside curly braces {}.

```python
name = 'John Doe'
age = 26
name_and_age = f'My name is {name} and I am {age} years old'
print(name_and_age)  # My name is John Doe and I am 26 years old
```

You can also perform calculations directly inside f-strings:

```python
num1 = 5
num2 = 10
print(f'The sum of {num1} and {num2} is {num1 + num2}')  # The sum of 5 and 10 is 15
```
> ✅ Notice: You don't need to convert non-string types with str(). Python automatically converts them to strings during interpolation.

---

## 🧩 Basic String Slicing

String slicing lets you extract a portion of a string or work with only a specific part of it.

Syntax:
```python
string[start:stop]
```

Example:
```python
my_str = 'Hello world'
print(my_str[1:4])  # ell
```
> ⚠️ Note: The stop index is non-inclusive, so [1:4] extracts characters from index 1 up to, but not including, index 4.

---

## ⏩ Omitting Start or Stop Indices

- Omit start index → defaults to 0:
```python
my_str = 'Hello world'
print(my_str[:7])  # Hello w
```

- Omit stop index → defaults to end of string:
```python
my_str = 'Hello world'
print(my_str[8:])  # rld
```
> Slicing does not modify the original string:

```python
my_str = 'Hello world'
print(my_str[8:])  # rld
print(my_str)      # Hello world
```

- Omit both start and stop indices → extracts the whole string:
```python
my_str = 'Hello world'
print(my_str[:])  # Hello world
```

---

## 🔢 Using the Step Parameter

You can specify an optional step parameter to control the increment between each index:
```python
string[start:stop:step]
```

Example:
```python
my_str = 'Hello world'
print(my_str[0:11:2])  # Hlowrd
```

- Step can also be used to reverse a string:
```python
my_str = 'Hello world'
print(my_str[::-1])  # dlrow olleH
```

---

# 🛠️ What Are Some Common String Methods?

Python provides a number of built-in **string methods** that make working with strings easier. Some of the most common methods include:

---

## 🔠 upper()
Returns a new string with all characters converted to **uppercase**.

```python
my_str = 'hello world'

uppercase_my_str = my_str.upper()
print(uppercase_my_str)  # HELLO WORLD
```

---

## 🔡 lower()

Returns a new string with all characters converted to lowercase.
```python
my_str = 'Hello World'

lowercase_my_str = my_str.lower()
print(lowercase_my_str)  # hello world
```

---

## ✂️ strip()

Removes leading and trailing characters. By default, removes whitespace.
```python
my_str = '  hello world  '

trimmed_my_str = my_str.strip()
print(trimmed_my_str)  # "hello world"
```

---

## 🔄 replace(old, new)

Returns a new string with all occurrences of old replaced by new.
```python
my_str = 'hello world'

replaced_my_str = my_str.replace('hello', 'hi')
print(replaced_my_str)  # hi world
```

---

## 🔗 split(separator)

Splits a string into a list using a separator. Defaults to whitespace if no separator is provided.
```python
my_str = 'hello world'

split_words = my_str.split()
print(split_words)  # ['hello', 'world']
```

---

## 🧩 join(iterable)

Joins elements of an iterable into a string with a separator.
```python
my_list = ['hello', 'world']

joined_my_str = ' '.join(my_list)
print(joined_my_str)  # hello world
```

---

## ✅ startswith(prefix)

Returns True if a string starts with the specified prefix, False otherwise.
```python
my_str = 'hello world'

starts_with_hello = my_str.startswith('hello')
print(starts_with_hello)  # True
```

---

## ✅ endswith(suffix)

Returns True if a string ends with the specified suffix, False otherwise.
```python
my_str = 'hello world'

ends_with_world = my_str.endswith('world')
print(ends_with_world)  # True
```

---

## 🔍 find(substring)

Returns the index of the first occurrence of the substring, or -1 if not found.
```python
my_str = 'hello world'

world_index = my_str.find('world')
print(world_index)  # 6
```

---

## 🔢 count(substring)

Returns the number of times a substring appears in a string.
```python
my_str = 'hello world'

o_count = my_str.count('o')
print(o_count)  # 2
```

---

## 🅰️ capitalize()

Returns a new string with the first character capitalized and the rest in lowercase.
```python
my_str = 'hello world'

capitalized_my_str = my_str.capitalize()
print(capitalized_my_str)  # Hello world
```

---

## 🔠 isupper()

Returns True if all letters in the string are uppercase, False otherwise.
```python
my_str = 'hello world'

is_all_upper = my_str.isupper()
print(is_all_upper)  # False
```

---

## 🔡 islower()

Returns True if all letters in the string are lowercase, False otherwise.
```python
my_str = 'hello world'

is_all_lower = my_str.islower()
print(is_all_lower)  # True
```

---

## 📝 title()

Returns a new string with the first letter of each word capitalized.
```python
my_str = 'hello world'

title_case_my_str = my_str.title()
print(title_case_my_str)  # Hello World
```

