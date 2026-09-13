# 🧠 Python Classes & Objects — Quiz

---

## 1. Which of the following is the correct way to define a class?

- `def className(class):`
- `class className:` ✅
- `self className:`
- `class className`

---

## 2. What is the purpose of the special method `__init__`?

- It initializes objects' attributes upon instantiation. ✅
- It sets a shortcut to create an instance of a class.
- It prevents an object from having duplicate attributes.
- It sets the value of `self` to the current object.

---

## 3. What is the difference between an instance attribute and a class attribute?

- Instance attributes define methods that can be accessed from an object; class attributes define methods that can be accessed from a class.
- Instance attributes belong to a specific object; class attributes belong to a class. ✅
- Instance attributes are set within the `__init__` method; class attributes are set within the `__class__` method.
- Instance attributes can be directly accessed from the class; class attributes can be only accessed from an actual instance of the class.

---

## 4. Which of the following is the correct way to call the `spam` method from the `menu` object?

- `spam.menu()`
- `menu.spam()` ✅
- `spam.menu`
- `menu[spam]`

---

## 5. Which of the following special methods is called under the hood when an object is printed to the console?

- `__str__` ✅
- `__string__`
- `__log__`
- `__print__`

---

## 6. What is the result of the following code?

```python
class Menu:
    dish_of_the_day = "spam"

print(Menu.dish_of_the_day)
```

- spam ✅
- SyntaxError
- AttributeError
- None

---

## 7. What does the self parameter refer to inside a method?

- It's a reference to the class being used.
- It's a reference to the object initializer.
- It's a reference to the instance of the class calling the method. ✅
- It's a reference to the module where the class is defined.

---

## 8. Which of the following correctly creates an instance of a class Person?

- `Person.new()`
- `new Person`
- `Person()` ✅
- `new Person()`

---

## 9. What will be the result of the following code?

```python
class Dog:
    def __init__(name, age):
        self.name = name
        self.age = age

dog = Dog("Pinky", 3)
print(dog.name)
```

- `TypeError` ✅
- `3`
- `AttributeError`
- `Pinky`

---

## 10. Which of the following is the correct way to access the name attribute of the dog object?

- `dog.name` ✅
- `dog().name`
- `dog.name()`
- `dog.get('name')`
