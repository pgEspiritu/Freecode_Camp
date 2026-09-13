# 🧱 How Do Stacks and Queues Work?

**Stacks** and **Queues** are common **linear data structures** used in computer science.

They store elements in order but follow **specific rules** for adding and removing items.

Understanding them is important for building **efficient algorithms and applications**.

---

# 📚 Stacks

## 🔹 What is a Stack?

A **Stack** is a **Last-In, First-Out (LIFO)** data structure.

This means:

➡️ The **last element added** is the **first element removed**.

---

## 🧠 Stack Structure

A stack has two ends:

- 🔼 **Top**
- 🔽 **Bottom**

All operations happen at the **top** of the stack.

Think of it like a **pile of dishes 🍽️**:

- You place dishes on **top**
- You remove dishes from **top**
```python
Top
[Plate 3]
[Plate 2]
[Plate 1]
Bottom
```

---

## ⚙️ Stack Operations

### ➕ Push Operation

Adding an element to the stack is called **push**.

We **push** an element **onto the top of the stack**.

Example:
```python
Push A
Push B
Push C

Stack:
Top
C
B
A
Bottom
```

---

### ➖ Pop Operation

Removing an element from the stack is called **pop**.

We **pop** the element from the **top**.

Example:
```python
Pop → removes C

Stack:
Top
B
A
Bottom
```

---

## ⏱️ Stack Time Complexity

| Operation | Complexity |
|-----------|------------|
| Push | O(1) |
| Pop | O(1) |

Both operations run in **constant time**, meaning the speed **does not change even if the stack grows**.

---

## 💾 Stack Space Complexity

| Operation | Space |
|-----------|-------|
| Push | O(1) |
| Pop | O(1) |

The memory required for these operations remains **constant**.

---

# 🚶 Queues

## 🔹 What is a Queue?

A **Queue** is a **First-In, First-Out (FIFO)** data structure.

This means:

➡️ The **first element added** is the **first element removed**.

---

## 🧠 Queue Structure

Queues have two ends:

- 🎯 **Front** – where elements are removed
- 🔚 **Back** – where elements are added

Think of a queue like a **line at a grocery store 🛒**.

- New people join at the **end**
- The person at the **front** leaves first
```python
Front → A B C ← Back
```

---

## ⚙️ Queue Operations

### ➕ Enqueue Operation

Adding an element to the queue is called **enqueue**.

The element is added to the **back** of the queue.

Example:
```python
Enqueue A
Enqueue B
Enqueue C

Queue:
Front → A B C ← Back
```

---

### ➖ Dequeue Operation

Removing an element from the queue is called **dequeue**.

The element is removed from the **front**.

Example:
```python
Dequeue → removes A

Queue:
Front → B C ← Back
```

---

## ⏱️ Queue Time Complexity

| Operation | Complexity |
|-----------|------------|
| Enqueue | O(1) |
| Dequeue | O(1) |

These operations also run in **constant time**.

---

## 💾 Queue Space Complexity

| Operation | Space |
|-----------|-------|
| Enqueue | O(1) |
| Dequeue | O(1) |

The memory usage stays **constant per operation**.

---

# ⚖️ Stack vs Queue

| Feature | Stack | Queue |
|-------|------|------|
| Order | LIFO | FIFO |
| Add Operation | Push | Enqueue |
| Remove Operation | Pop | Dequeue |
| Insert Location | Top | Back |
| Remove Location | Top | Front |

---

# 🎯 Key Takeaways

✅ **Stack**
- Last-In, First-Out  
- Operations: Push & Pop  
- Like a **stack of plates**

✅ **Queue**
- First-In, First-Out  
- Operations: Enqueue & Dequeue  
- Like a **waiting line**

---

# 🚀 Why They Are Important

Stacks and queues are widely used in:

- Function call stacks
- Task scheduling
- Breadth-first search (BFS)
- Undo/Redo systems
- Printer queues
- Operating systems

Understanding these structures helps you **design faster and more efficient algorithms**.
