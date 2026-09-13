# 📊 What Are Graphs in Computer Science?

Graphs are **data structures** used to represent the connections or relationships between objects or entities. They're often used to model **networks** 🌐.

The types of networks that you can model with a graph include:

- 👥 Social networks
- 🚗 Transportation networks
- 📡 Communications networks
- 🎯 Recommendation systems

For example, graphs can represent connections between users on a social media platform or connections between cities on a road network.

Graphs are very versatile ✨.

---

## 🧩 Components of a Graph

A graph is often represented as a collection of points (circles) connected by lines.

These represent the two main components:

- 🔵 **Nodes (Vertices)**
- 🔗 **Edges**

---

### 🔵 Nodes (Vertices)

Nodes, also known as **vertices**, represent the objects or entities in a network.

They could represent:

- 👤 Users  
- 📦 Products  
- 🚉 Stations  
- 🏙️ Cities  
- 🧩 Any entity in a model  

Nodes are usually drawn as circles labeled **A, B, C, D, E**, etc.

---

### 🔗 Edges

Edges are the **connections** between nodes.

If two nodes are connected by an edge, it means they are related in the network.

The connection may be:

- 🛣️ Physical (roads between cities)
- 💬 Abstract (social media friendships)

If two nodes are directly connected, they are called **adjacent nodes**.

---

## 🧠 Types of Graphs

There are different types of graphs with different characteristics and uses.

---

### ↔️ Undirected Graphs

Undirected graphs have edges with **no direction**.

✅ Connection works both ways.

If node A connects to node B:
- A → B
- B → A

Example:
Friendships on social media 👥 (bidirectional relationships).

---

### ➡️ Directed Graphs

Directed graphs (**digraphs**) have edges with a **specific direction**.

➡️ A connection from A to B does NOT mean B connects to A.

Edges are shown using arrows.

Example:
🚦 One-way streets in road networks.

Two-way connections require **two arrows**.

---

### 🏷️ Vertex Labeled Graphs

Each node has a **label or identifier**.

Labels help to:

- Identify nodes
- Display information visually
- Store additional data

Example:
Cities labeled with names or coordinates 🗺️.

---

### 🔄 Cyclic Graphs

A **cyclic graph** contains at least one **cycle**.

🔁 A cycle is a path that starts and ends at the same node.

Example:
B → C → D → B

---

### 🏷️ Edge Labeled Graphs

Edges contain labels describing properties of the connection.

Labels appear next to edges.

---

### ⚖️ Weighted Graphs

Weighted graphs assign **numerical values** to edges.

Weights represent a **cost**, such as:

- 📏 Distance
- ⏱️ Travel time
- 💰 Price
- 🌐 Network latency

Example:
Cost between nodes B and D = 3.

---

### 🌲 Directed Acyclic Graph (DAG)

A **Directed Acyclic Graph (DAG)** is:

- ➡️ Directed
- 🚫 Contains NO cycles

You cannot return to the starting node by following edges.

Common uses:

- 📅 Task scheduling
- 🔗 Dependency management
- 🧾 Version control systems

---

### 🧱 Disconnected Graph

A disconnected graph has two or more groups of nodes with **no edges between them**.

Example:
👥 Separate friend groups on social media with no mutual connections.

Each group is called a **component**.

---

## ⚙️ Graph Implementations

Graphs can be implemented using:

- 📦 Sets
- 🧮 Functions
- 📚 Arrays
- 📋 Adjacency Lists
- 🔢 Adjacency Matrices

---

## 🚀 Why Graphs Matter

Understanding graphs is essential for solving problems in:

- 💻 Computer Science
- 🌐 Networking
- 🚗 Transportation Systems
- 📱 Social Media Analysis
- 🎯 Recommendation Systems

Graphs provide a powerful way to model real-world relationships and connections.
