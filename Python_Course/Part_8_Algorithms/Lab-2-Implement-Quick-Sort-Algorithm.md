# ⚡ Implement the Quicksort Algorithm

## 📝 Instructions

Implement the **Quicksort Algorithm**.

---

## 🎯 Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## 📖 User Stories

You should define a function named `quick_sort` to implement the quicksort algorithm.

The `quick_sort` function should take a list of integers as input and return a new list of these integers in sorted order from **least to greatest**.

---

## ⚙️ Algorithm Requirements

To implement the algorithm, you should:

1. 🔹 **Choose a Pivot**
   - Select a pivot value from the elements of the input list.
   - Use either the **first** or the **last** element of the list.

2. 🔹 **Partition the List**
   - Divide the input list into three sublists:
     - 📉 Elements **less than** the pivot
     - ⚖️ Elements **equal to** the pivot
     - 📈 Elements **greater than** the pivot

3. 🔹 **Recursive Sorting**
   - Recursively call `quick_sort` to sort the sublists.
   - 🔗 Concatenate the sorted sublists to produce the final sorted list.


---

# CODE

# ⚡ Quicksort Implementation (With Guide Comments)

Below is your `quick_sort` function with detailed comments explaining each step of the algorithm and how the divide-and-conquer process works.

---

## 🧾 Source Code with Comments

```python
def quick_sort(arr):

    # ---------------------------------------------------------
    # Base Case
    # If the list is empty, return an empty list.
    # A list with no elements is already sorted.
    # ---------------------------------------------------------
    if len(arr) < 1:
        return []

    # ---------------------------------------------------------
    # Step 1: Choose Pivot
    # Select the last element as the pivot value.
    # The pivot is used to partition the list.
    # ---------------------------------------------------------
    pivot_value = arr[-1]

    # ---------------------------------------------------------
    # Step 2: Create Sublists
    #
    # first_sublist  -> elements less than pivot
    # second_sublist -> elements greater than pivot
    # third_sublist  -> elements equal to pivot
    #
    # This handles duplicate values safely.
    # ---------------------------------------------------------
    first_sublist = []
    second_sublist = []
    third_sublist = []

    # Iterator for traversing the list
    iteration = 0

    # ---------------------------------------------------------
    # Step 3: Partition the List
    # Compare each element with the pivot and
    # place it into the correct sublist.
    # ---------------------------------------------------------
    while iteration < len(arr):

        # Element belongs to LEFT partition
        if arr[iteration] < pivot_value:
            first_sublist.append(arr[iteration])

        # Element belongs to RIGHT partition
        elif arr[iteration] > pivot_value:
            second_sublist.append(arr[iteration])

        # Element equals pivot (handles duplicates)
        else:
            third_sublist.append(pivot_value)

        iteration += 1

    # ---------------------------------------------------------
    # Step 4: Recursive Sorting (Divide and Conquer)
    #
    # Recursively sort:
    # - left partition
    # - right partition
    #
    # Then concatenate:
    # sorted_left + pivot_values + sorted_right
    # ---------------------------------------------------------
    return (
        quick_sort(first_sublist)
        + third_sublist
        + quick_sort(second_sublist)
    )
```
