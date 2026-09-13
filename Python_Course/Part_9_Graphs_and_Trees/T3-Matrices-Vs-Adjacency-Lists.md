# 📊 How Do Matrices and Adjacency Lists Work?

Graphs are very powerful **data structures** made up of a set of **nodes** (also called **vertices**) and **edges** that connect them.

There are two common ways to implement graphs in code:

- 🧮 **Adjacency Matrices**
- 📋 **Adjacency Lists**

Let’s explore how they work, including their advantages and limitations.

---

## 🧮 Adjacency Matrices

An **adjacency matrix** is a **two-dimensional list (2D array)** where:

- Rows represent vertices (nodes)
- Columns represent vertices (nodes)
- Values represent connections (edges) between nodes

If a matrix is stored in a variable named `matrix`, then:
```python
matrix[i][j]
```


represents the edge between **node i** and **node j**.

---

### 🔢 Meaning of Values

The values depend on the type of graph:

✅ **Unweighted Graph**
- `1` → edge exists
- `0` → no edge

✅ **Weighted Graph**
- Value represents the **weight** of the edge.

---

### ⚡ Advantages

- ✅ Checking if an edge exists takes **constant time**:
```python
Time Complexity: O(1)
```

The program directly accesses one value in the matrix.

---

### ⚠️ Limitations

- ❌ Requires large memory space:
```python
Space Complexity: O(V²)
```

(where **V = number of vertices**)

This becomes inefficient for **sparse graphs** (graphs with few edges) because many `0`s must still be stored.

- ❌ Finding neighbors is slower:
```python
Time Complexity: O(V)
```

The program must scan an entire row or column.

---

### 🧩 Example Graph

Graph with nodes:
```python
A, B, C, D
```

Connections:

- A → B, C, D
- B → A, D
- C → A
- D → A, B

---

### 📐 Adjacency Matrix Representation
```python
A B C D
A [0, 1, 1, 1]
B [1, 0, 0, 1]
C [1, 0, 0, 0]
D [1, 1, 0, 0]
```

- Rows = source node
- Columns = destination node
- Diagonal values = self-loops (all `0` here)

---

### 🐍 Python Implementation

```python
adjacency_matrix = [
    [0, 1, 1, 1],  # Neighbors of A
    [1, 0, 0, 1],  # Neighbors of B
    [1, 0, 0, 0],  # Neighbor of C
    [1, 1, 0, 0]   # Neighbors of D
]
```

---

### 📋 Adjacency Lists

An adjacency list stores all neighbors of each node.

It can be implemented using:
- 📦 An array
- 🗂️ A dictionary

---

### 🧱 Implementation Methods
#### 1️⃣ Dictionary-Based

Each key represents a node, and its value is a list of neighbors.
```python
adjacency_list = {
    'A': ['B', 'C', 'D'],
    'B': ['A', 'D'],
    'C': ['A'],
    'D': ['A', 'B']
}
```

#### 2️⃣ Array (2D List) Implementation

Each index represents a node.
```python
adjacency_list = [
    ['B', 'C', 'D'],  # A (index 0)
    ['A', 'D'],       # B (index 1)
    ['A'],            # C (index 2)
    ['A', 'B']        # D (index 3)
]
```

---

### ⚡ Advantages
✅ More memory efficient:
```python
Space Complexity: O(V + E)
```

where:
- V = vertice
- E = edges
- ✅ Fast neighbor lookup (direct list access)

---

### ⚠️ Limitations
❌ Slower edge checking compared to matrices:
```python
Worst-case Time: O(V)
```
> The algorithm may need to scan a long neighbor list.

---

### 🔍 Key Difference

| Feature         | Adjacency Matrix | Adjacency List |
| --------------- | ---------------- | -------------- |
| Stores          | 0/1 or weights   | Neighbor nodes |
| Space Usage     | O(V²)            | O(V + E)       |
| Edge Lookup     | Fast ✅           | Slower ❌       |
| Neighbor Lookup | Slower ❌         | Fast ✅         |

---

### 🧠 When Should You Use Each?

🧮 Use Adjacency Matrix When:
- Graph is dense (many edges)
- Fast edge lookup is required

📋 Use Adjacency List When:
- Graph is sparse
- Memory efficiency matters
- Real-world datasets are used

---

### ✅ Summary

Both representations are essential for working with graphs:
- Adjacency Matrices → Fast edge checking, high memory usage
- Adjacency Lists → Memory efficient, faster neighbor traversal

Choosing the right one depends on:
- Graph size
- Number of edges
- Required operations

🚀 In real-world applications, adjacency lists are usually preferred because most graphs are sparse.
