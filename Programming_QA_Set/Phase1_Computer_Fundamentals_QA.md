# 📘 PHASE 1 — Computer Fundamentals: Questions & Answers
### (From CS Knowledge Enhancement Plan — Week 1–2)

> Study Tip: Read each question, try to answer in your head, THEN read the answer.

---

## 🔵 SECTION 1: What is a Computer?

### Q1. What is a Computer? Define it clearly.
**Answer:**
A computer is an **electronic device** that:
- **Accepts input** (from keyboard, mouse, etc.)
- **Processes data** (using CPU)
- **Stores data** (in RAM or hard drive)
- **Produces output** (on monitor, printer, etc.)

It follows the **IPO Cycle**: **Input → Process → Output**

---

### Q2. What are the two main types of components in a computer?

**Answer:**
| Type | Definition | Examples |
|------|-----------|---------|
| **Hardware** | Physical parts you can touch | CPU, RAM, keyboard, mouse, monitor |
| **Software** | Programs and instructions you cannot touch | Windows, MS Word, Chrome, Python |

---

### Q3. What are the functional units of a computer?

**Answer:** A computer is made up of 5 functional units:
1. **Input Unit** — takes data from user (keyboard, mouse)
2. **Output Unit** — gives results to user (monitor, printer)
3. **Memory Unit** — stores data (RAM, hard disk)
4. **Arithmetic Logic Unit (ALU)** — performs calculations & comparisons
5. **Control Unit (CU)** — manages and coordinates all units

ALU + CU together = **CPU (Central Processing Unit)**

---

## 🔵 SECTION 2: CPU, RAM, and Storage

### Q4. What is a CPU and what does it do?

**Answer:**
- **CPU** = Central Processing Unit — the **brain** of the computer
- Executes all instructions and performs calculations
- Contains:
  - **ALU** (Arithmetic Logic Unit) — does math and logic
  - **CU** (Control Unit) — controls data flow
  - **Registers** — tiny, super-fast temporary memory inside CPU
  - **Cache** — small fast memory between CPU and RAM

---

### Q5. What is RAM? What makes it different from a hard disk?

**Answer:**
| RAM | Hard Disk / SSD |
|-----|----------------|
| Random Access Memory | Secondary Storage |
| **Volatile** (data lost when power off) | **Non-volatile** (data stays permanently) |
| Stores currently running programs | Stores files long-term |
| Very **fast** | Slower than RAM |
| Example: 8GB, 16GB | Example: 512GB SSD, 1TB HDD |

---

### Q6. What is the difference between RAM and ROM?

**Answer:**
| RAM | ROM |
|-----|-----|
| Random Access Memory | Read Only Memory |
| **Volatile** — loses data on power off | **Non-volatile** — data is permanent |
| Can be **read and written** | Can only be **read** |
| Used for temporarily running programs | Used for storing BIOS/boot instructions |
| Changes every time computer is used | Set by manufacturer, rarely changes |

---

### Q7. Name the types of storage and arrange them by speed (fastest to slowest).

**Answer:**
```
Fastest  →   Registers (inside CPU)
             Cache (L1, L2, L3)
             RAM
             SSD (Solid State Drive)
             HDD (Hard Disk Drive)
Slowest  →   Optical Disc (CD/DVD), USB Drives
```

---

## 🔵 SECTION 3: Number Systems

### Q8. What are the different number systems used in computers?

**Answer:**
| System | Base | Digits Used | Example |
|--------|------|------------|---------|
| **Binary** | 2 | 0, 1 | 1010 |
| **Octal** | 8 | 0 to 7 | 12 |
| **Decimal** | 10 | 0 to 9 | 10 |
| **Hexadecimal** | 16 | 0–9, A–F | A (=10) |

Computers use **binary (base-2)** internally because electronic circuits have 2 states: **ON (1)** and **OFF (0)**.

---

### Q9. Convert Decimal 10 to Binary.

**Answer:**
```
10 ÷ 2 = 5  remainder → 0
 5 ÷ 2 = 2  remainder → 1
 2 ÷ 2 = 1  remainder → 0
 1 ÷ 2 = 0  remainder → 1

Read remainders bottom to top:  1 0 1 0
```
**Decimal 10 = Binary 1010** ✅

---

### Q10. Convert Decimal 255 to Binary.

**Answer:**
```
255 ÷ 2 = 127 → remainder 1
127 ÷ 2 =  63 → remainder 1
 63 ÷ 2 =  31 → remainder 1
 31 ÷ 2 =  15 → remainder 1
 15 ÷ 2 =   7 → remainder 1
  7 ÷ 2 =   3 → remainder 1
  3 ÷ 2 =   1 → remainder 1
  1 ÷ 2 =   0 → remainder 1

Read bottom to top: 11111111
```
**Decimal 255 = Binary 11111111** ✅ (8 bits — all ones)

