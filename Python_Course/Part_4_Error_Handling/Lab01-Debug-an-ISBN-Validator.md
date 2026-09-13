# 📚 Debug an ISBN Validator

The **ISBN (International Standard Book Number)** is a unique identifier assigned to commercial books. It can be either **10 or 13 digits long**, and the **last digit** is a check digit calculated from the other digits.

Camperbot has tried to build their own ISBN validator, but the code contains some mistakes. In this lab, you will **fix the existing code** to make it function properly. 🛠️

---

## 📝 Expected Behavior

When the program runs, it should show the prompt:

```python
Enter ISBN and length:
```


- Users can enter the ISBN code they want to validate in `ISBN,length` format.
- The ISBN code **should not contain hyphens**, followed by its length (`10` or `13`) separated by a comma.

**Example inputs:**

- ISBN-10: `1530051126,10`  
- ISBN-13: `9781530051120,13`

---

## 🔢 How to Find the Check Digit

You **do not need to know the detailed calculation logic** for this lab. The following functions handle it:

- `calculate_check_digit_10` → Returns the expected check digit for ISBN-10
- `calculate_check_digit_13` → Returns the expected check digit for ISBN-13

**Notes:**

- ISBN-10 check digit can be `0-9` or uppercase `X`
- ISBN-13 check digit can be `0-9`

---

## 🎯 Objective

Complete the user stories below to get all tests to pass.

### ✅ User Stories

1. Fix the **IndentationError** in the current code.  
2. Handle **IndexError** if the user does not enter comma-separated values.
   - Show the message: `Enter comma-separated values.` and terminate the program.
3. Handle **ValueError** if the user enters a non-numeric value for the length.
   - Show the message: `Length must be a number.` and terminate the program.
4. Fix the **off-by-one error** in the `validate_isbn` function.
5. Fix the **TypeError** and **IndexError** that occur when a valid ISBN code is entered.
6. Handle **ValueError** if the user enters an incorrect ISBN with non-numeric characters.
   - Show the message: `Invalid character was found.` ⚠️
7. When the user enters valid ISBNs:
   - `1530051126,10` → `Valid ISBN Code.` ✅  
   - `9781530051120,13` → `Valid ISBN Code.` ✅
8. Comment out the `main()` call in the global space so tests can run properly.

---

## 📊 Expected Output Table

| ISBN Code | Length | Message | Example Input |
|-----------|--------|---------|---------------|
| Valid | Valid | Valid ISBN Code. ✅ | 1530051126,10 |
| Invalid Number | Valid | Invalid ISBN Code. ❌ | 1530051125,10 |
| Wrong Length / Blank | Valid | ISBN-10 code should be 10 digits long.<br>ISBN-13 code should be 13 digits long. ⚠️ | 9781530051120,10 or 1530051126,13 |
| Non-numeric characters (except check digit) | Valid | Invalid character was found. ⚠️ | 15-0051126,10 |
| Any | Invalid Number | Length should be 10 or 13. ❌ | 1530051126,9 |
| Any | Non-numeric / Blank | Length must be a number. ❌ | 1530051125,A |
| Not comma-separated | Not comma-separated | Enter comma-separated values. ⚠️ | 1530051125 |

---

## 🧪 Example Inputs for Manual Testing

**Valid ISBN-10:**
```python
1530051126,10
9971502100,10
080442957X,10
```


**Valid ISBN-13:**
```python
9781530051120,13
9781947172104,13
```

---

## ORIGINAL CODE

