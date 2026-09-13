# 📝 What Are Dictionaries, and How Do They Work?

In Python, **dictionaries** are built-in data structures that store collections of **key-value pairs**. They work like real dictionaries, where you look up a word to find its meaning. You use dictionaries when you need to associate values with unique keys. This is useful for **fast lookups** and representing **structured data**.

---

## Dictionary Syntax

```python
dictionary = {
    key1: value1,
    key2: value2
}
```

- Culy braces {} define a dictionary.
- Each key is associated with a value.
- Keys must be unique and immutable.
- Values can be any type and may be repeated.

Example:
```python
pizza = {
    'name': 'Margherita Pizza',
    'price': 8.9,
    'calories_per_slice': 250,
    'toppings': ['mozzarella', 'basil']
}
```

---

## Using the dict() Constructor

You can also create dictionaries using the dict() constructor with a list of tuples:

```python
pizza = dict([
    ('name', 'Margherita Pizza'),
    ('price', 8.9),
    ('calories_per_slice', 250),
    ('toppings', ['mozzarella', 'basil'])
])
```

---

Accessing Values

Use bracket notation to access a value by its key:
```python
pizza['name']  # 'Margherita Pizza'
```

---

Updating Values

Assign a new value to a key:
```python
pizza['name'] = 'Margherita'
print(pizza['name'])  # 'Margherita'
```
- If the key doesn't exist, a new key-value pair is created.
- Dictionaries preserve insertion order in Python 3.7+.

---

## Useful Dictionary Methods

### 1. .get()

Retrieves the value for a key. Returns a default if the key doesn't exist:
```python
pizza.get('toppings', [])  # ['mozzarella', 'basil']
```

### 2. .keys() and .values()

Return views of the dictionary's keys and values:
```python
pizza.keys()
# dict_keys(['name', 'price', 'calories_per_slice', 'toppings'])

pizza.values()
# dict_values(['Margherita Pizza', 8.9, 250, ['mozzarella', 'basil']])
```

---

### 3. .items()

Returns a view of key-value pairs:
```python
pizza.items()
# dict_items([('name', 'Margherita Pizza'), ('price', 8.9), ('calories_per_slice', 250), ('toppings', ['mozzarella', 'basil'])])
```

### 4. .clear()

Removes all key-value pairs:
```python
pizza.clear()
```

### 5. .pop()

Removes a key-value pair and returns its value:
```python
pizza.pop('price', 10)  # removes 'price', returns 10 if key not found
# pizza.pop('total_price')  # KeyError if key doesn't exist
```

### 6. .popitem()

Removes the last inserted item (Python 3.7+):
```python
pizza.popitem()
```

### 7. .update()

Updates the dictionary with another dictionary. Existing keys are overwritten; new keys are added:
```python
pizza.update({'price': 15, 'total_time': 25})
```

Result:
```text
{
    'name': 'Margherita Pizza', 
    'price': 15, 
    'calories_per_slice': 250, 
    'toppings': ['mozzarella', 'basil'], 
    'total_time': 25
}
```

---

# 🔁 What Are Some Common Techniques to Loop Over a Dictionary?

You can loop over a dictionary when you need to access and process its **key-value pairs**. This is useful for updating values or applying logic to them.

---

## Example Dictionary

```python
products = {
    'Laptop': 990,
    'Smartphone': 600,
    'Tablet': 250,
    'Headphones': 70,
}
```

---

## Looping Over Values

Use .values() to iterate over all values in the dictionary:
```python
for price in products.values():
    print(price)
```

Output:
```python
990
600
250
70
```

---

## Looping Over Keys

You can loop over keys using .keys() or directly over the dictionary:

```python
for product in products.keys():
    print(product)

# Or

for product in products:
    print(product)
```

Output:

```text
Laptop
Smartphone
Tablet
Headphones
```

---

## Looping Over Key-Value Pairs

Use .items() to loop over keys and values together:

```python
for product in products.items():
    print(product)
```

Output:

```python
('Laptop', 990)
('Smartphone', 600)
('Tablet', 250)
('Headphones', 70)
```

---

## Separating Keys and Values

You can unpack keys and values into separate variables:

```python
for product, price in products.items():
    print(product, price)
```

Output:

```output
Laptop 990
Smartphone 600
Tablet 250
Headphones 70
```

---

## Updating Values While Looping

Example: Apply a 20% discount to all products:

```python
for product, price in products.items():
    products[product] = round(price * 0.8)

print(products)
```

Result:

```python
{
    'Laptop': 792,
    'Smartphone': 480,
    'Tablet': 200,
    'Headphones': 56
}
```

---

## Using enumerate() with Dictionaries
`enumerate()` adds a counter to each iteration.

### Enumerate Keys
```python
for product in enumerate(products):
    print(product)
```

Output:
```text
(0, 'Laptop')
(1, 'Smartphone')
(2, 'Tablet')
(3, 'Headphones')
```

Separate Index and Key
```python
for index, product in enumerate(products):
    print(index, product)
```

---

### Enumerate Values
```python
for index, price in enumerate(products.values()):
    print(index, price)
```

Output:
```text
0 990
1 600
2 250
3 70
```

---

### Enumerate Key-Value Pairs

```python
for index, product in enumerate(products.items()):
    print(index, product)
```

Output:

```text
0 ('Laptop', 990)
1 ('Smartphone', 600)
2 ('Tablet', 250)
3 ('Headphones', 70)
```

---

### Start Enumeration from a Custom Number

```python
for index, product in enumerate(products.items(), 1):
    print(index, product)
```

for index, product in enumerate(products.items(), 1):
    print(index, product)

```text
1 ('Laptop', 990)
2 ('Smartphone', 600)
3 ('Tablet', 250)
4 ('Headphones', 70)
```

---

## ✅ Summary

Common techniques to loop over dictionaries include:
- `.keys()` → loop over keys
- `.values()` → loop over values
- `.items()` → loop over key-value pairs
- `enumerate()` → loop with a counter
