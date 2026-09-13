# 🗂️ Maps, Hash Maps, and Sets

In computer science, **maps, hash maps, and sets** are powerful data structures used for **organizing and retrieving data efficiently**.

Before understanding them, it's important to know the concept of **Abstract Data Types (ADT)**.

---

# 🧠 Abstract Data Types (ADT)

An **Abstract Data Type (ADT)** is a **conceptual model** that defines:

- What **data** is stored
- What **operations** can be performed on that data

ADTs describe **what operations are possible**, but **not how they are implemented**.

📌 Think of them as **blueprints**.

Example operations of an ADT:
- Insert data
- Retrieve data
- Update data
- Delete data

The **implementation details** are handled by specific data structures.

---

# 🗺️ Maps

A **Map** is an **Abstract Data Type** that stores data as **key-value pairs**.

Example:
```python
Key → Value
"A" → 1
"B" → 2
"C" → 3
```

---

## 🔑 Key Characteristics of Maps

- Each **key must be unique**
- **Values can repeat**
- Data is accessed using **keys**

---

## ⚙️ Common Map Operations

| Operation | Description |
|--------|-------------|
| Insert | Add a key-value pair |
| Retrieve | Get value by key |
| Update | Change value of a key |
| Delete | Remove key-value pair |
| Search | Check if key exists |

Maps define these operations but **do not specify how they are implemented**.

---

# ⚡ Hash Maps (Hash Tables)

A **Hash Map** is a **concrete implementation** of the Map ADT.

It uses a technique called **hashing** to store and retrieve data efficiently.

---

## 🔢 How Hashing Works

1️⃣ A **hash function** takes a key  
2️⃣ The function generates a **hash value**  
3️⃣ That value determines an **index in an array**

Example concept:
```python
Key: "A"
Hash Function → 3
Store at index 3
```

---

## ⚠️ Hash Collisions

A **collision** occurs when two keys produce the **same index**.

Example:
```python
hash("A") → 3
hash("B") → 3
```

---

## 🔧 Collision Resolution Strategies

### 1️⃣ Chaining

Each index stores a **linked list** of elements.
```python
Index 3 → [A → B → C]
```

---

### 2️⃣ Open Addressing

If an index is occupied:

➡ The algorithm searches for the **next available slot**.

---

## ⏱️ Hash Map Complexity

| Operation | Average Case | Worst Case |
|----------|--------------|-----------|
| Insert | O(1) | O(n) |
| Retrieve | O(1) | O(n) |
| Delete | O(1) | O(n) |

Worst-case happens when **many collisions occur**.

---

# 🐍 Python Dictionaries (Hash Maps)

Python **dictionaries** are implemented using **hash maps**.

---

## Creating a Dictionary

```python
my_dictionary = {
  'A': 1,
  'B': 2,
  'C': 3
}
```

Or using dict():
```python
my_dictionary = dict(A=1, B=2, C=3)
```

Access Values
```python
my_dictionary['A']  # 1
```

Update Values
```python
my_dictionary['A'] = 4
```

Delete Elements
```python
del my_dictionary['A']
```

Check if Key Exists
```python
'C' in my_dictionary
```

Dictionary Methods
```python
my_dictionary.keys()
my_dictionary.values()
my_dictionary.items()
```

---

# 🔢 Sets

A Set is an unordered collection of unique elements.

## 🔑 Key Characteristics

- Elements are unique
- No duplicate values
- Elements are unordered
- Cannot access elements by index
Example:
```python
{1, 2, 3, 4}
```

## 📌 Why Sets Are Useful

Sets are often used for:
- Removing duplicates
- Fast membership checks
- Mathematical set operations

---

## 🐍 Python Sets
Create a Set
```python
numbers = {1, 2, 3, 4}
```

Create an Empty Set
```python
numbers = set()
```
⚠️ {} creates a dictionary, not a set.

Add Elements
```python
numbers.add(5)
```

Remove Elements
```python
numbers.remove(5)
```

If element might not exist:
```python
numbers.discard(5)
```

---

**Other Set Methods**
```python
numbers.pop()
numbers.clear()
```

Membership Testing
```python
5 in numbers
```

---

### 🧮 Set Operations

Example sets:
```python
set_a = {1,2,3,4}
set_b = {2,3,4,5,6}
```

Union
```python
set_a.union(set_b)
set_a | set_b
```

Intersection
```python
set_a.intersection(set_b)
set_a & set_b
```

Difference
```python
set_a.difference(set_b)
set_a - set_b
```

Symmetric Difference
```python
set_a.symmetric_difference(set_b)
set_a ^ set_b
```

---

### ⏱️ Set Complexity

| Operation  | Average | Worst |
| ---------- | ------- | ----- |
| Add        | O(1)    | O(n)  |
| Remove     | O(1)    | O(n)  |
| Membership | O(1)    | O(n)  |

> Worst case happens due to hash collisions.

---

### 🔍 Subset and Superset

```python
set_a.issubset(set_b)
set_a.issuperset(set_b)
```

### ⚠️ Immutable Elements Only

Sets can only contain immutable objects:

Allowed:
- integers
- strings
- tuples

Not allowed:
- lists
- dictionaries
- other mutable objects

Reason:
Mutable objects can change their hash value, making them impossible to locate in the hash table.

---

### ⚖️ Maps vs Sets

| Feature | Map (Dictionary) | Set                 |
| ------- | ---------------- | ------------------- |
| Stores  | Key-value pairs  | Unique values       |
| Keys    | Unique           | Elements themselves |
| Values  | Can repeat       | No duplicates       |
| Order   | Unordered        | Unordered           |

---

### 🎯 Key Takeaways

✅ Maps
- Store key-value pairs
- Keys must be unique

✅ Hash Maps
- Efficient implementation of maps
- Use hashing for fast operations

✅ Sets
- Store unique values
- Great for removing duplicates and membership checks
