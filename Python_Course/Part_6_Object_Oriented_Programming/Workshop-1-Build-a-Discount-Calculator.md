# CODE

```python
from abc import ABC, abstractmethod

class Product:
    def __init__(self, name: str, price: float) -> None:
        self.name = name
        self.price = price

    def __str__(self) -> str:
        return f'{self.name} - ${self.price}'

class DiscountStrategy(ABC):
    @abstractmethod
    def is_applicable(self, product: Product, user_tier: str) -> bool:
        pass

    @abstractmethod
    def apply_discount(self, product: Product) -> float:
        pass

class PercentageDiscount(DiscountStrategy):
    def __init__(self, percent: int) -> None:
        self.percent = percent

    def is_applicable(self, product: Product, user_tier: str) -> bool:
        return self.percent <= 70

    def apply_discount(self, product: Product) -> float:
        return product.price * (1 - self.percent / 100)

class FixedAmountDiscount(DiscountStrategy):
    def __init__(self, amount: int) -> None:
        self.amount = amount

    def is_applicable(self, product: Product, user_tier: str) -> bool:
        return product.price * 0.9 > self.amount

    def apply_discount(self, product: Product) -> float:
        return product.price - self.amount

class PremiumUserDiscount(DiscountStrategy):
    def is_applicable(self, product: Product, user_tier: str) -> bool:
        return user_tier.lower() == 'premium'

    def apply_discount(self, product: Product) -> float:
        return product.price * 0.8

class DiscountEngine:
    def __init__(self, strategies: list[DiscountStrategy]) -> None:
        self.strategies = strategies

    def calculate_best_price(self, product: Product, user_tier: str) -> float:
        prices = [product.price]

        for strategy in self.strategies:
            if strategy.is_applicable(product, user_tier):
                discounted = strategy.apply_discount(product)
                prices.append(discounted)

        return min(prices)

if __name__ == '__main__':
    product = Product('Wireless Mouse', 50.0)
    user_tier = 'Premium'

    strategies = [
        PercentageDiscount(10),
        FixedAmountDiscount(5),
        PremiumUserDiscount()
    ]

    engine = DiscountEngine(strategies)
    best_price = engine.calculate_best_price(product, user_tier)
print(f'Best price for {product.name} for {user_tier} user: ${best_price:.2f}')
```

---

# 🧮 Discount Calculator (Strategy Pattern) — Code Explanation

This program implements a **Discount Calculator** using **Object-Oriented Programming (OOP)** and the **Strategy Design Pattern** in Python.

Instead of hardcoding one discount rule, the system allows **multiple discount strategies** that can be added, removed, or modified easily.

---

# 📌 Overall Concept

The program:

1. Creates a **Product**
2. Defines multiple **discount strategies**
3. Checks which discounts are applicable
4. Applies valid discounts
5. Returns the **lowest (best) price**

👉 This design follows the **Open/Closed Principle**:
- Open for extension ✅
- Closed for modification ✅

---

# 🧱 Code Structure Overview
```mermaid
Product
│
├── DiscountStrategy (Abstract Base Class)
│ ├── PercentageDiscount
│ ├── FixedAmountDiscount
│ └── PremiumUserDiscount
│
└── DiscountEngine (Calculator)
```

---

## 1️⃣ Importing Abstract Base Classes

```python
from abc import ABC, abstractmethod
```

### ✅ Purpose

- `ABC` → Allows creation of abstract classes
- `@abstractmethod` → Forces subclasses to implement required methods
This ensures all discount types follow the same structure.

---

## 2️⃣ Product Class

```python
class Product:
    def __init__(self, name: str, price: float) -> None:
        self.name = name
        self.price = price
```

### ✅ Purpose

Represents an item being purchased.
| Attribute | Description    |
| --------- | -------------- |
| `name`    | Product name   |
| `price`   | Original price |

**String Representation**
```python
def __str__(self) -> str:
    return f'{self.name} - ${self.price}'
```

Allows printing the product nicely:
```code
Wireless Mouse - $50.0
```

---

## 3️⃣ Abstract Discount Strategy (Blueprint)

```python
class DiscountStrategy(ABC):
```
This is a template for all discount types.

#### **Required Methods**

A. Check Applicability
```python
@abstractmethod
def is_applicable(self, product: Product, user_tier: str) -> bool:
```
Determines: Should this discount be used?

