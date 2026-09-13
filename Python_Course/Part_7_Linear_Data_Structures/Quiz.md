# 📘 Data Structures Quiz

**Instruction:**  
To pass the quiz, you must correctly answer at least **18 of the 20 questions** below.

---

## 1. What does Big O notation describe in algorithm analysis?

- ✅ How the time or space grows relative to input size (an upper bound).
- The exact runtime in seconds for a specific computer.
- How readable the code is to other developers.
- The percentage of code lines executed during a run.

---

## 2. When starting an algorithmic challenge, what is the best first step?

- Begin coding immediately to gain momentum.
- Optimize for performance before you understand the problem.
- Write unit tests only after finishing the solution.
- ✅ Clarify the problem and constraints with examples and edge cases.

---

## 3. What is the key difference between dynamic arrays and static arrays?

- Dynamic arrays store values of different types; static arrays cannot.
- Static arrays allow duplicate values; dynamic arrays do not.
- Dynamic arrays are faster than static arrays for every operation.
- ✅ Dynamic arrays can grow or shrink by resizing; static arrays have a fixed size.

---

## 4. What is the amortized time complexity of appending an element to the end of a dynamic array?

- O(n log n)
- O(n)
- ✅ O(1) amortized.
- O(log n)

---

## 5. Why does accessing the k-th element by index in a singly linked list take O(n) time?

- Nodes are stored contiguously, so shifting is required.
- The index is hashed and looked up in a table.
- The list must be resized before any access.
- ✅ You must traverse from the head node to the k-th node one by one.

---

## 6. Which feature does a doubly linked list have that a singly linked list does not?

- Random access to any index in O(1) time.
- Automatic maintenance of the list length as a constant.
- A built-in array buffer for faster iteration.
- ✅ Pointers to both next and previous nodes enabling backward traversal.

---

## 7. Which of the following best describes a stack?

- First In, First Out (FIFO) with removals at the front.
- A structure where any element can be removed in O(1) time.
- ✅ Last In, First Out (LIFO) with push and pop at the top.
- A circular buffer with constant-time random access.

---

## 8. Which operation removes the element at the front of a queue?

- pop
- peek
- ✅ dequeue
- push

---

## 9. What is the typical average-case time complexity to look up a value by key in a hash map?

- O(log n) due to binary search within buckets.
- ✅ O(1) on average with a good hash function and low load factor.
- O(n log n) because keys are sorted during insertion.
- O(n) because all keys must be scanned sequentially.

---

## 10. Which guarantee is provided by a set data structure?

- Elements are stored in sorted order by default.
- Duplicate values are allowed and kept together.
- Elements are indexed by their insertion position.
- ✅ It stores only unique elements (no duplicates).

---

## 11. In a dynamic array, what is the worst-case time complexity of inserting an element at index i (not at the end)?

- O(1) amortized
- ✅ O(n)
- O(log n)
- O(1)

---

## 12. What is the time complexity of inserting a new node at the head of a singly linked list?

- O(n)
- O(log n)
- O(n log n)
- ✅ O(1)

---

## 13. Which operation is used to remove an element from a stack?

- push
- dequeue
- ✅ pop
- Insert at bottom.

---

## 14. Which of the following best describes a queue?

- ✅ First In, First Out (FIFO) with enqueue at the back and dequeue at the front.
- Random access to any index in O(1) time.
- Last In, First Out (LIFO) with removals at the top.
- Elements are always kept in sorted order automatically.

---

## 15. What is a hash collision in a hash map?

- When a key maps to multiple distinct values by design.
- ✅ When two different keys produce the same hash index.
- When two identical keys are stored in different buckets.
- When the map runs out of memory and must be resized.

---

## 16. Why do hash maps resize (rehash) as they grow?

- To sort keys in ascending order for faster iteration.
- To compress values and reduce memory fragmentation.
- To avoid triggering the language's garbage collector.
- ✅ To keep the load factor low so that average operations remain O(1).

---

## 17. Which statement about sets is true?

- ✅ Membership tests are typically O(1) on average.
- Set membership tests are O(n log n) on average.
- Sets preserve insertion order by definition.
- Sets allow duplicate elements and keep counts.

---

## 18. Which time complexity grows faster than O(n log n) as n becomes large?

- O(log n)
- ✅ O(n²)
- O(1)
- O(n)

---

## 19. After implementing a brute-force solution, what is a good next step?

- Discard tests and rewrite the solution from scratch.
- Micro-optimize constant factors before measuring.
- Avoid considering edge cases to keep the code simple.
- ✅ Analyze its time/space complexity and optimize identified bottlenecks.

---

## 20. What does space complexity measure?

- The length of a program in lines of code.
- ✅ How memory usage grows relative to input size.
- How many CPU cores a program uses.
- How long a program takes to compile.

---
