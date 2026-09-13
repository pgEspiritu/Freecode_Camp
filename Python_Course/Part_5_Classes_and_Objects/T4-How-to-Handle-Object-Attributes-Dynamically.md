# How to Handle Object Attributes Dynamically?

In a previous lesson, you learned that **attributes** are variables that belong to an object. They hold data that describes the state or behavior of that object.

For example, a car has a brand and a model:

```python
class Car: 
    def __init__(self, brand, model): 
        self.brand = brand 
        self.model = model 

my_car = Car('Lamborghini', 'Gallardo') 
print(my_car.brand)  # Lamborghini 
print(my_car.model)  # Gallardo 
```

But sometimes, you don’t know which attributes you’ll need until the program is already running. Maybe the attribute names come from:
- User input
- A configuration file
- An environment variable file
- External data
This is where dynamic attribute handling becomes useful.

Python provides four built-in functions to work with attributes dynamically:
- getattr() – Get an attribute
- setattr() – Set or create an attribute
- hasattr() – Check if an attribute exists
- delattr() – Delete an attribute

---

## 1️⃣ getattr() – Access Attributes Dynamically

`getattr()` lets you access an attribute when its name is stored in a variable.

Syntax

```python
getattr(object, attribute_name, default_value)
```
- object → the object you’re inspecting
- attribute_name → string name of the attribute
- default_value → optional value if attribute doesn’t exist

### Example
```python
class Person: 
    def __init__(self, name, age): 
        self.name = name 
        self.age = age 

person = Person('John Doe', 30) 

print(getattr(person, 'name'))  # John Doe 
print(getattr(person, 'age'))   # 30 
print(getattr(person, 'city', 'Milano'))  # Milano
```
Since `city` does not exist, it returns the default value "`Milano"`.

---

## Using getattr() With User Input

```python
class Person: 
    def __init__(self, name, age): 
        self.name = name 
        self.age = age 

person = Person('John Doe', 30)

attr_name = input('Enter the attribute you want to see: ')
print(getattr(person, attr_name, 'Attribute not found'))
```
This allows your program to respond dynamically to runtime input.

---

## 2️⃣ Using dir() to Inspect Attributes

If you want to see all attributes of an object, use dir():

```python
class Person: 
    def __init__(self, name, age): 
        self.name = name 
        self.age = age 

person = Person('John Doe', 30)

for attr in dir(person):
    if not attr.startswith('__') and not callable(getattr(person, attr)):
        value = getattr(person, attr)
        print(f'{attr}: {value}')
```

### Output

```python
age: 30
name: John Doe
```

This filters out special (dunder) methods and regular methods.

---

## 3️⃣ `setattr()` – Create or Modify Attributes Dynamically

`setattr()` allows you to add or update attributes dynamically.

### Syntax

```python
setattr(object, attribute_name, value)
```

### Example

```python
class Configuration:
    pass

settings_data = {
    'server_url': 'https://api.example.com',
    'timeout_sec': 30,
    'max_retries': 5
}

config_obj = Configuration()

for attr_name, attr_value in settings_data.items():
    setattr(config_obj, attr_name, attr_value)

print(config_obj.server_url)  # https://api.example.com
print(config_obj.timeout_sec) # 30
```
This is very useful when loading configuration values at runtime.

---

## 4️⃣ hasattr() – Check if Attribute Exists

Before accessing or deleting an attribute, it’s good practice to check if it exists.

Syntax

```python
hasattr(object, attribute_name)
```

Example

```python
class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price

product_a = Product('T-Shirt', 25)

required_attributes = ['name', 'price', 'inventory_id']

for attr in required_attributes:
    if not hasattr(product_a, attr):
        print(f"ERROR: Product is missing the required attribute: '{attr}'")
    else:
        print(f'{attr}: {getattr(product_a, attr)}')
```

### Output

```vbnet
name: T-Shirt
price: 25
ERROR: Product is missing the required attribute: 'inventory_id'
```

---

## 5️⃣ delattr() – Remove Attributes Dynamically

`delattr()` removes an attribute from an object.

### Syntax

```python
delattr(object, attribute_name)
```

### Example

```python
class UserSession:
    def __init__(self, user_id, token):
        self.user_id = user_id
        self.auth_token = token  # sensitive
        self.temp_counter = 0    # temporary

session = UserSession(101, 'a1b2c3d4e5')

attributes_to_clean = ['auth_token', 'temp_counter']

for attr in attributes_to_clean:
    if hasattr(session, attr):
        delattr(session, attr)
        print(f'Removed attribute: {attr}')

print('\nFinal attributes remaining:')

for attr in dir(session):
    if not attr.startswith('__') and not callable(getattr(session, attr)):
        print(f' - {attr}: {getattr(session, attr)}')
```

### Output

```yaml
Removed attribute: auth_token
Removed attribute: temp_counter

Final attributes remaining:
 - user_id: 101
```

---

## ✅ Summary

Dynamic attribute handling allows your program to:

- Access attributes using variables (getattr)
- Create or update attributes at runtime (setattr)
- Check if attributes exist (hasattr)
- Remove attributes dynamically (delattr)
- Inspect all attributes (dir)

This makes your code flexible, adaptable, and powerful, especially when working with dynamic data like user input, configuration files, APIs, or external systems.
