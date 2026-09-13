# 📋 What Are Lists and How Do They Work?

In Python, **lists** are an **ordered sequence** of elements that can include strings, numbers, or even other lists. Lists are **mutable** and use **zero-based indexing**, meaning the first element is at index `0`.

---

## 🔹 Creating Lists

```python
cities = ['Los Angeles', 'London', 'Tokyo']
```

Access elements using indices:

```python
cities[0]  # 'Los Angeles'
cities[-1] # 'Tokyo' (last element)
```

You can also create a list from an iterable using the `list()` constructor:

```python
developer = 'Jessica'
list(developer)  # ['J', 'e', 's', 's', 'i', 'c', 'a']
```

Get the length of a list with `len()`:

```python
numbers = [1, 2, 3, 4, 5]
len(numbers)  # 5
```

---

## 🔹 Updating and Deleting Elements

Lists are mutable, so you can update elements by index:

```python
programming_languages = ['Python', 'Java', 'C++', 'Rust']
programming_languages[0] = 'JavaScript'
print(programming_languages)  # ['JavaScript', 'Java', 'C++', 'Rust']
```

Accessing an out-of-bounds index raises an `IndexError`:

```python
programming_languages[10] = 'JavaScript'
# IndexError: list assignment index out of range
```

Remove elements with `del`:

```python
developer = ['Jane Doe', 23, 'Python Developer']
del developer[1]
print(developer)  # ['Jane Doe', 'Python Developer']
```

Check if an element exists with `in`:

```python
'Rust' in programming_languages       # True
'JavaScript' in programming_languages # False
```

---

## 🔹 Nested Lists

Lists can contain other lists:

```python
developer = ['Alice', 25, ['Python', 'Rust', 'C++']]
developer[2]     # ['Python', 'Rust', 'C++']
developer[2][1]  # 'Rust'
```

---

## 🔹 Unpacking Lists

Unpacking assigns list elements to variables:

```python
developer = ['Alice', 34, 'Rust Developer']
name, age, job = developer

print(name)  # 'Alice'
print(age)   # 34
print(job)   # 'Rust Developer'
```

Use `*` to collect remaining elements:

```python
developer = ['Alice', 34, 'Rust Developer']
name, *rest = developer

print(name)  # 'Alice'
print(rest)  # [34, 'Rust Developer']
```

Mismatched variables and list items raise a `ValueError`:

```python
name, age, job, city = developer
# ValueError: not enough values to unpack (expected 4, got 3)
```

---

## 🔹 List Slicing

Similar to strings, lists support slicing with ::

```python
desserts = ['Cake', 'Cookies', 'Ice Cream', 'Pie', 'Brownies']
desserts[1:4]  # ['Cookies', 'Ice Cream', 'Pie']
```

You can also use a step to skip elements:

```python
numbers = [1, 2, 3, 4, 5, 6]
numbers[1::2]  # [2, 4, 6]
```
Here, `1` is the start index, the end index is omitted, and `2` is the step interval.

---

## ✅ Key Points

- Lists are ordered, mutable, and zero-indexed.
- Use indices for accessing or updating elements.
- Lists can be nested and unpacked into variables.
- The slice operator allows extracting portions of a list.
- Lists are flexible and widely used in Python programs.

---

# 📚 Common Methods Used for Lists

In the previous lesson, you learned how to access elements and slice lists. In this lesson, we will explore **common methods** for Python lists like `append()`, `extend()`, `pop()`, `sort()`, and more.

---

## 🔹 append()

The `append()` method adds an item to the **end** of the list:

```python
numbers = [1, 2, 3, 4, 5]
numbers.append(6)
print(numbers)  # [1, 2, 3, 4, 5, 6]
```

Appending a list as a single element:

```python
numbers = [1, 2, 3, 4, 5]
even_numbers = [6, 8, 10]

numbers.append(even_numbers)
print(numbers)  # [1, 2, 3, 4, 5, [6, 8, 10]]
```

---

## 🔹 extend()

The extend() method adds all elements from another list:

```python
numbers = [1, 2, 3, 4, 5]
even_numbers = [6, 8, 10]

numbers.extend(even_numbers)
print(numbers)  # [1, 2, 3, 4, 5, 6, 8, 10]
```

---

## 🔹 insert()

Insert an element at a specific index:

```python
numbers = [1, 2, 3, 4, 5]
numbers.insert(2, 2.5)
print(numbers)  # [1, 2, 2.5, 3, 4, 5]
```

---

## 🔹 remove()

Remove an element by value. Only the first occurrence is removed:

```python
numbers = [10, 20, 30, 40, 50, 50]
numbers.remove(50)
print(numbers)  # [10, 20, 30, 40, 50]
```

---

## 🔹 pop()

Remove an element by index (returns the removed element):

```python
numbers = [1, 2, 3, 4, 5]
numbers.pop(1)  # Removes 2
numbers.pop()   # Removes last element, 5
```

---

## 🔹 clear()

Remove all elements from the list:

```python
numbers = [1, 2, 3, 4, 5]
numbers.clear()
print(numbers)  # []
```

---

## 🔹 sort() and sorted()

sort() sorts in place:

```python
numbers = [19, 2, 35, 1, 67, 41]
numbers.sort()
print(numbers)  # [1, 2, 19, 35, 41, 67]
```

sorted() returns a new sorted list without modifying the original:

```python
numbers = [19, 2, 35, 1, 67, 41]
sorted_numbers = sorted(numbers)

print(numbers)         # [19, 2, 35, 1, 67, 41]
print(sorted_numbers)  # [1, 2, 19, 35, 41, 67]
```
> Both sort() and sorted() accept optional key and reverse parameters (to be explored later).


---

## 🔹 reverse()

Reverse the order of elements in place:

```python
numbers = [6, 5, 4, 3, 2, 1]
numbers.reverse()
print(numbers)  # [1, 2, 3, 4, 5, 6]
```

---

## 🔹 index()

Find the first index of a value in a list:

```python
programming_languages = ['Rust', 'Java', 'Python', 'C++']
programming_languages.index('Java')  # 1
```

If the element is not found, Python raises a ValueError:

```python
programming_languages.index('JavaScript')
# ValueError: 'JavaScript' is not in list
```

---

## ✅ Key Points

- append() adds a single element at the end.
- extend() adds multiple elements from another iterable.
- insert() adds an element at a specific position.
- remove() and pop() delete elements by value or index.
- sort() and sorted() order elements in place or return a new list.
- reverse() flips the order of elements.
- index() finds the position of an element in a list.
