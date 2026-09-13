# 📝 Error Handling Quiz

To pass the quiz, you must correctly answer at least **9 out of 10 questions**.

---

## 1️⃣ What will be the output of this code?

```python
try:
    print(22 / 0)
except ZeroDivisionError:
    print("You can't divide by zero!")
```

Choices:

- 0
- 10
- You can't divide by zero! ✅
- 22

Answer: You can't divide by zero!
Dividing by zero raises a ZeroDivisionError, which is caught by the except block.

---

## 2️⃣ Which module of the Python standard library lets you debug your code in an interactive way?

**Choices:**  
- debugpy  
- numpy  
- ABC  
- pdb ✅  

**Answer:** `pdb`  
- The `pdb` module provides an **interactive debugger** for Python code.

---

## 3️⃣ Which exception does Python raise when you try to use a method or attribute that does not exist for that type?

**Choices:**  
- SyntaxBug  
- AttributeError ✅  
- AttributeBug  
- SyntaxError  

**Answer:** `AttributeError`  
- Raised when an object does not have the requested attribute.

---

## 4️⃣ Which Python statement can you insert around various points in your code so you can see the values of variables while debugging?

**Choices:**  
- len()  
- log()  
- print() ✅  
- console()  

**Answer:** `print()`  
- `print()` statements help **inspect variable values** during debugging.

---

## 5️⃣ Which statement lets you manually raise an exception?

**Choices:**  
- from  
- throw  
- raise ✅  
- if  

**Answer:** `raise`  
- The `raise` statement allows you to **trigger exceptions manually**.

---

## 6️⃣ Which error will the code `print("Hello world" raise)` in your Python code?

**Choices:**  
- ValueError  
- NameError  
- SyntaxError ✅  
- It would not raise any error  

**Answer:** `SyntaxError`  
- The code is **syntactically invalid**, so Python raises a `SyntaxError`.

---

## 7️⃣ What does try...except let you do in Python?

**Choices:**  
- It speeds up testing.  
- It lets you write mathematical expressions.  
- It lets you execute a block of code that might raise an exception. ✅  
- It provides a way to test your code interactively.  

**Answer:** `It lets you execute a block of code that might raise an exception.`  
- `try...except` **handles exceptions gracefully**.

---

## 8️⃣ Which object lets you access the exception itself for better debugging and direct printing of the error message?

**Choices:**  
- Traceback Object  
- Exception Object ✅  
- Debugger Object  
- BugFinder Object  

**Answer:** `Exception Object`  
- Using `except Exception as e:` lets you access the **exception object `e`**.

---

## 9️⃣ Which of the following optional clauses can be added to a try...except statement?

**Choices:**  
- else and elif  
- if and else  
- else and finally ✅  
- elif and if  

**Answer:** `else and finally`  
- `else` runs if **no exception occurs**,  
- `finally` runs **no matter what**.

---

## 🔟 Which block of a try statement runs whether an error occurs or not?

**Choices:**  
- except  
- try  
- finally ✅  
- else  

**Answer:** `finally`  
- `finally` is always executed, **useful for cleanup tasks**.
