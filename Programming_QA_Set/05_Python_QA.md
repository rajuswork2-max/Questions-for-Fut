# ❓ Q&A — Python Programming

---

## Q1. Who invented Python and when?
**Answer:** **Guido van Rossum** (Netherlands) created Python in **1991**.
He was the "Benevolent Dictator for Life (BDFL)" — he made final decisions for the language until 2018.

---

## Q2. Why is Python popular? What are its key features?
**Answer:**
- **Easy to read** — code looks like plain English
- **Interpreted** — runs line by line (no compilation needed)
- **Dynamically typed** — no need to declare data types
- **Huge library support** — NumPy, Pandas, Django, Flask, TensorFlow
- **Cross-platform** — works on Windows, Mac, Linux
- **Free and open source**

---

## Q3. What is the difference between a List, Tuple, Set, and Dictionary?

**Answer:**
| Type | Ordered | Mutable | Duplicates | Syntax |
|------|---------|---------|------------|--------|
| **List** | ✅ Yes | ✅ Yes | ✅ Yes | `[1, 2, 3]` |
| **Tuple** | ✅ Yes | ❌ No | ✅ Yes | `(1, 2, 3)` |
| **Set** | ❌ No | ✅ Yes | ❌ No | `{1, 2, 3}` |
| **Dictionary** | ✅ Yes | ✅ Yes | Keys: No | `{"a": 1}` |

---

## Q4. What is the difference between `=`, `==`, and `is`?
**Answer:**
- `=` → **Assignment** — `a = 5` (assigns value)
- `==` → **Equality check** — `a == 5` (compares values)
- `is` → **Identity check** — `a is b` (checks if same object in memory)

---

## Q5. What are Python's data types?
**Answer:**
```python
x = 10          # int
x = 3.14        # float
x = "Hello"     # str
x = True        # bool
x = [1,2,3]     # list
x = (1,2,3)     # tuple
x = {1,2,3}     # set
x = {"a": 1}    # dict
x = None        # NoneType
```

---

## Q6. What is a function in Python? How do you define one?
**Answer:**
```python
def greet(name):          # Define function
    return f"Hello, {name}!"

result = greet("Raju")    # Call function
print(result)             # Output: Hello, Raju!
```

---

## Q7. What is a Lambda function?
**Answer:** A lambda is an **anonymous (nameless), one-line function**.
```python
# Regular function
def square(x):
    return x * x

# Lambda equivalent
square = lambda x: x * x
print(square(5))   # Output: 25

# Common use with map()
nums = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, nums))
# Output: [1, 4, 9, 16]
```

---

## Q8. What is `*args` and `**kwargs`?
**Answer:**
- `*args` — accepts **multiple positional arguments** as a tuple
- `**kwargs` — accepts **multiple keyword arguments** as a dictionary

```python
def add(*args):
    return sum(args)
add(1, 2, 3)    # Returns 6

def info(**kwargs):
    for k, v in kwargs.items():
        print(k, "=", v)
info(name="Raju", age=20)   # name = Raju, age = 20
```

---

## Q9. What is a List Comprehension?
**Answer:** A concise way to create lists in one line.
```python
# Normal way
squares = []
for i in range(5):
    squares.append(i**2)

# List comprehension
squares = [i**2 for i in range(5)]
# Output: [0, 1, 4, 9, 16]
```

---

## Q10. What is the difference between `append()` and `extend()`?
**Answer:**
```python
a = [1, 2, 3]
a.append([4, 5])    # Adds as single element → [1, 2, 3, [4, 5]]
a.extend([4, 5])    # Adds each element → [1, 2, 3, 4, 5]
```

---

## Q11. What is exception handling in Python?
**Answer:** Used to handle **runtime errors** without crashing the program.
```python
try:
    x = 10 / 0           # Risky code
except ZeroDivisionError:
    print("Can't divide by zero!")   # Handle error
else:
    print("Success!")    # Runs if no exception
finally:
    print("Done!")       # Always runs
```

---

## Q12. What is OOP in Python? Write a simple class.
**Answer:**
```python
class Animal:
    def __init__(self, name):    # Constructor
        self.name = name

    def speak(self):
        return f"{self.name} makes a sound"

class Dog(Animal):               # Inheritance
    def speak(self):             # Overriding
        return f"{self.name} says Woof!"

d = Dog("Rex")
print(d.speak())   # Output: Rex says Woof!
```

---

## Q13. What is the difference between `range()` and `list()`?
**Answer:**
- `range(5)` → Creates a **range object** (lazy, memory efficient)
- `list(range(5))` → Converts to `[0, 1, 2, 3, 4]` (actual list in memory)

---

## Q14. What does `if __name__ == "__main__":` mean?
**Answer:** This code runs **only when the file is executed directly**, not when imported as a module.
```python
def greet():
    print("Hello!")

if __name__ == "__main__":
    greet()   # Only runs when this file is run directly
```

---

## Q15. What are Python decorators?
**Answer:** A decorator **wraps a function** to add behavior without modifying it.
```python
def shout(func):
    def wrapper():
        print("START")
        func()
        print("END")
    return wrapper

@shout
def hello():
    print("Hello!")

hello()
# Output:
# START
# Hello!
# END
```

---

*File: 05_Python_QA.md | Category: Python Programming*
