# 📝 Implement the Selection Sort Algorithm

Selection sort is another popular sorting algorithm taught in most computer science courses.

This algorithm works by repeatedly finding the smallest element from the unsorted portion of the list and swapping it with the first unsorted element. It begins by selecting the minimum value in the entire list and swapping it with the first element. Then it moves to the second position, finds the smallest value in the remaining unsorted elements, and swaps it with the second element. This process continues, moving through the list one element at a time, until the entire list is sorted. 🔄

Selection sort results in a **quadratic time complexity** ⏱️ in the best, average, and worst case scenarios. The **space complexity** is **O(1)** 🧠 because the sorting is done in place, using a constant amount of memory regardless of the size of the list.

---

## 🎯 Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## 📜 User Stories

- You should define a function named `selection_sort`.  
- Your `selection_sort` function should have **one parameter** that represents the list of items.  
- Your `selection_sort` function should take a list and **sort the items in place from smallest to largest** 🔢.  
- Your `selection_sort` function should **modify the input list in-place**, and return it once it's sorted ✅.  
- Your `selection_sort` function should follow the **selection sort algorithm**, swapping the smallest element from the unsorted portion of the list with the first unsorted element 🔁.  
- Your `selection_sort` function should **not perform unnecessary swaps** when the smallest element is already in the correct position ❌↔️.  
- Your `selection_sort` function should **not use** either the built-in `sort()` method or `sorted()` function 🚫.


---

## CODE

```python
def selection_sort(items):
    """
    Sorts a list of items in place from smallest to largest using the selection sort algorithm.

    Args:
        items (list): The list of elements to sort.

    Returns:
        list: The sorted list (same object as input, sorted in-place).
    """
    n = len(items)
    
    # Traverse through all elements in the list
    for i in range(n - 1):
        # Assume the current position holds the smallest element
        min_index = i
        
        # Find the smallest element in the remaining unsorted portion
        for j in range(i + 1, n):
            if items[j] < items[min_index]:
                min_index = j
        
        # Swap only if the smallest element is not already at position i
        if min_index != i:
            items[i], items[min_index] = items[min_index], items[i]
    
    return items
```
