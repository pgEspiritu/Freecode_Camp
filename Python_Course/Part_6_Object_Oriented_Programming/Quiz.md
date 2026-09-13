# 🧠 Object Oriented Programming Quiz

> ✅ To pass the quiz, you must correctly answer **at least 18 of the 20 questions**.

---

## 1. What serves as the blueprint for creating objects?

- Functions  
- Loops  
- ✅ Classes  
- Variables  

---

## 2. Which module does Python use to implement abstract classes?

- ✅ abc  
- Random  
- Time  
- xyz  

---

## 3. What defines the data and behaviors of an object?

- Seeders and databases.  
- Variables and loops.  
- Functions and classes.  
- ✅ Attributes and methods.  

---

## 4. What is single inheritance?

- ✅ A child class inheriting attributes and methods from a single class.  
- A child class inheriting attributes and methods from a single function.  
- A child class inheriting attributes and methods from multiple classes.  
- A child class inheriting attributes and methods from multiple functions.  

---

## 5. Which of the following is NOT one of the key principles of object-oriented programming?

- Inheritance  
- Encapsulation  
- Abstraction  
- ✅ Don't repeat yourself (DRY)  

---

## 6. What is the difference between prefixing attributes and methods with a double underscore and single underscore?

- Single underscore hides the attribute completely, double underscore makes it readable only inside methods.  
- Single underscore makes them public, double underscore makes them static.  
- ✅ Single underscore is just a convention for internal use, double underscore triggers name mangling to prevent accidental attribute and method overriding.  
- Single underscore means private, double underscore means protected.  

---

## 7. Which OOP concept lets you hide complex implementation details and only shows the essential features of an object or system?

- Encapsulation  
- Inheritance  
- ✅ Abstraction  
- Polymorphism  

---

## 8. Which decorator do you use to create a setter?

- @\<method_name>.creator  
- ✅ @\<property_name>.setter  
- @\<property_name>.creator  
- @\<method_name>.creater  

---

## 9. Which OOP concept lets you hide the internal state of the object behind a set of public methods and attributes that act like doors?

- ✅ Encapsulation  
- Polymorphism  
- Single inheritance  
- Abstraction  

---

## 10. What is a getter?

- ✅ A method that retrieves or returns the value of an attribute.  
- A method that deletes an attribute from an object.  
- A method that updates or changes the value of an attribute.  
- A method that creates a new attribute in an object.  

---

## 11. What is a setter?

- A method that retrieves the value of an attribute.  
- ✅ A method that sets or updates the value of an attribute.  
- A method that deletes the value of an attribute.  
- A method that deletes an attribute from an object.  

---

## 12. What lets you delete a value you set and get with a setter and getter?

- Eraser  
- ✅ Deleter  
- Remover  
- Delayer  

---

## 13. What promotes code reuse, provides clear hierarchies, and allows customization of behavior without rewriting everything?

- ✅ Inheritance  
- WET  
- Abstraction  
- DRY  

---

## 14. Which of these is the correct syntax of inheritance?

a.
```python
class Parent:
    pass
class Child(Inheriter):
    pass
```
b. ✅
```python
class Parent:
   pass
class Child(Parent):
   pass
```
c.
```python
class Parent:
    pass
class Child(InheritParent):
    pass
```
d.
```python
class Child:
   pass
class Parent(Parent):
   pass
```

---

## 15. What connects setters and getters?

- Classes
- Functions
- ✅ Properties
- Methods

---

## 16. What is the process by which Python internally renames an attribute prefixed with a double underscore by adding an underscore and the class name as a prefix?

- Polymorphism
- Abstraction
- ✅ Name Mangling
- Name Mingling

---

## 17. Which function lets you invoke a method from a parent inside a child class?

- constructor()
- init()
- ✅ super()
- property()

---

## 18. Which of the following statements best describes polymorphism in OOP?

- It allows creating objects with the class keyword.
- It allows a class to have multiple constructors with different attributes and methods.
- It allows a class to inherit attributes and methods from another class.
- ✅ It allows different classes to use the same method name while performing different actions when called.

---

## 19. Why does Python mangle the name of an attribute prefixed with double underscores?

- To make the attribute completely private and inaccessible from outside the class.
- To automatically convert attributes into read-only properties.
- To improve performance by storing attributes more efficiently.
- ✅ To prevent accidental attribute and method overriding in subclasses when using inheritance.

---

## 20. Why are properties used instead of methods for getters and setters?

- To automatically log every value change.
- To make code longer and more explicit.
- ✅ To allow direct attribute-like access with dot notation for better readability.
- To prevent access to the value entirely.
