# 🔐 What are Getters and Setters?

**Getters** and **setters** are methods that let you control how the attributes of a class are **accessed** and **modified**.

- **Getters** → retrieve a value  
- **Setters** → set or update a value  

These actions are handled through **properties**, which connect getters and setters and manage access to data.

---

## 🧩 What Are Properties?

Properties act like **attributes** but behave like **methods under the hood**.

- You access them using **dot notation**
- They can run **extra logic** when values are:
  - Retrieved
  - Set
  - Deleted

👉 Think of properties as *methods that look like attributes*.

---

## 🤔 Why Use Properties Instead of Methods?

It’s mostly about **readability and convention**:

- Methods require parentheses: `obj.get_value()`
- Properties look cleaner: `obj.value`

This keeps your code simple while still allowing validation, calculations, or transformations behind the scenes.

---

## 🧱 Creating a Getter with `@property`

To create a property, define a method and place the `@property` decorator above it.

```python
class Circle:
    def __init__(self, radius):
        self._radius = radius

    @property
    def radius(self):  # Getter to retrieve radius
        return self._radius
  
    @property
    def area(self):  # Getter to calculate area
        return 3.14 * (self._radius ** 2)

my_circle = Circle(3)

print(my_circle.radius)  # 3
print(my_circle.area)    # 28.26
```

📌 Notice the use of `_radius`.
A single underscore is a Python convention indicating that the attribute is meant for internal use.

---

## ✏️ Creating a Setter

To create a setter, define another method with the same name and use the `@<property_name>.setter` decorator.
```python
class Circle:
    def __init__(self, radius):
        self.radius = radius  # Calls the setter

    @property
    def radius(self):  # Getter
        return self._radius

    @radius.setter
    def radius(self, value):  # Setter
        if value <= 0:
            raise ValueError('Radius must be positive')
        self._radius = value
```

### ✅ Using the Setter

```python
my_circle = Circle(3)
print('Initial radius:', my_circle.radius)  # 3

my_circle.radius = 8
print('After modifying the radius:', my_circle.radius)  # 8
```
🛡️ The setter not only assigns a value, but also validates it.

---

### ⚙️ How Python Uses Getters and Setters

Once defined, Python automatically calls them:
```python
my_circle.radius        # Calls the getter
my_circle.radius = 4    # Calls the setter
```

### ⚠️ Important Setter Rule

Inside a setter, never assign to the property itself:

❌ Wrong:
```python
self.radius = value
```

✔ Correct:
```python
self._radius = value
```
Using `self.radius = value` inside the setter would call the setter again, causing infinite recursion and a `RecursionError`.

---

## 🗑️ Creating a Deleter

A deleter lets you define what happens when an attribute is deleted using del.

Use the `@<property_name>.deleter` decorator:
```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    # Getter
    @property
    def radius(self):
        return self._radius

    # Setter
    @radius.setter
    def radius(self, value):
        if value <= 0:
            raise ValueError("Radius must be positive")
        self._radius = value

    # Deleter
    @radius.deleter
    def radius(self):
        print("Deleting radius...")
        del self._radius
```

### 🧪 Using the Deleter

```python
my_circle = Circle(33)
print("Initial radius:", my_circle.radius)  # 33

del my_circle.radius  # Deleting radius...
print("Radius deleted!")

try:
    print(my_circle.radius)
except AttributeError as e:
    print("Error:", e)
```

---

## 🧾 Key Takeaways

- ✅ Getters retrieve or compute values
- ✅ Setters validate and safely modify values
- ✅ Properties connect getters and setters using dot notation
- ✅ Deleters control what happens when an attribute is deleted
✨ Properties allow you to write clean, readable code while still enforcing rules and encapsulation behind the scenes.