```python
def validate_isbn(isbn, length):
    if len(isbn, length) != length:
        print(f'ISBN-{length} code should be {length} digits long.')
        return
    main_digits = isbn[0:length]
    given_check_digit = isbn[length]
    main_digits_list = [int(digit) for digit in main_digits]
    # Calculate the check digit from other digits
    if length == 10:
        expected_check_digit = calculate_check_digit_10(main_digits_list)
    else:
        expected_check_digit = calculate_check_digit_13(main_digits_list)
    # Check if the given check digit matches with the calculated check digit
    if given_check_digit == expected_check_digit:
        print('Valid ISBN Code.')
    else:
        print('Invalid ISBN Code.')
def calculate_check_digit_10(main_digits_list):
    # Note: You don't have to fully understand the logic in this function.
    digits_sum = 0
    # Multiply each of the first 9 digits by its corresponding weight (10 to 2) and sum up the results
    for index, digit in enumerate(main_digits_list):
        digits_sum += digit * (10 - index)
    # Find the remainder of dividing the sum by 11, then subtract it from 11
    result = 11 - digits_sum % 11
    # The calculation result can range from 1 to 11.
    # If the result is 11, use 0.
    # If the result is 10, use upper case X.
    # Use the value as it is for other numbers.
    if result == 11:
        expected_check_digit = '0'
    elif result == 10:
        expected_check_digit = 'X'
    else:
        expected_check_digit = str(result)
    return expected_check_digit
def calculate_check_digit_13(main_digits_list):
    # Note: You don't have to fully understand the logic in this function.
    digits_sum = 0
    # Multiply each of the first 12 digits by 1 and 3 alternately (starting with 1), and sum up the results
    for index, digit in enumerate(main_digits_list):
        if index % 2 == 0:
            digits_sum += digit * 1
        else:
            digits_sum += digit * 3
    # Find the remainder of dividing the sum by 10, then subtract it from 10
    result = 10 - digits_sum % 10
    # The calculation result can range from 1 to 10.
    # If the result is 10, use 0.
    # Use the value as it is for other numbers.
    if result == 10:
        expected_check_digit = '0'
    else:
        expected_check_digit = str(result)
    return expected_check_digit
def main():
    user_input = input('Enter ISBN and length: ')
    values = user_input.split(',')
    isbn = values[0]
    length = int(values[1])
    if length == 10 or length == 13:
    validate_isbn(isbn, length)
    else:
    print('Length should be 10 or 13.')

main()
```

---

## FINAL CODE

```python

def validate_isbn(isbn, length):
    if len(isbn) != length:
        print(f'ISBN-{length} code should be {length} digits long.')
        return
    main_digits = isbn[0:length-1]
    given_check_digit = isbn[length-1]
    try:
        main_digits_list = [int(digit) for digit in main_digits]
    except ValueError:
        print('Invalid character was found.')
        return
    # Calculate the check digit from other digits
    if length == 10:
        expected_check_digit = calculate_check_digit_10(main_digits_list)
    else:
        expected_check_digit = calculate_check_digit_13(main_digits_list)
    # Check if the given check digit matches with the calculated check digit
    if given_check_digit == expected_check_digit:
        print('Valid ISBN Code.')
    else:
        print('Invalid ISBN Code.')
def calculate_check_digit_10(main_digits_list):
    # Note: You don't have to fully understand the logic in this function.
    digits_sum = 0
    # Multiply each of the first 9 digits by its corresponding weight (10 to 2) and sum up the results
    for index, digit in enumerate(main_digits_list):
        digits_sum += digit * (10 - index)
    # Find the remainder of dividing the sum by 11, then subtract it from 11
    result = 11 - digits_sum % 11
    # The calculation result can range from 1 to 11.
    # If the result is 11, use 0.
    # If the result is 10, use upper case X.
    # Use the value as it is for other numbers.
    if result == 11:
        expected_check_digit = '0'
    elif result == 10:
        expected_check_digit = 'X'
    else:
        expected_check_digit = str(result)
    return expected_check_digit
def calculate_check_digit_13(main_digits_list):
    # Note: You don't have to fully understand the logic in this function.
    digits_sum = 0
    # Multiply each of the first 12 digits by 1 and 3 alternately (starting with 1), and sum up the results
    for index, digit in enumerate(main_digits_list):
        if index % 2 == 0:
            digits_sum += digit * 1
        else:
            digits_sum += digit * 3
    # Find the remainder of dividing the sum by 10, then subtract it from 10
    result = 10 - digits_sum % 10
    # The calculation result can range from 1 to 10.
    # If the result is 10, use 0.
    # Use the value as it is for other numbers.
    if result == 10:
        expected_check_digit = '0'
    else:
        expected_check_digit = str(result)
    return expected_check_digit
def main():
    user_input = input('Enter ISBN and length: ')
    try:
        values = user_input.split(',')
        isbn = values[0]
        length = int(values[1])
    except IndexError:
        print('Enter comma-separated values.')
        return
    except ValueError:
        print('Length must be a number.')
        return
    if length == 10 or length == 13:
        validate_isbn(isbn, length)
    else:
        print('Length should be 10 or 13.')

#main()
```
