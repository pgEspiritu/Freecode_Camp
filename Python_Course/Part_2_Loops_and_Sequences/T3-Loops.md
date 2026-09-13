# 🔁 How Do Loops Work in Python?

As you learned in earlier modules, **loops** are used to repeat a block of code a set number of times. In this lesson, you’ll learn how to work with different types of loops in Python.

---

## 🔹 The `for` Loop

The `for` loop is commonly used to iterate over an **iterable** such as a list or string.

### Example: Iterating Through a List

```python
programming_languages = ['Rust', 'Java', 'Python', 'C++']

for language in programming_languages:
    print(language)
```

Output
```sql
Rust
Java
Python
C++
```
Notice that `**print(language)**` is indented. Python uses indentation to define code blocks. Without proper indentation, you will get an error.

Indentation Error Example
```python
"""
Traceback (most recent call last):
  File "<stdin>", line 4, in <module>
IndentationError: expected an indented block after 'for' statement on line 3
"""
```

---

## 🔹 Looping Through a String

You can also loop through a string, which is an iterable:
```python
for char in 'code':
    print(char)
```

Output:
```text
c
o
d
e
```

---

## 🔹 Nested for Loops

Python allows you to nest loops inside one another.

```python
categories = ['Fruit', 'Vegetable']
foods = ['Apple', 'Carrot', 'Banana']

for category in categories:
    for food in foods:
        print(category, food)
```

Output:

```text
Fruit Apple
Fruit Carrot
Fruit Banana
Vegetable Apple
Vegetable Carrot
Vegetable Banana
```
The outer loop runs first, and for each iteration, the inner loop runs completely.

---

## 🔹 The while Loop

The while loop repeats a block of code as long as a condition is True.

Example: Guessing Game

```python
secret_number = 3
guess = 0

while guess != secret_number:
    guess = int(input('Guess the number (1-5): '))
    if guess != secret_number:
        print('Wrong! Try again.')

print('You got it!')
```
In this example:
- The loop continues until the user guesses the correct number.
- input() gets user input as a string.
- int() converts the string to an integer.


Sample Output:
```python
Guess the number (1-5): 2
Wrong! Try again.
Guess the number (1-5): 1
Wrong! Try again.
Guess the number (1-5): 3
You got it!
```

---

## 🔹 break Statement

The break statement stops the loop immediately.

```python
developer_names = ['Jess', 'Naomi', 'Tom']

for developer in developer_names:
    if developer == 'Naomi':
        break
    print(developer)
```

Output:

```text
Jess
```
> Once Naomi is encountered, the loop exits.

---

## 🔹 continue Statement

The continue statement skips the current iteration and moves to the next one.

```python
developer_names = ['Jess', 'Naomi', 'Tom']

for developer in developer_names:
    if developer == 'Naomi':
        continue
    print(developer)
```

Output:

```text
Jess
Tom
```
> The loop skips printing Naomi but continues running.

---

## 🔹 else Clause in Loops

Both for and while loops can have an else clause.
The else block runs only if the loop completes without hitting a break.

Example: Checking for Vowels

```python
words = ['sky', 'apple', 'rhythm', 'fly', 'orange']

for word in words:
    for letter in word:
        if letter.lower() in 'aeiou':
            print(f"'{word}' contains the vowel '{letter}'")
            break
    else:
        print(f"'{word}' has no vowels")
```

Output:

```text
'sky' has no vowels
'apple' contains the vowel 'a'
'rhythm' has no vowels
'fly' has no vowels
'orange' contains the vowel 'o'
```

In this example:
- The inner else runs only if no vowel is found.
- If break is triggered, the else block is skipped.

---

## ✅ Key Takeaways

- for loops iterate over iterables like lists and strings.
- while loops run as long as a condition is True.
- break exits a loop immediately.
- continue skips the current iteration.
- Loops can include an else clause that runs only if no break occurs.
