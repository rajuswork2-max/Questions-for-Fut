# ❓ Q&A — Java, Web Technologies, DSA & General CS

---

# ☕ JAVA PROGRAMMING

## Q1. Who invented Java and what does JVM stand for?
**Answer:** **James Gosling** invented Java in **1995** at **Sun Microsystems**.
- **JVM** = Java Virtual Machine — runs Java bytecode on any platform
- **JDK** = Java Development Kit — tools to write and compile Java
- **JRE** = Java Runtime Environment — needed to run Java programs

---

## Q2. What is the difference between JDK, JRE, and JVM?

**Answer:**
```
JDK (Java Development Kit)
  └── JRE (Java Runtime Environment)
        └── JVM (Java Virtual Machine)
```
- **JVM** — Executes bytecode
- **JRE** — JVM + libraries (for running Java)
- **JDK** — JRE + compiler/tools (for developing Java)

---

## Q3. What does "Write Once, Run Anywhere" mean?
**Answer:** Java code is compiled into **bytecode** (not machine code).
The **JVM** on any operating system can run this bytecode.
So the same `.class` file runs on Windows, Linux, and Mac without changes.

---

## Q4. What is the difference between `==` and `.equals()` in Java?
**Answer:**
- `==` compares **memory addresses** (reference comparison)
- `.equals()` compares **actual content/values**
```java
String a = new String("hello");
String b = new String("hello");
System.out.println(a == b);        // false (different objects)
System.out.println(a.equals(b));   // true (same content)
```

---

## Q5. What is an Interface in Java?
**Answer:** An interface is like a **contract** — it defines methods a class MUST implement.
```java
interface Animal {
    void sound();   // No body — just declaration
}
class Dog implements Animal {
    public void sound() { System.out.println("Woof!"); }
}
```
- A class can **implement multiple interfaces** (solving Java's no-multiple-inheritance issue)

---

## Q6. What is an ArrayList vs Array vs LinkedList?

**Answer:**
| Feature | Array | ArrayList | LinkedList |
|---------|-------|-----------|-----------|
| Size | Fixed | Dynamic | Dynamic |
| Memory | Contiguous | Contiguous | Non-contiguous |
| Access speed | Fast (index) | Fast (index) | Slow (sequential) |
| Insert/Delete | Slow | Slow | Fast |

---

## Q7. What is Exception Handling in Java?
**Answer:**
```java
try {
    int result = 10 / 0;     // Risky code
} catch (ArithmeticException e) {
    System.out.println("Error: " + e.getMessage());
} finally {
    System.out.println("Always runs");
}
```

---

---

# 🌐 WEB TECHNOLOGIES

## Q8. Who invented HTML, CSS, and JavaScript?

**Answer:**
| Language | Inventor | Year | Organization |
|---------|---------|------|-------------|
| HTML | Tim Berners-Lee | 1991 | CERN |
| CSS | Håkon Wium Lie | 1996 | W3C |
| JavaScript | Brendan Eich | 1995 | Netscape |

---

## Q9. What is the difference between HTML, CSS, and JavaScript?
**Answer:**
- **HTML** = Structure of the page (the skeleton/bones)
- **CSS** = Style and appearance (the skin/clothes)
- **JavaScript** = Behavior and interactivity (the muscles/brain)

```html
<h1 id="title">Hello World</h1>   <!-- HTML: structure -->
<style> #title { color: red; } </style>   <!-- CSS: style -->
<script> document.getElementById("title").innerHTML = "Hi!"; </script>   <!-- JS: behavior -->
```

---

## Q10. What is the DOM?
**Answer:** DOM = **Document Object Model**
It is a **tree representation** of the HTML page that JavaScript can access and modify.
```
Document
└── html
    ├── head
    │   └── title
    └── body
        ├── h1
        └── p
```

---

## Q11. What is the difference between GET and POST?

**Answer:**
| GET | POST |
|-----|------|
| Data sent in **URL** | Data sent in **request body** |
| Visible in browser bar | Not visible |
| Used for **fetching** data | Used for **sending** data |
| Can be bookmarked | Cannot be bookmarked |
| Less secure | More secure |

---

## Q12. What is HTTP and HTTPS?
**Answer:**
- **HTTP** = HyperText Transfer Protocol — rules for communication between browser and server
- **HTTPS** = HTTP + **SSL/TLS encryption** — secure version
- **S** stands for **Secure** — data is encrypted, shown by 🔒 padlock in browser

---

---

# 🗂️ DATA STRUCTURES & ALGORITHMS

## Q13. What is the difference between Stack and Queue?

**Answer:**
| Stack | Queue |
|-------|-------|
| **LIFO** (Last In, First Out) | **FIFO** (First In, First Out) |
| `push()` and `pop()` | `enqueue()` and `dequeue()` |
| Like a stack of plates | Like a queue at a ticket counter |

---

## Q14. What is the time complexity of common operations?

**Answer:**
| Operation | Array | Linked List | Binary Search Tree |
|-----------|-------|------------|-------------------|
| Access | O(1) | O(n) | O(log n) |
| Search | O(n) | O(n) | O(log n) |
| Insert | O(n) | O(1) | O(log n) |
| Delete | O(n) | O(1) | O(log n) |

---

## Q15. What is Binary Search? When can you use it?
**Answer:** Binary Search finds an element in a **sorted array** by repeatedly **halving** the search range.
**Time Complexity: O(log n)** — very fast!
```python
def binary_search(arr, target):
    low, high = 0, len(arr)-1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target: return mid
        elif arr[mid] < target: low = mid + 1
        else: high = mid - 1
    return -1
```
**Condition:** Array must be **sorted** before using binary search.

---

## Q16. What is Big O Notation?

**Answer:** Big O describes **how fast an algorithm scales** as input size grows.

| Notation | Name | Example |
|----------|------|---------|
| O(1) | Constant | Accessing array by index |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Linear search |
| O(n log n) | Linearithmic | Merge sort |
| O(n²) | Quadratic | Bubble sort |
| O(2ⁿ) | Exponential | Recursive fibonacci |

---

## Q17. What is the difference between BFS and DFS?

**Answer:**
| BFS (Breadth-First Search) | DFS (Depth-First Search) |
|---------------------------|------------------------|
| Explores **level by level** | Explores **as deep as possible** |
| Uses a **Queue** | Uses a **Stack** (or recursion) |
| Finds **shortest path** | Better for detecting cycles |
| Good for social networks | Good for maze solving |

---

## Q18. Name and explain 3 sorting algorithms.

**Answer:**
1. **Bubble Sort** — Repeatedly swaps adjacent elements if out of order | O(n²)
2. **Selection Sort** — Finds minimum and puts it first each pass | O(n²)
3. **Merge Sort** — Divides array in half, sorts, then merges | O(n log n) ✅ best

---

## Q19. What is a Linked List?
**Answer:** A linked list is a **chain of nodes** where each node contains **data** + a **pointer** to the next node.
```
[10 | →] → [20 | →] → [30 | NULL]
```
- **Advantage:** Fast insert/delete (no shifting)
- **Disadvantage:** No direct access by index (must traverse)

---

## Q20. What is Recursion?
**Answer:** Recursion is when a **function calls itself** to solve a smaller version of the same problem.
Every recursive function needs:
1. **Base case** — condition to stop
2. **Recursive case** — calls itself

```python
def countdown(n):
    if n == 0:          # Base case
        print("Done!")
    else:
        print(n)
        countdown(n-1)  # Recursive call
```

---

*File: 06_Java_Web_DSA_QA.md | Category: Java, Web Technologies, DSA*
