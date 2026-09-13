# 🔁 What Is Polymorphism and How Does It Promote Code Reuse?

Polymorphism is another core concept of **object-oriented programming (OOP)**.

With polymorphism, you can interact with **many objects through a single interface**, even though those objects may behave differently.

---

## 🧠 Understanding Polymorphism

**Polymorphism** allows methods in different classes to share the **same name** but perform **different tasks**.

You can call the same method on different objects, and **each object responds in its own way**.

This makes your code:
- More flexible
- Easier to extend
- Less repetitive
- Easier to maintain

---

## 🧱 Basic Idea of Polymorphism

```python
class A:
    def action(self): ...

class B:
    def action(self): ...

class C:
    def action(self): ...

obj.method()  # Works for A, B, or C
```

As long as each class defines the same method name `(action())`, the caller does not need to know the object’s exact type.

---

### 🐾 Example: Polymorphism with Animal Sounds

```python
class Cat:
    def speak(self):
        return "A cat meow"

class Bird:
    def speak(self):
        return "A bird tweet"
  
class Monkey:
    def speak(self):
        return "A monkey ooh ooh aah aah ooh ooh aah aah"

def animal_sound(animal):
    print(animal.speak())

animal_sound(Cat())
animal_sound(Bird())
animal_sound(Monkey())
```

#### ✅ Explanation
- animal_sound() accepts any object that has a speak() method
- Each class implements speak() differently
- The same function call produces different outputs
➡️ This is polymorphism in action

---

## 🌐 Polymorphism with Objects and Attributes

```python
class Twitter:
    def __init__(self, content):
        self.content = content

    def post(self):
        return f"🐦 Tweet: '{self.content}' (280 chars max)"

class Instagram:
    def __init__(self, content):
        self.content = content

    def post(self):
        return f"📸 Instagram Post: '{self.content}' + ✨ filters"

class LinkedIn:
    def __init__(self, content):
        self.content = content

    def post(self):
        return f"💼 LinkedIn Article: '{self.content}' (Professional Mode)"

def start(social_media):
    print(social_media.post())
```

### ▶️ Usage Example

```python
tweet = Twitter('Just learned Python polymorphism!')
photo = Instagram('Sunset vibes 🌅')
article = LinkedIn('Why OOP matters in 2024')

start(tweet)
start(photo)
start(article)
```

🖨 Output

```python
🐦 Tweet: 'Just learned Python polymorphism!' (280 chars max)
📸 Instagram Post: 'Sunset vibes 🌅' + ✨ filters
💼 LinkedIn Article: 'Why OOP matters in 2024' (Professional Mode)
```

🔍 Key Idea
- One function (start)
- One method name (post)
- Multiple behaviors depending on the object

---

## 🧬 Inheritance-Based Polymorphism

In inheritance-based polymorphism, a parent class defines a method, and child classes override it.
The same method call behaves differently depending on the subclass.

### 🐶 Example: Inheritance-Based Polymorphism

```python
class Animal:
    def speak(self):
        return 'Some generic sound'

class Cat(Animal):
    def speak(self):
        return 'A cat meow'

class Dog(Animal):
    def speak(self):
        return 'A dog barks woof woof'

class Monkey(Animal):
    def speak(self):
        return 'A monkey ooh ooh aah aah ooh ooh aah aah'
```

▶️ Method Calls

```python
print(Cat().speak())
print(Dog().speak())
print(Monkey().speak())
print(Animal().speak())
```

🔁 Polymorphism in a Loop

```python
animals = [Cat(), Dog(), Monkey()]

for animal in animals:
    print(animal.speak())
```

🖨 Output

```python
A cat meow
A dog barks woof woof
A monkey ooh ooh aah aah ooh ooh aah aah
```

---

## ✅ Key Takeaways

- Polymorphism allows one interface, many behaviors
- Methods share the same name but act differently
- Works with:
  - Unrelated classes (duck typing)
  - Inheritance and method overriding
- Enables flexible, reusable, and scalable code