---

### Q11. What is Hexadecimal and why is it used?

**Answer:**
- **Hexadecimal** = Base-16 number system
- Uses digits: **0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F**
  - A=10, B=11, C=12, D=13, E=14, F=15
- **Why used:** Each hex digit = **4 binary bits** — more compact
- Examples: Colors in web design (`#FF5733`), memory addresses

---

## 🔵 SECTION 4: Data Storage Units

### Q12. What is a bit and a byte? Write the full data unit hierarchy.

**Answer:**
- **1 Bit** = Smallest unit — either **0** or **1**
- **1 Byte** = **8 bits**

```
1 Byte     = 8 bits
1 KB       = 1024 Bytes      (Kilobyte)
1 MB       = 1024 KB         (Megabyte)
1 GB       = 1024 MB         (Gigabyte)
1 TB       = 1024 GB         (Terabyte)
1 PB       = 1024 TB         (Petabyte)
```

---

### Q13. How much storage does a single character take?

**Answer:**
- In **ASCII** encoding, each character = **1 Byte (8 bits)**
- In **Unicode (UTF-8)**, characters can take 1–4 bytes
- Example: The letter `'A'` = ASCII 65 = binary `01000001` = 1 Byte

---

## 🔵 SECTION 5: Operating Systems

### Q14. What is an Operating System (OS)?

**Answer:**
An Operating System is **system software** that:
- Manages **hardware resources** (CPU, memory, files, devices)
- Acts as **middleman** between user and hardware
- Provides a **platform** for application software to run

Without an OS, a computer is just a box of hardware!

---

### Q15. Name the popular Operating Systems and their creators.

**Answer:**
| OS | Created By | Type |
|----|-----------|------|
| **Windows** | Microsoft (Bill Gates) | Proprietary |
| **macOS** | Apple (Steve Jobs team) | Proprietary |
| **Linux** | Linus Torvalds | Open Source (Free) |
| **Android** | Google (based on Linux) | Open Source |
| **iOS** | Apple | Proprietary |
| **Unix** | Bell Labs (Ken Thompson & Dennis Ritchie) | Original OS |

---

### Q16. What are the main functions of an Operating System?

**Answer:**
1. **Process Management** — manages running programs (CPU scheduling)
2. **Memory Management** — allocates RAM to programs
3. **File Management** — organizes files and folders
4. **Device Management** — controls input/output devices via drivers
5. **Security Management** — user authentication, access control
6. **User Interface** — GUI (graphical) or CLI (command line)

---

## 🔵 SECTION 6: Types of Software

### Q17. What is the difference between System Software and Application Software?

**Answer:**
| System Software | Application Software |
|----------------|---------------------|
| Manages hardware | Helps user perform tasks |
| Runs in background | Runs when user needs it |
| Example: OS, Device Drivers, BIOS | Example: MS Word, Photoshop, Chrome, VLC |
| Needed for computer to work | Not essential for basic functioning |

---

### Q18. What is Firmware?

**Answer:**
- Firmware is **software stored permanently in hardware**
- It is between hardware and software — "hardcoded software"
- Cannot be easily changed by users
- Examples: **BIOS** (Basic Input/Output System), printer firmware, router firmware

---

## 🔵 SECTION 7: Input and Output Devices

### Q19. Name 5 input devices and 5 output devices.

**Answer:**
| Input Devices | Output Devices |
|--------------|---------------|
| Keyboard | Monitor (Display) |
| Mouse | Printer |
| Scanner | Speaker / Headphones |
| Microphone | Projector |
| Webcam / Camera | Plotter |
| Joystick | LED / LCD Screen |

---

### Q20. What is a Touch Screen? Is it input or output?

**Answer:**
A **touch screen is BOTH input and output**:
- **Output** — displays information (like a monitor)
- **Input** — detects touch to take user input (like a keyboard/mouse)
It is called a **dual-function device**.

---

## 🔵 SECTION 8: Internet Basics

### Q21. What is the Internet? How is it different from the World Wide Web (WWW)?

**Answer:**
| Internet | World Wide Web (WWW) |
|---------|---------------------|
| Physical **network of networks** — cables, routers, servers | A **service/system** that runs ON the internet |
| Infrastructure | Content (websites, web pages) |
| Also carries email, games, video calls | Accessed using a web browser |

