# 🤖 What Is an Algorithm and How Does Big O Notation Work?

Every computer program has a set of instructions executed in a specific order to complete a task, such as:

- Sorting numbers  
- Modifying images  
- Tracking inventory  
- Running a video game  

---

## 📝 What Is an Algorithm?

An **algorithm** is a set of unambiguous instructions for solving a problem or completing a task.  

Think of algorithms as **recipes**:

- They have a finite number of steps.  
- Each step must be precise and unambiguous.  
- They can have zero, one, or more inputs and outputs.  
- Algorithm steps are independent of programming language.  

To run an algorithm on a computer, it must be implemented in a language like Python or JavaScript.  

✅ A correct algorithm should produce the expected output for any valid input.  
✅ Efficiency matters: it affects runtime and memory usage as input size grows.

---

## ⚡ Algorithm Efficiency

Algorithm efficiency is measured in terms of:

1. **Time complexity** – how long it takes to run.  
2. **Space complexity** – how much memory it requires.  

Inefficient algorithms can slow down programs or even crash systems, especially as input size increases.  

---

## 📈 Big O Notation

**Big O notation** describes the **worst-case performance** or **growth rate** of an algorithm as the input size `n` increases.  

- Focuses on the **dominant term** of operations.  
- Ignores constant factors and lower-order terms.  
- Helps understand scalability without exact timing.

### Examples:

- Algorithm with `7n + 20` → dominated by `7n` → **linear** complexity.  
- Algorithm with `20n² + 15n + 7` → dominated by `20n²` → **quadratic** complexity.

---

## ⏱️ Common Time Complexities

| Complexity | Name | Example / Description |
|------------|------|----------------------|
| O(1)      | Constant | Time does not change with input size. E.g., check if a number is even. |
| O(log n)  | Logarithmic | Time grows slowly. E.g., Binary Search. |
| O(n)      | Linear | Time grows proportionally. E.g., iterate over a list. |
| O(n log n)| Log-Linear | Common in efficient sorting algorithms. E.g., Merge Sort, Quick Sort. |
| O(n²)     | Quadratic | Time grows quadratically. E.g., nested loops. |
| O(2^n)    | Exponential | Time doubles with each input. Rarely practical. |
| O(n!)     | Factorial | Time grows factorially. Very inefficient. |

### Python Example of O(1):

```python
def check_even_or_odd(number):
    if number % 2 == 0:
        return "Even"
    else:
        return "Odd"
```

**Python Example of O(n):**
```python
for grade in grades:  # grades is a list
    print(grade)
```

Python Example of O(n²):
```python
for i in range(n):
    for j in range(n):
        print("Hello, World!")
```

---

## 🖥️ Space Complexity

Big O notation can also describe memory usage:
- O(1) Constant Space – memory does not increase with input.
- O(n) Linear Space – memory grows proportionally. E.g., storing a copy of a list.
- O(n²) Quadratic Space – memory grows quadratically. E.g., creating a 2D matrix of size n×n.

---

## ✅ Summary

- Algorithms are building blocks of programs.
- Big O notation analyzes efficiency in terms of time and space as input size grows.
- Understanding efficiency is crucial for developing software that scales and works in real-world scenarios.
