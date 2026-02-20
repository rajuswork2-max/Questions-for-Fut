# ❓ Q&A — C++ and Object-Oriented Programming (OOP)

---

## Q1. Who invented C++ and what does it add to C?
**Answer:** **Bjarne Stroustrup** invented C++ in **1980** at Bell Labs.
C++ added **Object-Oriented Programming (OOP)** features — classes, objects, inheritance, polymorphism — to the C language.

---

## Q2. What are the 4 pillars of OOP?

**Answer:**
| Pillar | Meaning | Real-World Example |
|--------|---------|-------------------|
| **Encapsulation** | Hiding internal details | ATM machine hides internal circuits |
| **Abstraction** | Showing only essential features | Car's steering wheel (you don't see engine) |
| **Inheritance** | Child class gets parent's properties | Dog inherits from Animal |
| **Polymorphism** | Same name, different behavior | `area()` calculates differently for circle vs square |

---

## Q3. What is a Class and an Object?
**Answer:**
- **Class** = A **blueprint/template** (like a house design)
- **Object** = An **instance** of a class (like the actual house built from the design)

```cpp
class Car {           // Class (blueprint)
public:
    string brand;
    int speed;
    void drive() { cout << "Driving!"; }
};

Car myCar;            // Object (instance)
myCar.brand = "Toyota";
```

---

## Q4. What is a Constructor?
**Answer:** A constructor is a **special function** that is automatically called when an object is created.
It has the **same name as the class** and **no return type**.
```cpp
class Student {
public:
    Student() {          // Constructor
        cout << "Student created!";
    }
};
Student s;   // Automatically prints "Student created!"
```

---

## Q5. What is Inheritance? Name its types.
**Answer:** Inheritance allows a **child class to use properties and methods of a parent class**.
```cpp
class Animal {           // Parent class
public:
    void eat() { cout << "Eating"; }
};

class Dog : public Animal {  // Child class inherits Animal
public:
    void bark() { cout << "Barking"; }
};
```
**Types:**
1. Single Inheritance (A → B)
2. Multiple Inheritance (A, B → C)
3. Multilevel Inheritance (A → B → C)
4. Hierarchical Inheritance (A → B, A → C)
5. Hybrid Inheritance (combination)

---

## Q6. What is the difference between Function Overloading and Function Overriding?

**Answer:**
| Overloading | Overriding |
|------------|-----------|
| **Same name**, different parameters | **Same name**, same parameters |
| In the **same class** | In **parent and child** class |
| Compile-time polymorphism | Runtime polymorphism |
| `add(int, int)` vs `add(float, float)` | Child redefines parent's `display()` |

---

## Q7. What is a Virtual Function?
**Answer:** A virtual function in a parent class can be **overridden in child class** and is resolved at **runtime**.
```cpp
class Animal {
public:
    virtual void sound() { cout << "Some sound"; }
};
class Dog : public Animal {
public:
    void sound() { cout << "Woof!"; }
};
Animal *a = new Dog();
a->sound();  // Output: Woof! (runtime decision)
```

---

## Q8. What is Encapsulation?
**Answer:** Encapsulation = **wrapping data and methods together**, and **restricting direct access** to data.
Achieved using **private** access specifier + **getter/setter** methods.
```cpp
class BankAccount {
private:
    double balance = 1000;    // Hidden from outside
public:
    double getBalance() { return balance; }    // Getter
    void deposit(double amt) { balance += amt; }
};
```

---

## Q9. What is the difference between public, private, and protected?

**Answer:**
| Specifier | Accessible In |
|-----------|--------------|
| `public` | Everywhere (inside + outside class) |
| `private` | Only inside the **same class** |
| `protected` | Inside the class and **child classes** |

---

## Q10. What is Abstraction?
**Answer:** Abstraction means **hiding implementation details** and showing only what's necessary.
Achieved using **abstract classes** (with pure virtual functions).
```cpp
class Shape {
public:
    virtual float area() = 0;   // Pure virtual function — must be overridden
};
class Circle : public Shape {
public:
    float area() { return 3.14 * 5 * 5; }
};
```

---

## Q11. What is the difference between a Class and a Structure in C++?
**Answer:**
| class | struct |
|-------|--------|
| Members are **private** by default | Members are **public** by default |
| Used for OOP with methods | Used for grouping data |
| Supports all OOP features | Simpler, no inheritance by default |

---

## Q12. What is a Destructor?
**Answer:** A destructor is called **automatically when an object is destroyed** (goes out of scope).
Same name as class but with `~` prefix. Used to free memory.
```cpp
class Demo {
public:
    ~Demo() { cout << "Object destroyed!"; }
};
```

---

*File: 04_CPP_OOP_QA.md | Category: C++ & OOP*