> The Internet is the **highway**. The WWW is the **cars and shops** on that highway.

---

### Q22. What is an IP Address?

**Answer:**
- **IP Address** = Internet Protocol Address — a **unique address** for every device on a network
- Like your **home address** but for computers
- **IPv4**: 32-bit → Example: `192.168.1.1`
- **IPv6**: 128-bit → Example: `2001:0db8:85a3::8a2e:0370:7334`
- IPv6 was introduced because IPv4 addresses were running out

---

## 🔵 SECTION 9: Compiler, Interpreter & Assembler (KEY TOPIC ⭐)

### Q23. What is a Compiler?

**Answer:**
- A compiler **translates the ENTIRE program** at once from high-level language to machine code
- Creates a separate **executable file** (.exe)
- **Shows all errors at once** after full compilation
- Faster execution after compilation
- **Examples:** GCC (for C), `javac` (for Java), g++ (for C++)

```
Source Code (.c) → [Compiler] → Object Code → [Linker] → Executable (.exe)
```

---

### Q24. What is an Interpreter?

**Answer:**
- An interpreter **translates and runs line by line**
- **No separate output file** — runs directly
- **Stops at first error**
- Slower execution (translates every time it runs)
- **Examples:** Python interpreter, JavaScript engine in browser, PHP

```
Source Code (.py) → [Interpreter → runs line 1] → [runs line 2] → ...
```

---

### Q25. What is an Assembler?

**Answer:**
- An assembler converts **Assembly Language → Machine Code**
- Assembly language uses mnemonics (like `MOV`, `ADD`, `JMP`) instead of pure binary
- **Example:** NASM, MASM
- Works at a very **low level**, close to hardware

---

### Q26. Comparison Table — Compiler vs Interpreter vs Assembler

**Answer:**
| Feature | Compiler | Interpreter | Assembler |
|---------|---------|-------------|-----------|
| Input | High-level code (C, Java) | High-level code (Python, JS) | Assembly language |
| Output | Machine code / exe file | Direct execution | Machine code |
| Translation | **Entire program at once** | **Line by line** | **Entire program at once** |
| Speed | Fast after compilation | Slower | Fast |
| Error detection | After full scan | At first error | After full scan |
| Examples | GCC, javac | Python, JavaScript | NASM, MASM |

---

## 🔵 SECTION 10: Source Code, Machine Code, Object Code

### Q27. What is Source Code?

**Answer:**
- Source code is the **human-readable code** written by a programmer
- Written in a high-level language (C, Python, Java, etc.)
- **Not directly executable** by the computer
- Example: `print("Hello World")` in Python is source code

---

### Q28. What is Machine Code?

**Answer:**
- Machine code is **binary instructions** (0s and 1s) that the CPU can directly execute
- Every CPU has its own machine code (x86, ARM, etc.)
- Humans cannot easily read or write machine code
- Example: `10110000 01100001` (assembly `MOV AL, 61`)

---

### Q29. What is Object Code?

**Answer:**
- Object code is the **intermediate output** produced by a compiler
- It is machine code but **not yet fully linked** (cannot run yet)
- Object files have `.obj` or `.o` extension
- A **Linker** combines object files → final executable

```
Source Code → [Compiler] → Object Code (.o) → [Linker] → Executable
```

---

### Q30. What is Bytecode? (Bonus — Java specific)

**Answer:**
- Bytecode is an **intermediate code** produced by the Java compiler (`javac`)
- It is NOT machine code for any specific CPU
- Stored in `.class` files
- The **JVM (Java Virtual Machine)** reads and executes bytecode on any platform
- This is why Java is "Write Once, Run Anywhere"

```
Java Source → [javac] → Bytecode (.class) → [JVM] → Machine Code → Runs
```

---

## 📝 QUICK REVISION — Phase 1 Cheat Sheet

| Topic | Key Point |
|-------|----------|
| Computer definition | IPO Cycle: Input → Process → Output |
| CPU full form | Central Processing Unit |
| ALU function | Arithmetic & Logic operations |
| RAM type | Volatile (temporary) |
| ROM type | Non-volatile (permanent) |
| Binary base | Base-2 (0 and 1 only) |
| 1 Byte = | 8 bits |
| OS examples | Windows, Linux, macOS |
| Compiler vs Interpreter | Whole program vs Line by line |
| Source code | Human-readable code |
| Machine code | Binary code CPU understands |

---

*File: Phase1_Computer_Fundamentals_QA.md*
*CS Knowledge Enhancement Plan — Phase 1 (Week 1–2)*
*Total: 30 Questions & Answers*
