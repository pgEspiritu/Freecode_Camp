# 🔎 What Is Binary Search and How Does It Differ From Linear Search?

Searching through a list of items is a common task in computer science. Two important searching algorithms you should understand are:

- **Linear Search**
- **Binary Search**

---

## 📌 Linear Search

**Linear search** starts at the beginning of a list and checks each item one by one until it finds the target value.

### ✅ Behavior
- If the target value is found → return its **index**.
- If the target value is not found → return **-1**.

We return `-1` because it is not a valid index in most programming languages.

---

### 🧾 Linear Search Code

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1
```

---

### 🧪 Example

Given the list:
```python
[13, 4, 7, 9, 10]
```
- Target = 9 → returns 3 (index position)
- Target = 5 → returns -1 (not found)

---

### ⚠️ Efficiency

Linear search is simple but not very efficient for large datasets.
- Time Complexity: O(n)
  - Search time grows linearly with list size.
- Space Complexity: O(1)
  - No extra memory required.

---

### 📌 Binary Search

Binary search is a more efficient searching algorithm.

⚠️ Requirement: The list must be sorted in ascending order.

---

### ⚙️ How Binary Search Works

1. Divide the list into two halves.
2. Check the middle element.
3. If the middle equals the target → return index.
4. If target is larger → search the right half.
5. If target is smaller → search the left half.
6. Repeat until found or no elements remain.
If the target is not found, return -1.

---

### 🧾 Binary Search Code

```python
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1

    return -1
```

---

### 🧠 Step-by-Step Explanation
- low → starting index of search range
- high → ending index of search range
- Continue searching while low <= high.

Steps performed each loop:
1. Compute middle index:
   ```python
   mid = (low + high) // 2
   ```
2. Compare middle value with target.
3. Adjust search range:
   - Search right half → low = mid + 1
   - Search left half → high = mid - 1
The process repeats until the target is found or the range becomes invalid.

---

### ⚡ Efficiency

Binary search is significantly faster for large sorted lists.
- Time Complexity: O(log n)
  - Search space halves each step.
- Space Complexity: O(1)
  - No additional memory required.

---

### 🔄 Linear Search vs Binary Search

| Feature            | Linear Search       | Binary Search      |
| ------------------ | ------------------- | ------------------ |
| List Requirement   | Unsorted or sorted  | Must be sorted     |
| Approach           | Check every element | Divide and conquer |
| Time Complexity    | O(n)                | O(log n)           |
| Speed (Large Data) | Slower              | Faster             |
| Space Complexity   | O(1)                | O(1)               |

---

### ✅ When to Use Each

Use Linear Search when:
- Data is small.
- List is unsorted.
- Simplicity is preferred.

Use Binary Search when:
- Data is large.
- List is sorted.
- Performance matters.
