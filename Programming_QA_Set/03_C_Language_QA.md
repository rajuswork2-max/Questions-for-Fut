# ❓ Q&A — C Programming Language

---

## Q1. Who invented C and when?
**Answer:** **Dennis Ritchie** invented C in **1972** at Bell Labs.
C was developed to rewrite the **Unix Operating System**.

---

## Q2. What is the structure of a basic C program?
**Answer:**
```c
#include <stdio.h>       // Header file

int main() {             // Main function - execution starts here
    printf("Hello!");    // Output statement
    return 0;            // Exit code (0 = success)
}
```

---

## Q3. What are data types in C?

**Answer:**
| Data Type | Size | Example |
|-----------|------|---------|
| `int` | 4 bytes | 10, -5, 0 |
| `float` | 4 bytes | 3.14, -2.5 |
| `double` | 8 bytes | 3.14159265 |
| `char` | 1 byte | 'A', 'z' |
| `void` | 0 bytes | No value |

---

## Q4. What is the difference between `printf` and `scanf`?
**Answer:**
- `printf()` — used to **print/display** output to screen
- `scanf()` — used to **read/take input** from user
```c
printf("Enter a number: ");
scanf("%d", &num);
```

---

## Q5. What are the types of operators in C?

**Answer:**
| Type | Operators | Example |
|------|----------|---------|
| Arithmetic | +, -, *, /, % | a + b |
| Relational | ==, !=, >, <, >=, <= | a > b |
| Logical | &&, \|\|, ! | a && b |
| Assignment | =, +=, -=, *= | a = 5 |
| Increment/Decrement | ++, -- | a++, --b |
| Bitwise | &, \|, ^, ~, <<, >> | a & b |

---

## Q6. What is the difference between `while` and `do-while` loop?

**Answer:**
| while | do-while |
|-------|---------|
| Condition checked **before** loop body | Condition checked **after** loop body |
| May not execute at all (0 times) | Executes **at least once** |

```c
// while
while(condition) { ... }

// do-while
do { ... } while(condition);
```

---

## Q7. What is a pointer in C?
**Answer:** A pointer is a **variable that stores the memory address** of another variable.
```c
int a = 10;
int *p = &a;   // p stores address of a
printf("%d", *p);  // *p gives value at address = 10
```
- `&a` = address of a
- `*p` = value at the address stored in p (dereferencing)

---

## Q8. What is the difference between `++i` and `i++`?
**Answer:**
- `++i` = **Pre-increment** — increment first, then use
- `i++` = **Post-increment** — use first, then increment
```c
int i = 5;
printf("%d", ++i);  // prints 6 (incremented before print)
printf("%d", i++);  // prints 6 (printed before increment)
printf("%d", i);    // prints 7
```

---

## Q9. What is a function in C?
**Answer:** A function is a **reusable block of code** that performs a specific task.
```c
int add(int a, int b) {   // Function definition
    return a + b;
}

int main() {
    int result = add(3, 4);   // Function call
    printf("%d", result);     // Output: 7
}
```

---

## Q10. What is recursion? Give an example.
**Answer:** Recursion is when a **function calls itself**.
```c
int factorial(int n) {
    if (n == 0) return 1;        // Base case
    return n * factorial(n-1);   // Recursive call
}
// factorial(4) = 4 × 3 × 2 × 1 = 24
```
Every recursion needs a **base case** to stop.

---

## Q11. What is an array in C?
**Answer:** An array is a **collection of elements of the same data type** stored in contiguous memory.
```c
int marks[5] = {90, 85, 78, 92, 88};
printf("%d", marks[0]);  // Access first element: 90
```
Index starts from **0**.

---

## Q12. What is the difference between `struct` and `union`?

**Answer:**
| struct | union |
|--------|-------|
| Each member has its **own memory** | All members **share the same memory** |
| Total size = sum of all members | Total size = size of **largest** member |
| All members can hold values simultaneously | Only **one** member holds value at a time |

```c
struct Student { int id; float marks; };  // size = 4 + 4 = 8 bytes
union Data { int i; float f; };           // size = 4 bytes (largest)
```

---

## Q13. What is `malloc()` in C?
**Answer:** `malloc()` (**Memory Allocation**) dynamically allocates memory at runtime.
```c
int *ptr = (int*) malloc(5 * sizeof(int));  // Allocates memory for 5 integers
free(ptr);   // Always free after use to avoid memory leak!
```

---

## Q14. What is the difference between `break` and `continue`?
**Answer:**
- `break` — **exits** the loop completely
- `continue` — **skips** current iteration and goes to next

```c
for(int i=0; i<5; i++) {
    if(i == 3) break;      // Loop stops at 3
    printf("%d ", i);      // Output: 0 1 2
}

for(int i=0; i<5; i++) {
    if(i == 3) continue;   // Skips 3
    printf("%d ", i);      // Output: 0 1 2 4
}
```

---

## Q15. Write a C program to check if a number is even or odd.
**Answer:**
```c
#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n % 2 == 0)
        printf("%d is Even", n);
    else
        printf("%d is Odd", n);
    return 0;
}
```

---

*File: 03_C_Language_QA.md | Category: C Programming*
