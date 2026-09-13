# Build a Budget App

In this lab, you will build a simple budget app that tracks spending in different categories and can show the relative spending percentage on a graph.

---

## Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## User Stories

### Category Class

You should have a `Category` class that accepts a `name` as an argument.

- The `Category` class should have an instance attribute `ledger` that is a list containing the list of transactions.

---

### Methods

The `Category` class should include the following methods:

1. **`deposit(amount, description="")`**  
   - Accepts an amount and an optional description (defaults to an empty string).  
   - Appends an object to the ledger in the form:
     ```python
     {'amount': amount, 'description': description}
     ```

2. **`withdraw(amount, description="")`**  
   - Accepts an amount and an optional description (defaults to an empty string).  
   - Stores the amount as a negative number in the ledger.  
   - Returns `True` if the withdrawal succeeds and `False` otherwise.

3. **`get_balance()`**  
   - Returns the current category balance based on the ledger.

4. **`transfer(amount, category)`**  
   - Accepts an amount and another `Category` instance.  
   - Withdraws the amount from the source category with description:
     ```
     Transfer to [Destination]
     ```
   - Deposits the amount into the other category with description:
     ```
     Transfer from [Source]
     ```
   - Returns `True` if the transfer is successful and `False` otherwise.

5. **`check_funds(amount)`**  
   - Accepts an amount and returns `False` if it exceeds the balance or `True` otherwise.  
   - Must be used by both the `withdraw` and `transfer` methods.

---

### Printing a Category Object

When a `Category` object is printed:

- Display a **title line** of 30 characters with the category name centered between `*` characters.  
- List each ledger entry with:
  - Up to 23 characters of the description, left-aligned.  
  - Amount right-aligned (two decimal places, maximum 7 characters).  
- Show a final line:
```python
Total: [balance]
```
where `[balance]` is the category’s total balance.

#### Example Usage

```python
food = Category('Food')
food.deposit(1000, 'deposit')
food.withdraw(10.15, 'groceries')
food.withdraw(15.89, 'restaurant and more food for dessert')
clothing = Category('Clothing')
food.transfer(50, clothing)
print(food)
```

#### Example Output

```markdown
*************Food*************
deposit               1000.00
groceries              -10.15
restaurant and more fo -15.89
Transfer to Clothing   -50.00
Total: 923.96
```

---

## Spending Chart Function

You should have a function outside the Category class named:
```python
create_spend_chart(categories)
```
- Accepts a list of Category objects.
- Returns a bar-chart string showing the percentage spent by category.

### Requirements

1. Start with the title:
   ```charp
   Percentage spent by category
   ```
2. Calculate percentages from withdrawals only, not deposits.
  - The percentage is the amount spent for each category relative to the total spent for all categories.
  - Round down to the nearest 10.
3. Label the y-axis from 100 down to 0 in steps of 10.
4. Use o characters for the bars.
5. Include a horizontal line two spaces past the last bar.
6. Write category names vertically below the bar.
7. The function will be tested with up to four categories.
8. Match the spacing of the example output exactly.

### Example Output

```markdown
Percentage spent by category
100|          
 90|          
 80|          
 70|          
 60| o        
 50| o        
 40| o        
 30| o        
 20| o  o     
 10| o  o  o  
  0| o  o  o  
    ----------
     F  C  A  
     o  l  u  
     o  o  t  
     d  t  o  
        h     
        i     
        n     
        g     
```

---

## CODE

```python
# -----------------------------
# Category Class for Budget App
# -----------------------------
class Category:
    def __init__(self, name):
        """
        Initialize a Category instance.

        Args:
            name (str): The name of the category.
        """
        self.name = name
        self.ledger = []  # List to store all transactions as dictionaries

    # -------------------------
    # Deposit and Withdrawal
    # -------------------------
    def deposit(self, amount, description=""):
        """
        Add a deposit to the ledger.

        Args:
            amount (float): Amount to deposit.
            description (str, optional): Description of the transaction. Defaults to "".
        """
        self.ledger.append({'amount': amount, 'description': description})

    def withdraw(self, amount, description=""):
        """
        Attempt to withdraw an amount from the ledger.

        Args:
            amount (float): Amount to withdraw.
            description (str, optional): Description of the transaction. Defaults to "".

        Returns:
            bool: True if withdrawal succeeds, False if insufficient funds.
        """
        if self.check_funds(amount):
            self.ledger.append({'amount': -amount, 'description': description})
            return True
        return False

    # -------------------------
    # Transfers
    # -------------------------
    def transfer(self, amount, category):
        """
        Transfer amount from this category to another category.

        Args:
            amount (float): Amount to transfer.
            category (Category): Destination category object.

        Returns:
            bool: True if transfer succeeds, False if insufficient funds.
        """
        if self.check_funds(amount):
            self.withdraw(amount, f'Transfer to {category.name}')
            category.deposit(amount, f'Transfer from {self.name}')
            return True
        return False

    # -------------------------
    # Balance & Funds Checking
    # -------------------------
    def get_balance(self):
        """
        Calculate the current balance of the category.

        Returns:
            float: Current balance.
        """
        balance = 0
        for item in self.ledger:
            balance += item['amount']
        return balance

    def check_funds(self, amount):
        """
        Check if the category has enough funds for a transaction.

        Args:
            amount (float): Amount to check.

        Returns:
            bool: True if sufficient funds, False otherwise.
        """
        return self.get_balance() >= amount

    # -------------------------
    # String Representation
    # -------------------------
    def __str__(self):
        """
        Return a formatted string of the category ledger.

        Format:
        - Title: 30 characters wide, centered with '*'
        - Ledger entries: description left-aligned (23 chars max), amount right-aligned (7 chars, 2 decimals)
        - Total line: shows total balance
        """
        title = f'{self.name:*^30}\n'
        items = ""

        for entry in self.ledger:
            description = entry["description"][:23]          # truncate description
            amount = f'{entry["amount"]:>7.2f}'             # format amount
            items += f'{description:<23}{amount}\n'

        last_line = f'Total: {self.get_balance():.2f}'
        return title + items + last_line


# -----------------------------
# Function: Create Spend Chart
# -----------------------------
def create_spend_chart(categories):
    """
    Create a bar chart showing percentage spent by category.

    Args:
        categories (list): List of Category objects.

    Returns:
        str: Formatted string representing the percentage spent chart.
    """
    # Chart title
    title = 'Percentage spent by category\n'

    # Calculate total spent per category (only withdrawals)
    spent = []
    for cat in categories:
        total = 0
        for item in cat.ledger:
            if item['amount'] < 0: 
                total += -item['amount']
        spent.append(total)

    total_spent = sum(spent)
    # Calculate percentage spent per category, rounded down to nearest 10
    percentages = [int((s / total_spent) * 100) // 10 * 10 for s in spent]

    # Build chart bars
    chart = ""
    for level in range(100, -1, -10):
        line = f"{level:>3}|"   # Y-axis label
        for p in percentages:
            line += " o " if p >= level else "   "  # Add 'o' if category reaches this level
        line += " \n"
        chart += line

    # Add horizontal line under chart
    chart += "    " + "-" * (len(categories) * 3 + 1) + "\n"

    # Add category names vertically
    max_len = max(len(cat.name) for cat in categories)
    for i in range(max_len):
        line = "     "  # initial spacing for y-axis
        for cat in categories:
            if i < len(cat.name):
                line += cat.name[i] + "  "
            else:
                line += "   "
        if i != max_len - 1:
            line += "\n"
        chart += line

    return title + chart
```
