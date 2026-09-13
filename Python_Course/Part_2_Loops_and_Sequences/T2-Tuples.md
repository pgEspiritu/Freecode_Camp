# 📚 Tuples in Python

A **tuple** is an **ordered sequence of values** in Python. Tuples can contain mixed data types:

```python
developer = ('Alice', 34, 'Rust Developer')
```

---

## 🔹 Immutability

Unlike lists, tuples are immutable, meaning their elements cannot be changed after creation.

```python
programming_languages = ('Python', 'Java', 'C++', 'Rust')
programming_languages[0] = 'JavaScript'

"""
TypeError: 'tuple' object does not support item assignment
"""
```

---

## 🔹 Accessing Elements

You can access elements using indexing:

```python
developer = ('Alice', 34, 'Rust Developer')
developer[1]  # 34
```

Negative indexing allows you to start from the end of the tuple:

```python
numbers = (1, 2, 3, 4, 5)
numbers[-2]  # 4
```

Passing an invalid index raises an `IndexError`:

```python
numbers[7]

"""
IndexError: tuple index out of range
"""
```

---

## 🔹 Creating Tuples

You can also use the tuple() constructor to convert iterables into a tuple:

```python
developer = 'Jessica'
tuple(developer)  # ('J', 'e', 's', 's', 'i', 'c', 'a')
```

---

## 🔹 Membership Testing

Check if an element is in a tuple using `**in**`:

```python
programming_languages = ('Python', 'Java', 'C++', 'Rust')

'Rust' in programming_languages       # True
'JavaScript' in programming_languages # False
```

---

## 🔹 Unpacking Tuples

You can unpack tuple values into variables:

```python
developer = ('Alice', 34, 'Rust Developer')
name, age, job = developer

print(name)  # 'Alice'
print(age)   # 34
print(job)   # 'Rust Developer'
```

Collect remaining elements with **`*`**:

```python
developer = ('Alice', 34, 'Rust Developer')
name, *rest = developer

print(name)  # 'Alice'
print(rest)  # [34, 'Rust Developer']
```
> Note: The **rest** variable is returned as a list, even when unpacking a tuple.

---

## 🔹 Slicing Tuples

Like lists, you can use the slice operator : to extract portions:

```python
desserts = ('cake', 'pie', 'cookies', 'ice cream')
desserts[1:3]  # ('pie', 'cookies')
```
- First number: starting index
- Second number: ending index (not included)

---

## 🔹 Deletion

Tuples are immutable, so items cannot be removed:

```python
developer = ('Jane Doe', 23, 'Python Developer')
del developer[1]

"""
TypeError: 'tuple' object doesn't support item deletion
"""
```

---

## 🔹 When to Use Tuples

- Use a list if you need a dynamic, mutable collection.
- Use a tuple if you need a fixed, immutable collection.

---

## ✅ Key Points

- Tuples are ordered and immutable.
- Access elements with indexing or slicing.
- Use unpacking to assign elements to variables.
- Tuples cannot be modified or deleted.
- Ideal for fixed collections of data.

---

# 📚 Common Methods for Tuples

In the previous lesson, you learned how to work with the tuple data type. In this lesson, we'll explore **common methods and functions** used with tuples.

---

## 🔹 `count()` Method

The `count()` method returns **how many times an item appears** in a tuple:

```python
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust')
programming_languages.count('Rust')  # 2
```

If the item is not present, it returns `0`:

```python
programming_languages.count('JavaScript')  # 0
```

Passing no arguments raises a `TypeError`:

```python
programming_languages.count()

"""
TypeError: tuple.count() takes exactly one argument (0 given)
"""
```

---

## 🔹 index() Method

The index() method returns the index of the first occurrence of an item:

```python
programming_languages.index('Java')  # 1
```

If the item is not found, Python raises a `ValueError`:

```python
programming_languages.index('JavaScript')

"""
ValueError: tuple.index(x): x not in tuple
"""
```

---

## Optional start and stop Arguments

You can specify a starting index for the search:

```python
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust', 'Python')
programming_languages.index('Python', 3)  # 5
```

You can also specify start and stop indices:

```python
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust', 'Python', 'JavaScript', 'Python')
programming_languages.index('Python', 2, 5)  # 2
```
> Note: The stop index is exclusive.

---

## 🔹 sorted() Function

The `sorted()` function can be used with any iterable, including tuples. It returns a new list of sorted elements:

```python
numbers = (13, 2, 78, 3, 45, 67, 18, 7)
sorted(numbers)  # [2, 3, 7, 13, 18, 45, 67, 78]
```
> Unlike `list.sort()`, `sorted()` **does not modify the original tuple.**

---

## Sorting with key and reverse Arguments

Sort by length of elements:

```python
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust', 'Python')
sorted(programming_languages, key=len)

# Result:
# ['C++', 'Rust', 'Java', 'Rust', 'Python', 'Python']
```

Sort in reverse order:

```python
sorted(programming_languages, reverse=True)

# Result:
# ['Rust', 'Rust', 'Python', 'Python', 'Java', 'C++']
```

---

## ✅ Key Points

- count() → Number of times an element appears in a tuple.
- index() → First index of an element; optional start and stop parameters can control search.
- sorted() → Returns a new list with sorted elements; supports key and reverse arguments.
- Tuples are immutable, so these methods do not modify the original tuple.
