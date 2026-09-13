# 🧱 What is Object-Oriented Programming, and How Does Encapsulation Work?

## 🔹 Object-Oriented Programming (OOP)

Object-oriented programming, also known as **OOP**, is a programming style in which developers treat everything in their code like a real-world **object**.

A **class** is like a blueprint for creating objects. Every object created from a class has:

- **Attributes** → define the data
- **Methods** → define the behavior

---

## 🏗️ Class Structure (Syntax Reminder)

```python
class ClassName:
    def __init__(self, parameters):
        attribute = value

    def method_name(self):
        # method logic
```

### 🚗 Example: A Simple Class

Here’s an example of a class that uses the __init__ special method to initialize attributes whenever an object is created:
```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

# create two objects from the Car class
car1 = Car('Toyota', 'red')
car2 = Car('Lambo', 'green')

print('Car 1 Brand:', car1.brand)  # Car 1 Brand: Toyota
print('Car 1 Color:', car1.color)  # Car 1 Color: red

print('Car 2 Brand:', car2.brand)  # Car 2 Brand: Lambo
print('Car 2 Color:', car2.color)  # Car 2 Color: green
```

---

## 📚 The Four Principles of OOP

Object-oriented programming has four key principles that help organize and manage code effectively:
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction
➡️ This lesson focuses on encapsulation.

---

## 🔐 What is Encapsulation?

Encapsulation is the bundling of the attributes and methods of an object into a single unit—the class.

It allows you to:
- Hide internal data
- Expose only safe, controlled ways to interact with that data
- Centralize validation logic
Think of public methods as doors, and private attributes as what’s behind the doors.

---

### 👛 Example: Wallet Without Direct Access

You want to track a wallet balance where:
- Users can deposit or withdraw
- No one can directly modify the balance

🔸 Using a Single Underscore (Convention)
```python
class Wallet:
    def __init__(self, balance):
        self._balance = balance  # For internal use by convention

    def deposit(self, amount):
        if amount > 0:
            self._balance += amount  # Add to the balance safely

    def withdraw(self, amount):
        if 0 < amount <= self._balance:
            self._balance -= amount  # Remove from the balance safely
```
🔹 A single underscore (_balance) means internal use by convention, but it is still accessible from outside the class.

---

### 🔒 Private Attributes with Double Underscore

Prefixing attributes and methods with a double underscore makes them effectively private.
```python
class Wallet:
    def __init__(self, balance):
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

account = Wallet(500)
print(account.__balance)
# AttributeError: 'Wallet' object has no attribute '__balance'
```

---

### 📤 Accessing Private Data Safely (Getter Method)

To access private data, define a public method:
```python
class Wallet:
    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

    def get_balance(self):
        return self.__balance
```

✅ Usage Example
```python
acct_one = Wallet(100)
acct_one.deposit(50)
print(acct_one.get_balance())  # 150

acct_two = Wallet(450)
acct_two.withdraw(28)
print(acct_two.get_balance())  # 422

acct_two.deposit(150)
print(acct_two.get_balance())  # 572
```

---

### 🛡️ Private Validation Method

You can also define a private method to validate inputs:
```python
class Wallet:
    def __init__(self):
        self.__balance = 0

    def __validate(self, amount):
        if amount < 0:
            raise ValueError('Amount must be positive')

    def deposit(self, amount):
        self.__validate(amount)
        self.__balance += amount

    def withdraw(self, amount):
        self.__validate(amount)
        if amount > self.__balance:
            raise ValueError('Insufficient funds')
        self.__balance -= amount

    def get_balance(self):
        return self.__balance
```

🧪 Example Usage
```python
acct_one = Wallet()
acct_one.deposit(3)
print(acct_one.get_balance())  # 3

acct_one.deposit(50)
print(acct_one.get_balance())  # 53

acct_one.deposit(-4)   # ValueError: Amount must be positive
acct_one.withdraw(-8)  # ValueError: Amount must be positive
acct_one.withdraw(58)  # ValueError: Insufficient funds
```
🔹 The __validate method runs behind the scenes, ensuring all operations are safe and consistent.

---

### 🧾 Summary
- Encapsulation protects internal data
- Public methods provide controlled access
- Private attributes and methods prevent tampering
- Validation logic is centralized in one place
✅ This design makes your classes safer, easier to maintain, and more flexible to extend in the future.
