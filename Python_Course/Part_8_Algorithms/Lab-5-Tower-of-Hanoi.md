# 🗼 Implement the Tower of Hanoi Algorithm

In this lab, you will solve the mathematical puzzle known as the **Tower of Hanoi**. The puzzle consists of **three rods** and a number of disks of different diameters.

The puzzle starts with the disks piled up on the **first rod**, arranged in decreasing size, with the **smallest disk on top** and the **largest disk at the bottom**.

---

## 🎯 Goal

Move all the disks from the **first rod** to the **last rod** while following the puzzle rules.

---

## 📏 Rules of the Puzzle

You must follow these three simple rules:

1. 🔝 You can move **only the top-most disk**.
2. 🔂 You can move **only one disk at a time**.
3. 🚫 You **cannot place a larger disk on top of a smaller disk**.

---

## 🧪 Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## 📜 User Stories

- You should have a function named `hanoi_solver` that takes an **integer** representing the total number of disks as the argument.
- The `hanoi_solver` function should solve the puzzle following the given rules in **2ⁿ − 1 moves**, where `n` is the total number of disks.
- The `hanoi_solver` function should **return a string** with all the moves taken to solve the puzzle, including the **starting arrangement**.
- Each move should appear on a **new line**.
- Rods should be represented as **lists of integers**:
  - The smallest disk is represented by `1`.
  - Each rod is separated by a space.

---

## 💡 Example Output

Calling:

```python
hanoi_solver(3)
```

Should return:
```text
[3, 2, 1] [] []
[3, 2] [] [1]
[3] [2] [1]
[3] [2, 1] []
[] [2, 1] [3]
[1] [2] [3]
[1] [] [3, 2]
[] [] [3, 2, 1]
```

## 🧠 Key Concept

The Tower of Hanoi uses recursion 🔁:
- Move n-1 disks to the auxiliary ro
- Move the largest disk to the destination rod
- Move n-1 disks onto the largest disk

Total moves required:
```python
2ⁿ − 1
```

---

## CODE

def hanoi_solver(n):
    # create the three rods
    rod1 = list(range(n, 0, -1))  # starting rod
    rod2 = []
    rod3 = []

    result = ""

    # function to save current state
    def record_state():
        nonlocal result
        result += str(rod1) + " " + str(rod2) + " " + str(rod3) + "\n"

    # move one disk between rods
    def move_disk(from_rod, to_rod):
        disk = from_rod.pop()
        to_rod.append(disk)
        record_state()

    # recursive Hanoi steps
    def hanoi(num, source, auxiliary, target):
        if num == 1:
            move_disk(source, target)
        else:
            hanoi(num - 1, source, target, auxiliary)
            move_disk(source, target)
            hanoi(num - 1, auxiliary, source, target)

    # record starting arrangement
    record_state()

    # solve puzzle
    hanoi(n, rod1, rod2, rod3)

    # remove last newline
    return result.strip()
```
