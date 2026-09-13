# How Do Classes Work and How Do They Differ From Objects?

In Python, classes and objects work hand in hand to organize and manage data. You build a class to define shared behavior, then create objects that use those behaviors.

In other words, a **class** is like a blueprint or template you use to create **objects** with.

Let's look at what classes are, and how to use them to create objects.

---

## Creating a Class

To create a class, you use the `class` keyword followed by the name of the class and a colon. Then within the class, you can add an initializer, along with any attributes and methods.

- **Attributes** are like variables within a class and are used to store data.
- **Methods** are functions defined within a class and are the actions objects created with a class can perform.

### Basic Class Syntax

```python
class ClassName:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def sample_method(self):               
        print(self.name.upper())
```

- `class ClassName` uses the `class` keyword followed by the class name.
It is common in Python to use PascalCase when naming classes.
- `def __init__(self, name, age)` is a special method automatically called when a new object is created.
It initializes the attributes of the objects that will be created with the class.
- The first parameter of `__init__` is always a reference to the specific object being created or used.
By convention, this parameter is named self.
- `self.name = name` and self.age = age are the attributes the objects will have.
- `def sample_method(self)` is a method each object created can call.
- `print(self.name.upper())` is what the sample_method does—in this case, it prints the name in uppercase.

---

## Example: A Dog Class

If that all sounds like a lot, don’t worry. Let’s look at a similar example of a Dog class and how you can create objects from it.

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        print(f"{self.name.upper()} says woof woof!")
```

---

## Creating Objects From a Class

Here’s the basic syntax for creating objects from a class:

```python
object_1 = ClassName(attribute_1, attribute_2)
object_2 = ClassName(attribute_1, attribute_2)
```

You can also call any of the methods defined in the class from each object:

```python
object_1.method_name()
object_2.method_name()
```

---

## Creating and Using Dog Objects

Now let’s create two dogs by using the Dog class as the blueprint:

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        print(f"{self.name.upper()} says woof woof! I'm {self.age} years old!")

dog_1 = Dog("Jack", 3)
dog_2 = Dog("Thatcher", 5)

# Call the bark method
dog_1.bark()  # JACK says woof woof! I'm 3 years old!
dog_2.bark()  # THATCHER says woof woof! I'm 5 years old!
```

As you can see, we create two dog objects using the Dog class. When initializing dog_1, the string "Jack" and the number 3 are passed, which sets the name and age attributes for that instance.
dog_2 is initialized with the string "Thatcher" and number 5 as its name and age, respectively.

When you call the .bark() method on dog_1 and dog_2, each object uses its own unique data.

---

## Summary: Class vs Object
- A class is the template or blueprint.
- An object is what is created using that template.
- A class defines what data and behavior the object should have.
- An object holds the actual data and uses that behavior.
- You write a class once and can create many objects from it, each with different data.

