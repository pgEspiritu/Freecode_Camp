# Python Data Structures and Modules Quiz

---

### 1. What is a dictionary?
- A data structure that is a collection of key-value pairs. ✅
- A data structure that only holds a collection of tuples.
- A data structure that is a collection of key-value pairs that only accept large numbers.
- A data structure that only holds strings and lists.

---

### 2. Which of the following is the correct syntax for a dictionary?

- dictionary = { key1: value1, key2: value2 } ✅
- dictionary = { <key1: value1>, <key2: value2> }
- dictionary = { [key1: value1], [key2: value2] }
- dictionary = { (key1: value1), (key2: value2) }

---

### 3. Which of the following is true about dictionaries?
- Keys must be unique. ✅
- Keys must include at least one number.
- Keys must include a special symbol.
- Keys must be at least two characters in length.

---

### 4. Which of the following constructors can be used to create a dictionary?
- dic()
- dict() ✅
- dictionary()
- diction()

---

### 5. Which of the following is the correct way to access a value from a dictionary?
- dictionary<key>
- dictionary/key/
- dictionary{key}
- dictionary[key] ✅

---

### 6. Which of the following is the correct way to update a value in a dictionary?
- pizza['name'] == 'Margherita'
- pizza['name'] = 'Margherita' ✅
- pizza['name'] >> 'Margherita'
- pizza['name'] << 'Margherita'

---

### 7. Which of the following methods can be used to retrieve a value associated with a key?
- retrieve()
- get() ✅
- access()
- set()

---

### 8. What is a view object?
- A way to view the content of a dictionary only if the dictionary has two or more key-value pairs.
- A way to see the content of a dictionary without creating a separate copy of the data. ✅
- A special object used to turn strings into dictionaries.
- A special object used to turn lists into dictionaries.

---

### 9. Which of the following methods returns a view object with all the key-value pairs in the dictionary?
- items() ✅
- lists()
- dictionaries()
- collections()

---

### 10. Which of the following methods removes all of the key-value pairs from the dictionary?
- remove()
- replace()
- clear() ✅
- empty()

---

### 11. What will be the output for the following code?
```python
products = {
    'Laptop': 990,
    'Smartphone': 600,
    'Tablet': 250,
    'Headphones': 70,
}
```

- ('Laptop', 990)
  ('Smartphone', 600)
  ('Tablet', 250)
  ('Headphones', 70) ✅
- 'Laptop', 990
  'Smartphone', 600
  'Tablet', 250
  'Headphones', 70
- <'Laptop', 990>
  <'Smartphone', 600>
  <'Tablet', 250>
  <'Headphones', 70>
- `['Laptop', 990]`
  `['Smartphone', 600]`
  `['Tablet', 250]`
  `['Headphones', 70]`

---

### 12. Which of the following is true about sets?
- Sets are immutable and unordered.
- Sets are mutable and ordered.
- Sets are mutable and unordered. ✅
- Sets are mutable and ordered in reverse.

---

### 13. Which of the following is the correct way to create a set?

- my_set = `[1, 2, 3, 4, 5]`
- my_set = {1, 2, 3, 4, 5} ✅
- my_set = (1, 2, 3, 4, 5)
- my_set = <1, 2, 3, 4, 5>

---

### 14. Which of the following functions is used to create an empty set?

- sets()
- create_set()
- empty_set()
- set() ✅

---

### 15. What will be output to the terminal?

```python
for product in products.items():
    print(product)
```

- {1, 2, 3, 4, 5, 6
- RangeError
- {1, 2, 3, 4, 5, 5, 6
- SyntaxError

---

### 16. Which of the following methods checks if a set is a subset?

- issubset() ✅
- subset()
- issub()
- isset()

---

### 17. Which of the following methods checks if two sets are disjoint?

- joint()
- disjoint()
- isdisjoint() ✅
- isjoint()

---

### 18. What does the symmetric difference operator (^) do?

- It returns a new set with the elements of the first set that are not in the other set.
- It finds the difference between the sets and updates the first set with that result.
- It returns a new set with only the elements that the sets have in common.
- It returns a new set with the elements that are either in the first or the second set, but not both. ✅

---

### 19. Which of the following built-in modules is used for generating random numbers?

- get_random
- set_random
- rand
- random ✅

---

### 20. Which of the following modules is used for working with regular expressions?

- r
- reg
- re ✅
- regex
