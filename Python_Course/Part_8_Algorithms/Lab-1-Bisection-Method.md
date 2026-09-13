# 🧮 Implement the Bisection Method

The **bisection method**, also known as the **binary search method**, is a numerical technique used to find the **roots of a real-valued function**.

It works by repeatedly narrowing down an interval where the root lies until the result converges within a specified **tolerance** (acceptable error).

---

## 📌 How the Bisection Method Works

The method repeatedly:

1. Selects a lower and upper bound.
2. Finds the midpoint of the interval.
3. Determines which half contains the root.
4. Halves the interval again.
5. Continues until the result meets the tolerance requirement.

---

### ✅ Example

If the tolerance is:
```python
0.01
```

The algorithm keeps halving the interval until the difference between the upper and lower bounds is **≤ 0.01**.

---

## 🎯 Lab Objective

Implement a function that uses the **bisection method** to compute the **square root of a number**.

Complete all user stories and pass all tests.

---

## 📖 User Stories

### 1️⃣ Function Definition

Define a function named:

```python
square_root_bisection
```
with three parameters:
- Number – the value whose square root will be computed.
- Tolerance – acceptable error margin (must have a default value).
- Maximum iterations – maximum number of iterations allowed (must have a default value).

---

### 2️⃣ Function Requirements

The square_root_bisection function should behave as follows:

❌ Negative Numbers
If the input number is negative:
- Raise a ValueError with the message:
```python
Square root of negative number is not defined in real numbers
```

---

###🔢 Special Cases (0 and 1)

If the number is 0 or 1:
- Print:
```python
The square root of [number] is [number]
```
- Return the number itself.

---

### ✅ Positive Numbers
For any other positive number:
- Use the bisection method to approximate the square root.
- Print:
```python
The square root of [square_target] is approximately [root]
```
- Return the computed root value.

---

### ⚠️ Failure to Converge

If no value satisfies the tolerance condition within the allowed iterations:

- Print:
```python
Failed to converge within [maximum] iterations
```

- Return None.

---

### 🚫 Important Rule

❗ You are not allowed to import any modules for this lab.

#### 🧠 Key Concepts Practiced

- Binary search principles
- Numerical approximation
- Iterative algorithms
- Error tolerance handling
- Input validation

---

# CODE

# 🧮 Square Root Using the Bisection Method (With Guide Comments)

Below is the implementation of the **Bisection Method** with detailed comments explaining each step of the algorithm.

This guide helps you understand **why each line exists** and how the algorithm converges to the square root.

---

## 🧾 Source Code (With Explanatory Comments)

```python
def square_root_bisection(number, tolerance=0.01, max_iteration=100):

    # ---------------------------------------------------------
    # Step 1: Input Validation
    # Square roots of negative numbers are not real.
    # Raise an error if input is negative.
    # ---------------------------------------------------------
    if number < 0:
        raise ValueError(
            "Square root of negative number is not defined in real numbers"
        )

    # ---------------------------------------------------------
    # Step 2: Handle Simple Base Cases
    # The square root of 0 and 1 is the number itself.
    # No iteration needed.
    # ---------------------------------------------------------
    if number == 0 or number == 1:
        print(f"The square root of {number} is {number}")
        return number

    # ---------------------------------------------------------
    # Step 3: Initialize Search Bounds
    #
    # low  -> lower bound of search interval
    # high -> upper bound of search interval
    #
    # For numbers < 1, the root lies between 0 and 1.
    # For numbers >= 1, the root lies between 0 and number.
    # ---------------------------------------------------------
    low = 0
    high = max(1, number)

    # Counter to prevent infinite looping
    iteration = 0

    # ---------------------------------------------------------
    # Step 4: Bisection Loop
    #
    # Continue while:
    # - interval size is larger than tolerance
    # - iteration limit not exceeded
    # ---------------------------------------------------------
    while (high - low) > tolerance and iteration < max_iteration:

        # Find midpoint of current interval
        mid = (low + high) / 2

        # -----------------------------------------------------
        # Decide which half contains the square root
        #
        # If mid² is too large → root is on the LEFT side
        # Otherwise → root is on the RIGHT side
        # -----------------------------------------------------
        if mid * mid > number:
            high = mid
        else:
            low = mid

        # Increase iteration counter
        iteration += 1

    # ---------------------------------------------------------
    # Step 5: Check Convergence
    #
    # If interval is within tolerance,
    # compute final approximation.
    # ---------------------------------------------------------
    if (high - low) <= tolerance:
        root = (low + high) / 2
        print(f"The square root of {number} is approximately {root}")
        return root

    # ---------------------------------------------------------
    # Step 6: Failure Case
    # Algorithm did not converge within allowed iterations.
    # ---------------------------------------------------------
    print(f"Failed to converge within {max_iteration} iterations")
    return None
```
