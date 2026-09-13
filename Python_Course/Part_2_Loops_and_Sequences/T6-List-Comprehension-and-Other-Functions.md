# 📋 What Are List Comprehensions and Useful Functions to Work With Lists?

In previous lessons, you learned how to create lists using loops. Here’s a common example of building a list of even numbers using a `for` loop:

```python
even_numbers = []

for num in range(21):
    if num % 2 == 0:
        even_numbers.append(num)

print(even_numbers)
```
This code loops through numbers from 0 to 20 and appends only the even numbers to the even_numbers list.

---

## ⚡ List Comprehensions

List comprehensions provide a more concise way to create lists. They combine a loop and condition into a single line inside square brackets [].

###🔹 Example: Even Numbers Using List Comprehension

```python
even_numbers = [num for num in range(21) if num % 2 == 0]
print(even_numbers)
```

✅ Output:

```text
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

---

### 🔹 Example: Using Conditional Expressions in List Comprehension

```python
numbers = [1, 2, 3, 4, 5]
result = [(num, 'Even') if num % 2 == 0 else (num, 'Odd') for num in numbers]
print(result)
```

✅ Output:

```text
[(1, 'Odd'), (2, 'Even'), (3, 'Odd'), (4, 'Even'), (5, 'Odd')]
```
Here, we create a list of tuples indicating whether each number is even or odd.

---

### 🛠 Useful Functions for Lists

Python provides several built-in functions that work well with lists.

### 1️⃣ filter()

The filter() function selects elements from a list that meet a specific condition.
```python
words = ['tree', 'sky', 'mountain', 'river', 'cloud', 'sun']

def is_long_word(word):
    return len(word) > 4

long_words = list(filter(is_long_word, words))
print(long_words)
```

✅ Output:

```text
['mountain', 'river', 'cloud']
```
- Accepts a function and an iterable
- Returns only the items for which the function returns True

---

### 2️⃣ map()

The map() function applies a function to each element in a list.

```python
celsius = [0, 10, 20, 30, 40]

def to_fahrenheit(temp):
    return (temp * 9/5) + 32

fahrenheit = list(map(to_fahrenheit, celsius))
print(fahrenheit)
```

✅ Output:

```text
[32.0, 50.0, 68.0, 86.0, 104.0]
```
- Useful for transforming all elements in a list

---

### 3️⃣ sum()

The sum() function calculates the sum of all elements in a list or iterable.

```python
numbers = [5, 10, 15, 20]
total = sum(numbers)
print(total)
```

✅ Output:

```text
50
```

You can also use the optional `start` argument:

```python
total = sum(numbers, start=10)  # or sum(numbers, start=10)
print(total)  # 60
```

---

## 🧠 Summary

- List comprehensions allow you to create lists in a single line.
- filter() selects items from a list based on a condition.
- map() applies a function to every element in a list.
- sum() calculates the total of a list’s elements.
- Using these tools together makes Python code more concise and readable.
