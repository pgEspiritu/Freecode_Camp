# 🔎 How Do Depth First and Breadth First Search Work?

As you start working with data structures and algorithms, you'll realize that one common operation is **visiting each node**.

This process is called **traversing** the data structure.

Traversals are used to:

- 🖨️ Print node values
- 🔍 Find a specific value
- ⚙️ Perform operations on nodes

By systematically visiting each node, we make sure **no node is skipped**.

But how do we decide:

- 📍 Where to start?
- ➡️ Which node to visit next?
- 🧭 What order to follow?

Without a strategy, traversing would be like walking through a maze without a path.

That’s where **Breadth-First Search (BFS)** and **Depth-First Search (DFS)** come in.

They are commonly used to:

- 🌐 Traverse graphs
- 🌳 Traverse trees
- 🛣️ Find paths between nodes

---

# 🌊 Breadth-First Search (BFS)

Breadth-First Search (BFS) visits **all neighboring nodes first** before moving to the next level.

👉 It explores the graph **level by level**.

## ✅ Why Use BFS?

- Finds the **shortest path** in an **unweighted graph**
- Explores all nodes at the same depth before going deeper

## 🧰 Data Structure Used

BFS uses a **Queue**.

A queue follows **FIFO (First In, First Out)**:
- The first node added is the first removed.

---

## 📝 BFS Algorithm Steps

1. Start at a specific node.
2. Mark it as visited.
3. Add it to the queue.
4. While the queue is not empty:
   - Dequeue a node.
   - Add its unvisited neighbors to the queue.
   - Mark them as visited.

---

## 🌳 BFS Example (Tree Traversal)

Tree structure:
```text
    A
   / \
  B   C
 / \ / \
D  E F  G
```

---

### Step-by-Step BFS

**Step 1**
```text
Queue: [A]
Visited: {A}
```

**Step 2**
```text
Queue: [B, C]
Visited: {A, B, C}
```

**Step 3**
```text
Queue: [C, D, E]
Visited: {A, B, C, D, E}
```

**Step 4**
```text
Queue: [D, E, F, G]
Visited: {A, B, C, D, E, F, G}
```

Continue removing nodes until queue is empty.

---

## 📌 BFS Traversal Order
```text
A → B → C → D → E → F → G
```

💡 Notice: It visits **level by level**.

---

## ⚠️ BFS Limitation

Because it stores nodes in a queue, it may require **large memory** when many nodes exist at the same level.

---

# 🌲 Depth-First Search (DFS)

Depth-First Search (DFS) explores **as deep as possible** along one branch before backtracking.

Imagine exploring a maze:

- Pick a path
- Follow it completely
- If you hit a dead end, go back

---

## ✅ Why Use DFS?

- 🧩 Solve puzzles
- 🔄 Detect cycles
- 🧱 Find connected components
- 🌐 Traverse graphs deeply

---

## 🧰 Data Structure Used

DFS uses:

- 📚 A **Stack** (explicit)
OR
- 🔁 **Recursion** (implicit call stack)

A stack follows **LIFO (Last In, First Out)**:
- The last node added is the first removed.

---

## 📝 DFS Algorithm Steps

1. Start at a node.
2. Mark it as visited.
3. Add it to the stack.
4. While the stack is not empty:
   - Pop a node.
   - Visit/process it.
   - Add its unvisited neighbors to the stack.

---

## 🌳 DFS Example (Same Tree)
```text
    A
   / \
  B   C
 / \ / \
D  E F  G
```

---

### Step-by-Step DFS

**Step 1**
```text
Stack: [A]
Visited: {A}
```

**Step 2**
```text
Stack: [C, B]
Visited: {A, B, C}
```

**Step 3**
```text
Stack: [C, E, D]
Visited: {A, B, C, D, E}
```

Continue until stack is empty.

---

## 📌 DFS Traversal Order
```text
A → B → D → E → C → F → G
```

💡 Notice: It explores **one full branch before moving to another**.

---

## ⚠️ DFS Limitation

- Does **not guarantee shortest path** in an unweighted graph.

---

# 🔄 BFS vs DFS Comparison

| Feature | 🌊 BFS | 🌲 DFS |
|----------|--------|--------|
| Traversal Style | Level by level | Deep first |
| Data Structure | Queue (FIFO) | Stack (LIFO) |
| Shortest Path (Unweighted) | ✅ Yes | ❌ Not guaranteed |
| Memory Usage | Higher (wide graphs) | Lower (usually) |
| Good For | Shortest paths | Maze solving, cycles |

---

# 🚀 Final Thoughts

Both BFS and DFS are essential algorithms for traversing graphs and trees.

- 🌊 **BFS** explores level by level — best for shortest paths.
- 🌲 **DFS** explores branch by branch — best for deep exploration and cycle detection.

Understanding both helps you choose the right algorithm for the right problem.

---

# ❓ Questions

- When would BFS be better than DFS?
- Why doesn’t DFS always find the shortest path?
- What happens if a graph contains cycles and you don’t track visited nodes?
