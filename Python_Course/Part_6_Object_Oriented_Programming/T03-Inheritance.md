# 🧬 What Is Inheritance and How Does It Promote Code Reuse?

Inheritance is the next key concept of **object-oriented programming (OOP)** we'll cover.

This concept allows you to write **reusable, organized, and extensible code** by creating relationships between classes.

---

## 🔁 Understanding Inheritance

With **inheritance**, a **subclass (child class)** can use the **attributes and methods** of a **base class (parent class)**.

This allows you to:

- Reuse existing code
- Create clear class hierarchies
- Customize behavior without rewriting everything
- Extend or override methods when needed

---

## 🧱 Basic Inheritance Syntax

```python
class Parent:
    # Parent attributes and methods

class Child(Parent):
    # Child inherits, extends, and/or overrides where necessary
```

To allow the `Child` class to inherit from Parent, you pass the parent class inside the parentheses.

This is called single inheritance, since the child class inherits from one parent class.

---

### 🐶 Example: Single Inheritance

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def sound(self):
        return f'{self.name} makes a sound'

class Dog(Animal):
    bark = 'woof! woof!! woof!!!'

jack = Dog('Jack')
print(jack.sound())  # Jack makes a sound
print(jack.bark)     # woof! woof!! woof!!!
```

#### ✅ What’s Happening Here?

- `Dog` inherits from `Animal`
- `Dog` can access:
  - the `name` attribute
  - the `sound()` method
This demonstrates code reuse through inheritance

---

## 🔄 Method Overriding

A child class can override a method from its parent class to provide a different implementation.

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def sound(self):
        return f'{self.name} makes a sound.'

class Dog(Animal):
    bark = 'woof! woof!! woof!!!'

    # Override sound() to use bark class variable
    def sound(self):
        return f'{self.name} barks {self.bark}'

jack = Dog('Jack')
print(jack.sound())  # Jack barks woof! woof!! woof!!!
```

🔍 Key Idea
- The `Dog` class replaces the parent’s `sound()` method
- The parent version is no longer used for `Dog` objects

---

## ➕ Extending a Parent Method with super()

If you want to keep the parent’s behavior and add new functionality, use the `super()` function.

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def sound(self):
        return f'{self.name} makes a sound'

class Dog(Animal):
    bark = 'woof! woof!! woof!!!'

    # Call Animal.sound(), then append bark
    def sound(self):
        base = super().sound()
        return f'{base}, then {self.name} barks {self.bark}'

jack = Dog('Jack')
print(jack.sound())
# Jack makes a sound, then Jack barks woof! woof!! woof!!!
```

🧠 Explanation
- `super().sound() `calls the parent’s sound() method
- The child class extends the behavior instead of replacing it

---

## 🧬 Multiple Inheritance

Multiple inheritance allows a class to inherit from more than one parent class.

Basic Syntax
```python
class Parent:
    # Attributes and methods for Parent

class Child:
    # Attributes and methods for Child

class GrandChild(Parent, Child):
    # Inherits from both Parent and Child
```

### 🐸 Example: Multiple Inheritance

```python
class Walker:
    def walk(self):
        return 'I can walk on land'

class Swimmer:
    def swim(self):
        return 'I can swim in water'

# Amphibian inherits from both Walker and Swimmer
class Amphibian(Walker, Swimmer):
    def __init__(self, name):
        self.name = name

    def introduce(self):
        return f"I'm {self.name} the frog. {self.walk()} and {self.swim()}."

frog = Amphibian('Freddy')
print(frog.introduce())
```

🖨 Output
```text
I'm Freddy the frog. I can walk on land and I can swim in water.
```

---

### ✅ Key Takeaways

- Inheritance promotes code reuse and clean design
- Single inheritance → one parent class
- Multiple inheritance → more than one parent class
- Overriding replaces parent behavior
- Extending with super() keeps parent behavior and adds new functionality
