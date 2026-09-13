# 💳 Implement the Luhn Algorithm

The **Luhn algorithm**, also known as the "modulus 10" or "mod 10" algorithm, is a simple checksum formula used to validate a variety of identification numbers, like credit card numbers. ✅

---

## 🔹 Steps to Validate a Number Using the Luhn Algorithm

1. Starting from the **right**, and excluding the rightmost digit (the **check digit**), **double the value of every other digit**.  
2. If the result of doubling a digit is **greater than 9**, sum the digits to get a single digit. Alternatively, you can **subtract 9** from the result.  
3. Take the **sum of all the digits**, including the check digit.  
4. If the sum of all the digits is a **multiple of 10**, then the number is **valid**; otherwise, it is **not valid**. ❌

---

## 🔹 Example

Let's validate the number **453914881**:

| Account number      | 4 | 5  | 3 | 9  | 1 | 4 | 8 | 8  | 1 |
|--------------------|---|----|---|----|---|---|---|----|---|
| Double every other | 4 | 10 | 3 | 18 | 1 | 8 | 8 | 16 | 1 |
| Sum 2-digit numbers| 4 | 1  | 3 | 9  | 1 | 8 | 8 | 7  | 1 |

**Sum all numbers:** 4 + 1 + 3 + 9 + 1 + 8 + 8 + 7 + 1 = **42**  

Since **42** is **not a multiple of 10**, the number is **invalid**. ❌

---

## 🎯 Objective

Build a credit card validator using the **Luhn algorithm**. Fulfill the user stories below and get all tests to pass to complete the lab.

---

## 📜 User Stories

- Define a function named `verify_card_number` that takes a string of digits (representing a card number) and verifies whether it is valid according to the Luhn algorithm.  
- Within the `verify_card_number` function:  
  - Handle any **dashes** or **spaces** that may be present in the card number.  
  - Return `VALID!` if the card number is valid; otherwise, return `INVALID!`.  

---

## 💡 Sample Inputs & Expected Outputs

| Card Number            | Message     |
|------------------------|------------|
| 453914889              | VALID! ✅  |
| 4111-1111-1111-1111   | VALID! ✅  |
| 1234 5678 9012 3456    | INVALID! ❌ |

---

# CODE

```python
def verify_card_number(digits):
    n1 = len(digits)
    digits_only = []
    transformed = []
    total = 0  
    
    # Remove spaces or hyphens and convert to integers
    for i in range(n1):
        if digits[i] == " " or digits[i] == "-":
            continue
        else: 
            digits_only.append(int(digits[i]))

    n2 = len(digits_only)

    # Apply Luhn doubling: starting from the right, double every second digit
    for i in range(n2):
        # Determine position from the right
        if (n2 - 1 - i) % 2 == 1:
            # Double the digit
            doubled = digits_only[i] * 2
            if doubled > 9:
                doubled -= 9
            transformed.append(doubled)
        else:
            transformed.append(digits_only[i])

    # Sum all digits
    for i in range(n2):
        total += transformed[i]

    # Check validity
    if total % 10 == 0:
        return "VALID!"
    else:
        return "INVALID!"
```
