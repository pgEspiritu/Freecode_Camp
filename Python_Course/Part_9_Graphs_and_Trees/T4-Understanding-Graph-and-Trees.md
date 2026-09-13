# 🌳 What Are Trees and Tries and How Do They Work?

Trees are very important in the world of computer science.

A **tree** is a specific type of graph.

## 📌 Properties of a Tree

For a graph to be classified as a tree, it must:

- ❌ Have no loops or cycles (paths where the start and end nodes are the same)
- 🔗 Be connected (every node can be reached from every other node)

Trees are **non-linear data structures** that organize nodes in a hierarchy, where nodes may have:

- Parent nodes  
- Child nodes  
- Sibling nodes  

---

## 🌱 Basic Terminology

### 🔝 Root Node
The **root node** is the very top of a tree. It is the only node without a parent.  
Traversal usually starts here using algorithms like:

- Breadth-First Search (BFS)
- Depth-First Search (DFS)

---

### 👨‍👧 Parent Node
A node connected to nodes below it.

> Example: Node **A** is the parent of **B** and **C**

---

### 🧒 Child Node
A node connected to a node above it.

> Example: Nodes **D** and **E** are children of **C**

---

### 🍃 Leaf Node
A node with no children.

> Example: Nodes **B, D, and E**

---

## 📊 Tree Properties

### 📏 Depth
The number of edges from the root to a node.

> Example: Node **D** has depth **2**

---

### 📐 Height
The number of edges from a node to its deepest leaf.

> Example: Node **C** has height **1**

---

### 🔢 Degree
The number of children a node has.

- Node **B** → Degree **0**  
- Node **C** → Degree **2**

---

### 🌲 Tree Height
The height of the entire tree = height of the root node.

---

## 🌳 Types of Trees

Common types include:

- Binary Trees  
- Binary Search Trees (BST)  
- AVL Trees  
- Red-Black Trees  
- B-Trees  

---

# 🌿 Binary Trees and Binary Search Trees

## 🌲 Binary Tree
A **binary tree** is a tree where each node has at most:

- ⬅️ Left child  
- ➡️ Right child  

---

## 🔍 Binary Search Tree (BST)

A **BST** is a binary tree with an ordering rule:

- All values in the **left subtree** are **less than** the node  
- All values in the **right subtree** are **greater than** the node  
- Both subtrees must also be BSTs  

---

### 🌳 Subtree
A **subtree** is any node and its descendants forming a tree.

> Example: Nodes **C, D, and E**

---

### ⚖️ Balanced Tree
A tree where the heights of left and right subtrees are similar.

✅ Keeps operations efficient:
- Search  
- Insertion  
- Deletion  

---

# 🌲 Tries (Prefix Trees)

Now that you understand trees, let's explore **tries**.

## 🔤 What is a Trie?

A **trie** is a tree used to store a collection of strings.

Also called a **prefix tree**.

---

## 🧠 Key Idea

- Each node represents a **single character**
- The root represents an **empty string**
- Paths from root form **prefixes**

---

## 🔍 Example Words

Words stored:
- `top`
- `tea`
- `ten`

### ✨ Observation
- `"tea"` and `"ten"` share the prefix `"te"`
- The structure reuses nodes for shared prefixes

---

## 🏁 End-of-Word Marker

Nodes that complete a word are marked to indicate:

✔️ "This path forms a valid word"

---

## ⚡ Time Complexity

- 🔍 Search: **O(L)**
- ➕ Insertion: **O(L)**  
  *(L = length of the string)*

---

## ✅ Advantages

- Efficient prefix searching  
- Saves space for shared prefixes  
- Ideal for:
  - 🔎 Autocomplete systems  
  - 📝 Spell checkers  

---

## ⚠️ Disadvantages

- Can be memory-heavy if:
  - Many strings have **unique characters**
- Less efficient when prefix sharing is minimal  

---

# 🎯 Conclusion

Trees and tries are powerful data structures used in many real-world applications.

Understanding:
- 🌳 Tree hierarchy  
- 🔍 BST ordering  
- 🔤 Trie prefix storage  

…helps you choose the right structure for solving problems efficiently.

💡 Mastering these will significantly improve your problem-solving skills in computer science and software development.
