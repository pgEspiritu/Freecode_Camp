# What Are Methods and Attributes, and How Do They Work?

In the last lesson, you learned about classes and how they act as blueprints for creating objects.  

Here, we will dive deeper into **attributes** and **methods**. Let's start with attributes.

---

## Attributes

**Attributes** are variables that belong to an object, so they hold data. There are two kinds of attributes:

1. **Instance attributes** – Unique to each object created from a class. Usually set with the `__init__` method.  
2. **Class attributes** – Belong to the class itself and are shared by all instances of that class.

You access attributes using **dot notation**.

### Example: Instance vs Class Attributes

```python
class Dog:
    species = "French Bulldog"  # Class attribute

    def __init__(self, name):
        self.name = name  # Instance attribute

# Accessing class attribute directly
print(Dog.species)  # French Bulldog

# Creating objects
dog1 = Dog("Jack")
print(dog1.name)    # Jack
print(dog1.species) # French Bulldog

dog2 = Dog("Tom")
print(dog2.name)    # Tom
print(dog2.species) # French Bulldog
```

> Note: Class attributes can be accessed directly from the class itself.
> Instance attributes require creating an object first.

---

### Example: Cars

```python
class Car:
    def __init__(self, color, model):
        self.color = color
        self.model = model

car_1 = Car("red", "Toyota Corolla")
car_2 = Car("green", "Lamborghini Revuelto")

print(car_1.model)  # Toyota Corolla
print(car_2.model)  # Lamborghini Revuelto
print(car_1.color)  # red
print(car_2.color)  # green
```

---

## Methods

Methods are functions defined inside a class. They allow objects created from the class to perform actions, often using or modifying their own data.
You also access methods using dot notation.

### Example: Dog Class with bark Method

```python
class Dog:
    species = "French Bulldog"

    def __init__(self, name):
        self.name = name

    def bark(self):
        return f"{self.name} says woof woof!"

# Creating objects
jack = Dog("Jack")
jill = Dog("Jill")

print(jack.bark())  # Jack says woof woof!
print(jill.bark())  # Jill says woof woof!
```

### Example: Car Class with describe Method

```python
class Car:
    def __init__(self, color, model):
        self.color = color  # Instance attribute
        self.model = model  # Instance attribute

    def describe(self):
        return f"This car is a {self.color} {self.model}"

car_1 = Car("red", "Toyota Corolla")
car_2 = Car("green", "Lamborghini Revuelto")

print(car_1.describe())  # This car is a red Toyota Corolla
print(car_2.describe())  # This car is a green Lamborghini Revuelto
```

> In summary, attributes store data for objects, while methods allow objects to perform actions using that data.
