# 🔢 How Do You Work With Integers and Floating Point Numbers?

Integers and floats are the primary numeric data types in Python. With them, you can store numeric data and perform **mathematical operations**.

---

## 🧮 Integers

Integers are **whole numbers** without decimal points, either positive or negative:

```python
my_int_1 = 56
my_int_2 = -4

print(type(my_int_1))  # <class 'int'>
print(type(my_int_2))  # <class 'int'>
```

## Addition, Subtraction, Multiplication, Division

```python
# Addition
my_int_1 = 56
my_int_2 = 12
sum_ints = my_int_1 + my_int_2
print('Integer Addition:', sum_ints)  # 68

# Subtraction
diff_ints = my_int_1 - my_int_2
print('Integer Subtraction:', diff_ints)  # 44

# Multiplication
product_ints = my_int_1 * my_int_2
print('Integer Multiplication:', product_ints)  # 672

# Division
div_ints = my_int_1 / my_int_2
print('Integer Division:', div_ints)  # 4.666666666666667
```

---

## 🌊 Floating Point Numbers (Floats)

Floats are numbers with decimal points, like 3.14, -0.5, or 0.0.

```python
my_float_1 = -12.0
my_float_2 = 4.9

print(type(my_float_1))  # <class 'float'>
print(type(my_float_2))  # <class 'float'>
```

Arithmetic with Floats

```python
my_float_1 = 5.4
my_float_2 = 12.0

# Addition
float_addition = my_float_1 + my_float_2
print('Float Addition:', float_addition)  # 17.4

# Subtraction
float_subtraction = my_float_2 - my_float_1
print('Float Subtraction:', float_subtraction)  # 6.6

# Multiplication
float_multiplication = my_float_1 * my_float_2
print('Float Multiplication:', float_multiplication)  # 64.8

# Division
float_division = my_float_2 / my_float_1
print('Float Division:', float_division)  # 2.222222222222222
```
> ⚠️ Mixing integers and floats automatically converts the result to a float:

---

## 🧮 Advanced Arithmetic Operations

### Modulo Operator %

Returns the remainder of a division:
```python
mod_ints = 56 % 12
mod_floats = 12.0 % 5.4

print('Integer Modulus:', mod_ints)  # 8
print('Float Modulus:', mod_floats)  # 1.2
```

### Floor Division //

Divides two numbers and returns the greatest integer ≤ result:
```python
floor_div_ints = 56 // 12
floor_div_floats = 12.0 // 5.4

print('Integer Floor Division:', floor_div_ints)  # 4
print('Float Floor Division:', floor_div_floats)  # 2.0
```

### Exponentiation **

Raises a number to the power of another:
```python
exp_ints = 56 ** 12
exp_floats = 5.4 ** 12.0

print('Integer Exponentiation:', exp_ints)
print('Float Exponentiation:', exp_floats)
```

---

## 🔄 Type Conversion

Convert to Float
```python
my_int_1 = 56
my_float_1 = float(my_int_1)

print(my_float_1)       # 56.0
print(type(my_float_1)) # <class 'float'>
```

Convert to Integer
```python
my_float = 12.92563
my_int = int(my_float)

print(my_int)           # 12
print(type(my_int))     # <class 'int'>
```

Convert from Strings
```python
my_str_int = '45'
my_str_float = '7.8'

converted_int = int(my_str_int)
converted_float = float(my_str_float)

print(converted_int, type(converted_int))    # 45 <class 'int'>
print(converted_float, type(converted_float))# 7.8 <class 'float'>
```

---

## 🛠️ Useful Numeric Functions

### round()

Rounds a number to the specified decimal places:
```python
rounded_int_1 = round(4.798)
rounded_int_2 = round(4.253, 1)

print(rounded_int_1)  # 5
print(rounded_int_2)  # 4.3
```

### abs()

Returns the absolute value of a number:
```python
num = -15
absolute_value = abs(num)
print(absolute_value)  # 15
```

### pow()

Raises a number to a power, optionally with modulo:
```python
# Exponentiation
result_1 = pow(2, 3)  
print(result_1)  # 8

# Modular exponentiation
result_2 = pow(2, 3, 5)  
print(result_2)  # 3
```

---

# ➕ How Do Augmented Assignments Work?

Augmented assignment combines a **binary operation** with an **assignment** in one step. It takes a variable, applies an operation to it with another value, and stores the result back into the same variable.

If you're familiar with languages like JavaScript, you've probably heard of operators like `+=` (addition assignment) or `-=` (subtraction assignment). Python supports these too.  

---

## 🔹 Basic Syntax

```python
variable <operator>= value
```

This is equivalent to:
```python
variable = variable <operator> value
```

Example: Addition Assignment
```python
my_var = 10
my_var += 5

print(my_var)  # 15
```

Without augmented assignment:
```python
my_var = 10
my_var = my_var + 5

print(my_var)  # 15
```
> ✅ Advantage: Reduces redundancy and potential errors, making code more concise and readable.

---

## 🔹 Common Augmented Assignment Operators

Subtraction -=
```python
count = 14
count -= 3

print(count)  # 11
```

Multiplication *=
```python
product = 65
product *= 7

print(product)  # 455
```

Division /=
```python
price = 100
price /= 4

print(price)  # 25.0
```

Floor Division //=
```python
total_pages = 23
total_pages //= 5

print(total_pages)  # 4
```

Modulus %=
```python
bits = 35
bits %= 2

print(bits)  # 1
```

Exponentiation **=
```python
power = 2
power **= 3

print(power)  # 8
```

---

## 🔹 Using Augmented Assignments With Strings

Concatenation with +=
```python
greet = 'Hello'
greet += ' World'

print(greet)  # Hello World
```

Repetition with *=
```python
greet = 'Hello'
greet *= 3

print(greet)  # HelloHelloHello
```
> ⚠️ Other operators (-=, /=, *= with inappropriate types) will throw a TypeError:

```python
greet = 'Hello'
greet -= ' World'  # TypeError: unsupported operand type(s) for -=: 'str' and 'str'

greet = 'Hello'
greet /= 'World'  # TypeError: unsupported operand type(s) for /=: 'str' and 'str'
```

---

## 🔹 Increment and Decrement in Python

Python does not support ++ or -- operators.

Instead of x++, use:
```python
x += 1
```
> This makes it explicit that the value of x is incremented by 1.

Writing ++x in Python does not increment; it just applies the unary plus operator twice:
```python
x = 5
++x  # x is still 5
```