B. Apply Discount
```python
@abstractmethod
def apply_discount(self, product: Product) -> float:
```
Calculates the discounted price.

---

## 4️⃣ Percentage Discount

```python
class PercentageDiscount(DiscountStrategy):
```
Applies a percentage-based discount.


**Constructor**
```python
def __init__(self, percent: int):
    self.percent = percent
```

Example:
```code
10% discount
```

**Applicability Rule**
```python
return self.percent <= 70
```
✔ Prevents unrealistic discounts (>70%).

**Discount Formula**
```python
return product.price * (1 - self.percent / 100)
```

Example:
```code
$50 with 10% discount
= 50 × 0.9
= $45
```

---

## 5️⃣ Fixed Amount Discount

```python
class FixedAmountDiscount(DiscountStrategy):
```
Subtracts a fixed value.

**Applicability Rule**
```python
return product.price * 0.9 > self.amount
```
Meaning:
- Discount cannot exceed reasonable limits
- Prevents negative prices

**Discount Calculation**
```python
return product.price - self.amount
```

Example:
```code
$50 - $5 = $45
```

---

## 6️⃣ Premium User Discount

```python
class PremiumUserDiscount(DiscountStrategy):
```
Special discount for premium users.

**Applicability Check**
```python
return user_tier.lower() == 'premium'
```
Only premium users qualify.

**Discount Logic**
```python
return product.price * 0.8
```
👉 20% discount.

---

## 7️⃣ Discount Engine (Core Calculator)

```python
class DiscountEngine:
```
This class manages all discount strategies.

**Constructor**
```python
def __init__(self, strategies: list[DiscountStrategy]):
    self.strategies = strategies
```
Receives multiple discount rules.

Example:
```code
[
  PercentageDiscount,
  FixedAmountDiscount,
  PremiumUserDiscount
]
```

**Calculate Best Price**
```python
def calculate_best_price(self, product, user_tier):
```

**Step-by-step Logic**
```python
prices = [product.price]
```
Start with original price.

**Loop Through Strategies**
```python
for strategy in self.strategies:
```
Check each discount.

**Apply If Valid**
```python
if strategy.is_applicable(product, user_tier):
```
Only valid discounts are used.

**Store Discounted Price**
```python
discounted = strategy.apply_discount(product)
prices.append(discounted)
```
Collect all possible prices.

**Return Best Price**
```python
return min(prices)
```
Selects the lowest price.
> ✅ Customer always gets the best deal.

---

## 8️⃣ Main Program Execution

```python
if __name__ == '__main__':
```
Ensures code runs only when executed directly.

**Create Product**
```python
product = Product('Wireless Mouse', 50.0)
```

**Define User Tier**
```python
user_tier = 'Premium'
```

**Register Discount Strategies**
```python
strategies = [
    PercentageDiscount(10),
    FixedAmountDiscount(5),
    PremiumUserDiscount()
]
```

**Run Engine**
```python
engine = DiscountEngine(strategies)
best_price = engine.calculate_best_price(product, user_tier)
```

**Display Result**

```python
print(f'Best price for {product.name} for {user_tier} user: ${best_price:.2f}')
```

Output Example

```python
Best price for Wireless Mouse for Premium user: $40.00
```
(Because premium discount = 20%)

---

## 🎯 Design Pattern Used: Strategy Pattern
Why Strategy Pattern?

Instead of:
❌ giant if-else statements

We use:
✅ interchangeable algorithms (discounts)

| Benefit      | Explanation                       |
| ------------ | --------------------------------- |
| Extensible   | Add new discounts easily          |
| Maintainable | No modification of existing logic |
| Reusable     | Strategies work independently     |
| Clean Code   | Separation of responsibilities    |

---

## 🧠 Key OOP Concepts Used

| Concept       | Where Used                     |
| ------------- | ------------------------------ |
| Encapsulation | Product class                  |
| Inheritance   | Discount strategies            |
| Polymorphism  | Different discount behaviors   |
| Abstraction   | DiscountStrategy class         |
| Composition   | DiscountEngine uses strategies |

---

## ✅ Final Workflow
```mermaid
Create Product
      ↓
Load Discount Strategies
      ↓
Check Applicability
      ↓
Apply Discounts
      ↓
Compare Prices
      ↓
Return Lowest Price
```

