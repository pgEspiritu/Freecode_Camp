# 🧩 Build a Hash Table

In this lab, you will build a **hash table** from scratch. A hash table is a data structure that stores **key-value pairs**. It works by taking a key as input and transforming it using a specific **hashing function**.

For this lab, the hashing function will be simple: it will **sum the Unicode values** of each character in the key. The resulting hash value will be used as the actual key to store the associated value. The same hash value will also be used to retrieve and delete the value associated with the key.

---

## 🎯 Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## 📌 User Stories

### 1️⃣ HashTable Class

You should define a class named **`HashTable`** with a `collection` attribute initialized to an empty dictionary when a new instance is created.

The `collection` dictionary should store key-value pairs based on the **hashed value** of the key.

---

### 2️⃣ Required Instance Methods

The `HashTable` class should have four instance methods:

- `hash`
- `add`
- `remove`
- `lookup`

---

## 🔑 Method Specifications

### 🧮 `hash` Method

The `hash` method should:

- Take a **string** as a parameter.
- Return a hashed value computed as the **sum of the Unicode (ASCII) values** of each character in the string.
- Use the built-in `ord()` function for computation.

---

### ➕ `add` Method

The `add` method should:

- Take two arguments representing a **key-value pair**.
- Compute the hash of the key.
- Use the computed hash value as a key in the `collection` dictionary.
- Store a dictionary containing the key-value pair inside the collection.

#### Collision Handling
If multiple keys produce the same hash value:
- Store their key-value pairs in the **existing nested dictionary** under the same hash value.

---

### ❌ `remove` Method

The `remove` method should:

- Take a key as its argument.
- Compute the hash of the key.
- Confirm whether the key exists in the collection.
- Remove the corresponding key-value pair from the hash table.

If the key does **not** exist:
- Do **not** raise an error.
- Do **not** remove anything.

---

### 🔍 `lookup` Method

The `lookup` method should:

- Take a key as its argument.
- Compute the hash of the key.
- Return the corresponding value stored in the hash table.

If the key does **not** exist:
- Return `None`.

---

✅ **Goal:** Implement all methods correctly so that all tests pass.


# Code

```python
class HashTable:
    # ---------------------------------------------------------
    # Constructor
    # Initializes an empty dictionary called 'collection'
    # This will store hashed keys and their key-value pairs.
    # ---------------------------------------------------------
    def __init__(self):
        self.collection = {}

    # ---------------------------------------------------------
    # hash()
    # Converts a string key into a numeric hash value.
    # The hash is computed by summing Unicode values
    # of each character using ord().
    #
    # Example:
    # "abc" -> ord('a') + ord('b') + ord('c')
    # ---------------------------------------------------------
    def hash(self, key: str) -> int:
        return sum(ord(char) for char in key)

    # ---------------------------------------------------------
    # add()
    # Adds a key-value pair into the hash table.
    #
    # Steps:
    # 1. Compute hash value of the key.
    # 2. If hash does not exist, create a new dictionary.
    # 3. Store the key-value pair inside the nested dictionary.
    #
    # Handles collisions by storing multiple keys
    # under the same hash value.
    # ---------------------------------------------------------
    def add(self, key, value):
        hashed_value = self.hash(key)

        # Create bucket if hash not yet present
        if hashed_value not in self.collection:
            self.collection[hashed_value] = {key: value}

        # Add/update key-value pair
        self.collection[hashed_value][key] = value

    # ---------------------------------------------------------
    # remove()
    # Removes a key-value pair from the hash table.
    #
    # Steps:
    # 1. Compute hash value.
    # 2. Check if hash bucket exists.
    # 3. Remove the key if present.
    # 4. Remove empty bucket after deletion.
    #
    # No error is raised if key does not exist.
    # ---------------------------------------------------------
    def remove(self, key):
        hashed_value = self.hash(key)

        if hashed_value in self.collection:
            if key in self.collection[hashed_value]:
                # Delete specific key
                del self.collection[hashed_value][key]

            # Remove bucket if empty
            if not self.collection[hashed_value]:
                del self.collection[hashed_value]

    # ---------------------------------------------------------
    # lookup()
    # Retrieves the value associated with a key.
    #
    # Steps:
    # 1. Compute hash value.
    # 2. Check bucket existence.
    # 3. Return stored value if key exists.
    #
    # Returns None if key is not found.
    # ---------------------------------------------------------
    def lookup(self, key):
        hashed_value = self.hash(key)

        if hashed_value in self.collection:
            if key in self.collection[hashed_value]:
                return self.collection[hashed_value][key]

        return None
```
