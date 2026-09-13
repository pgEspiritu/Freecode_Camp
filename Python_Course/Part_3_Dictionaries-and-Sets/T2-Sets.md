# 📦 What Are Sets, and How Do They Work?

Sets are one of Python's built-in data structures. One of their core characteristics is that they **do not store duplicate values**. If you try to add a duplicate value to a set, only one instance of that value will be kept.

Sets are **mutable** and **unordered**, which means:
- Elements are not stored in a specific order
- You cannot access elements using indices or keys

Sets can only contain **immutable data types** such as numbers, strings, and tuples. They also support common **mathematical set operations**, including:
- Union
- Intersection
- Difference
- Symmetric difference

---

## Defining a Set

You define a set using curly braces `{}` and separate elements with commas:

```python
my_set = {1, 2, 3, 4, 5}
```

---

## Empty Set Gotcha ⚠️

To define an empty set, you must use the set() function. Using {} creates a dictionary instead.

```python
set()  # Set
{}     # Dictionary
```

---

## Adding Elements

Use the .add() method to add an element to a set:

```python
my_set.add(6)
```

my_set.add(6)

```text
{1, 2, 3, 4, 5, 6}
```

Adding a duplicate value has no effect:

```python
my_set.add(5)
```
The set remains unchanged.

---

## Removing Elements

You can remove elements using .remove() or .discard():
```python
my_set.remove(4)
my_set.discard(4)
```
- .remove() raises a KeyError if the element does not exist
- .discard() does not raise an error

---

## Clear All Elements

```python
my_set.clear()
```

---

## Subset and Superset Checks

```python
my_set = {1, 2, 3, 4, 5}
your_set = {2, 3, 4, 6}

print(your_set.issubset(my_set))   # False
print(my_set.issuperset(your_set)) # False
```

---

## Disjoint Sets

The .isdisjoint() method checks if two sets have no elements in common:

```python
print(my_set.isdisjoint(your_set))  # False
```

---

## Set Operations

### Union (|)
All unique elements from both sets:

```python
my_set | your_set
```

```text
{1, 2, 3, 4, 5, 6}
```

### Intersection (&)

Only elements common to both sets:

```python
my_set & your_set
```

```text
{2, 3, 4}
```

### Difference (-)

Elements in the first set but not in the second:

```python
my_set - your_set
```

```text
{1, 5}
```

### Symmetric Difference (^)

Elements in either set, but not both:

```python
my_set ^ your_set
```

```text
{1, 5, 6}
```

---

## Compound Assignment Operators

Each set operation has a compound version:

```python
|=  &=  -=  ^=
```

Example:
```text
my_set -= your_set
print(my_set)
```

---

## Membership Test

Use the in operator to check if an element exists in a set:
```python
print(5 in my_set)
```
Returns a boolean value (True or False).

---

## ✅ Summary

- Sets store unique values only
- They are unordered and mutable
- Ideal for membership testing and mathematical operations
- Very useful when order does not matter
