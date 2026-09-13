# 🧬 What is Name Mangling and How Does it Work?

In a previous lesson, you learned about prefixing attributes with a **single underscore (`_`)** and a **double underscore (`__`)**. While they may look similar, they behave very differently in Python.

---

## 🔹 Single Underscore vs Double Underscore

### ✅ Single Underscore (`_attribute`)
- A **naming convention**
- Means the attribute is for **internal use**
- Still accessible from outside the class
- Relies on developer discipline

### 🔒 Double Underscore (`__attribute`)
- Triggers **name mangling**
- Prevents direct access from outside the class
- Helps avoid accidental overrides, especially in inheritance

---

## 🧪 Example: Single vs Double Underscore

```python
class Example:
    def __init__(self):
        self._internal = 'I can be accessed from outside the class, but should not'
        self.__private = 'You cannot access me directly from outside the class'

obj = Example()

print(obj._internal)   # I can be accessed from outside the class, but should not
print(obj.__private)   # AttributeError
```
➡️ _internal works (by convention only)
➡️ __private raises an error

---

## 🔧 What Is Name Mangling?

When you prefix an attribute with a double underscore, Python internally renames it using this pattern:
```python
__attribute  →  _ClassName__attribute
```
This process is called name mangling.

---

## 🔍 Seeing Name Mangling in Action

You can inspect the renamed attributes using the `__dict__` attribute:
```python
class Example:
    def __init__(self, internal, private):
        self._internal = internal
        self.__private = private

example1 = Example(
    'I can be accessed from outside the class, but should not',
    'I cannot be accessed directly from outside the class'
)

print(example1.__dict__)
```

🖨️ Output
```python
{
  '_internal': 'I can be accessed from outside the class, but should not',
  '_Example__private': 'I cannot be accessed directly from outside the class'
}
```
📌 Notice how __private became _Example__private.

---

## 🚪 Accessing a Mangled Attribute (Not Recommended)

Even though it’s hidden, you can still access it if you know the mangled name:
```python
class Example:
    def __init__(self, internal, private):
        self._internal = internal
        self.__private = private

example1 = Example(
    'I can be accessed from outside the class, but should not',
    'I cannot be accessed directly from outside the class'
)

example2 = Example(
    'I should not be accessed from outside the class',
    'But I can be accessed from outside the class with name mangling'
)

print(example1._Example__private)
print(example2._Example__private)
```
⚠️ This works, but should be avoided—it defeats encapsulation.

---

### 🧠 Why Does Python Use Name Mangling?

The main purpose of name mangling is to prevent accidental attribute overriding when using inheritance.

---

## 🧬 Name Mangling with Inheritance
✅ With Double Underscore (Safe)

```python
class Parent:
    def __init__(self):
        self.__data = 'Parent data'

class Child(Parent):
    def __init__(self):
        super().__init__()
        self.__data = 'Child data'

c = Child()
print(c.__dict__)
```

🖨️ Output

```python
{
  '_Parent__data': 'Parent data',
  '_Child__data': 'Child data'
}
```

✔️ Both classes keep their own versions of `__data`
✔️ No accidental overwrite

---

## ❌ Without Name Mangling (Problematic)

```python
class Parent:
    def __init__(self):
        self.data = 'Parent data'

class Child(Parent):
    def __init__(self):
        super().__init__()
        self.data = 'Child data'

c = Child()
print(c.__dict__)
```

🖨️ Output
```output
{'data': 'Child data'}
```
❌ Child overwrites Parent’s data
❌ Bug-prone in large codebases

---

## 🧾 When to Use _ vs __
Use single underscore (_) when:
- Attribute is for internal use
- No inheritance concerns
- You trust developers to follow conventions

Use double underscore (__) when:
- Writing classes meant to be inherited
- You want to prevent accidental overrides
- You want stronger encapsulation

---

## ✅ Summary

- _attribute → convention-based, still accessible
- __attribute → triggers name mangling
- Name mangling renames attributes to _ClassName__attribute
- Prevents accidental overriding in inheritance
- Improves code safety and maintainability

✨ Name mangling isn’t about true privacy—it’s about protection by design.
