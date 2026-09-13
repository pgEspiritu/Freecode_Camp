# 📦 Dynamic Arrays vs Static Arrays

Arrays are a **fundamental data structure** in computer science used to store **ordered collections of data**.

Although all arrays store elements in order, **static arrays** and **dynamic arrays** behave differently behind the scenes — and this affects **performance and efficiency**.

---

# 🧱 Static Arrays

## 🔹 What is a Static Array?

A **static array** has a **fixed size** that is determined when the array is created.

Once memory is allocated:
- ❌ The size **cannot change**
- ❌ Cannot grow or shrink during program execution

---

## 🧠 Memory Behavior

Static arrays store elements in **adjacent memory locations**.

This allows:
- Fast indexing
- Simple memory calculations
- Efficient data retrieval

---

## ⚡ Time Complexity

| Operation | Complexity |
|-----------|------------|
| Access element | **O(1)** (Constant Time) |

Access is very fast because the program calculates the memory address directly.

---

## ✅ When to Use Static Arrays

Use static arrays when:

- The number of elements is known beforehand
- Elements are accessed frequently
- Memory size does not need to change

---

## ❌ Limitations

- Cannot resize
- Increasing size requires:
  1. Creating a new array
  2. Copying all elements
  3. Deleting the old array

This process is inefficient.

---

## 💻 Example (Java Static Array)

```java
int[] numbers = new int[3];
```
> Python does not provide traditional static arrays as built-in structures.

---

## 🔄 Dynamic Arrays
🔹 What is a Dynamic Array?

A dynamic array automatically grows or shrinks while the program runs.

It uses an automatic resizing mechanism:
- When full → creates a larger array
- Copies elements into the new array
This resizing is optimized to happen infrequently.

---

## ⚡ Time Complexity
| Operation        | Complexity           |
| ---------------- | -------------------- |
| Access element   | **O(1)**             |
| Insert at end    | **O(1)** (amortized) |
| Insert in middle | **O(n)**             |
| Resize operation | **O(n)**             |

---

### 📌 Important Note

Appending is usually fast, but becomes slower when resizing occurs.

---

## ✅ When to Use Dynamic Arrays

Use dynamic arrays when:
- Number of elements is unknown
- Data size changes frequently
- Frequent insertions or deletions occur

---

## 🐍 Python Dynamic Arrays (Lists)

Python lists are dynamic arrays.

Create a List
```python
numbers = [3, 4, 5, 6]
```

Access Elements (Indexing)
```python
numbers[0]  # 3
numbers[1]  # 4
numbers[2]  # 5
numbers[3]  # 6
```
✅ Indexing starts at 0.

Update Values
```python
numbers[2] = 16
```

Add Elements
Append (add to end)
```python
numbers.append(7)
```

Insert at specific position
```python
numbers.insert(3, 15)
```

Remove Elements
```python
numbers.pop(2)
```

If no index is provided:
```python
numbers.pop()  # removes last element
```

---

## ⚖️ Static vs Dynamic Arrays Comparison

| Feature        | Static Array  | Dynamic Array         |
| -------------- | ------------- | --------------------- |
| Size           | Fixed         | Resizable             |
| Memory         | Pre-allocated | Automatically managed |
| Access Speed   | O(1)          | O(1)                  |
| Insert/Delete  | Limited       | Flexible              |
| Flexibility    | Low           | High                  |
| Python Support | ❌ No          | ✅ Yes (list)          |

---

## 🎯 Key Takeaways

✅ Static arrays
- Fixed size
- Very predictable performance
- Best when size is known

✅ Dynamic arrays
- Flexible resizing
- Easier to use
- Ideal for changing data sizes

---

## 🧠 Final Insight

Choosing between static and dynamic arrays involves a tradeoff:
- Simplicity & predictability → Static arrays
- Flexibility & convenience → Dynamic arrays
Selecting the right data structure is an important problem-solving skill that improves with practice.  
