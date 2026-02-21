# 📘 Interview Question Paper — Set 3
## 20 Easy Questions with Detailed Answers per Subject

---

# 📡 SUBJECT 1: Computer Networks

**Q1. What is a Computer Network?**
A computer network is a system of interconnected computing devices (computers, printers, servers, smartphones) that share data and resources with one another through communication links. These links can be wired (Ethernet cables) or wireless (Wi-Fi, Bluetooth). Networks range in size from a simple two-device home setup to the global internet connecting billions of devices. Without networks, every device would operate in isolation, and tasks like sending an email, visiting a website, or sharing a file would be impossible.

---

**Q2. What is the internet? How is it different from an intranet?**
- **Internet:** A global, public network of networks. Anyone with a connection can access it. It uses the TCP/IP protocol suite. Examples: websites, email, and social media.
- **Intranet:** A private network restricted to members of an organization (like a company or university). It uses the same internet technologies but is isolated from the public internet using firewalls. It is used for sharing internal documents, messaging, and internal tools.
- **Extranet:** An intranet extended to specific, trusted external partners.

---

**Q3. What are the different network topologies? Explain each with advantages and disadvantages.**

A network topology describes how nodes are physically or logically connected:

| Topology | Description | Advantage | Disadvantage |
|---------|------------|-----------|--------------|
| **Bus** | All devices share one main cable | Simple, cheap | Cable failure breaks entire network |
| **Star** | All devices connect to a central hub/switch | Easy to manage; failure of one node doesn't break others | Hub/switch failure brings down the whole network |
| **Ring** | Devices connected in a closed loop | Equal access for all devices | One failure can break the entire loop |
| **Mesh** | Every device connects to every other | High redundancy, very reliable | Very expensive and complex to set up |
| **Tree** | Hierarchical combination of star and bus | Easily scalable | Root failure disrupts large parts of the network |

---

**Q4. Define bandwidth and latency. How do they affect network performance?**
- **Bandwidth:** The maximum amount of data that can be transmitted over a network connection per second (measured in Mbps or Gbps). Think of it as the width of a highway — more lanes mean more cars can travel simultaneously.
- **Latency:** The time it takes for data to travel from the source to the destination (measured in milliseconds). Think of it as the speed limit on that highway — even a wide highway is slow if cars move slowly.
- **Performance:** High bandwidth but high latency (like a satellite connection) can still "feel" slow. Ideal networks have **high bandwidth AND low latency**. Gaming and video calls are especially sensitive to latency.

---

**Q5. What are the seven layers of the OSI model? What does each layer do?**

| Layer | Name | Function | Example Protocols |
|-------|------|----------|-------------------|
| 7 | Application | Interface for user applications | HTTP, FTP, SMTP |
| 6 | Presentation | Data formatting, encryption, compression | SSL/TLS, JPEG |
| 5 | Session | Manages sessions/connections between apps | NetBIOS, PPTP |
| 4 | Transport | Reliable end-to-end data delivery, segmentation | TCP, UDP |
| 3 | Network | Logical addressing and routing | IP, ICMP, ARP |
| 2 | Data Link | Physical addressing (MAC), error detection | Ethernet, Wi-Fi |
| 1 | Physical | Raw bit transmission over the medium | Cables, fiber, radio waves |

*Mnemonic to remember:* "**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing" (Application → Physical)

---

**Q6. What is an IP address? What are its types?**
An IP (Internet Protocol) address is a unique numerical label assigned to every device connected to a network. It serves two purposes: **host identification** and **location addressing**.

**Based on version:**
- **IPv4:** 32-bit (e.g., `192.168.0.1`), approx 4.3 billion addresses.
- **IPv6:** 128-bit (e.g., `2001:db8::1`), virtually unlimited addresses.

**Based on type:**
- **Public IP:** Globally unique, assigned by ISP, used on the internet.
- **Private IP:** Used within local networks (e.g., `192.168.x.x`, `10.x.x.x`). Not routable on the internet.
- **Static IP:** Does not change over time (used for servers).
- **Dynamic IP:** Assigned each time a device connects, managed by DHCP.

---

**Q7. What is a subnet mask? Explain with an example.**
A subnet mask is a 32-bit number used alongside an IP address to identify which part of the IP address represents the **network** and which part represents the **host** (device).

**Example:**
- IP Address: `192.168.1.50`
- Subnet Mask: `255.255.255.0`
- Network part: `192.168.1` (first 3 octets)
- Host part: `.50` (last octet)
- This means up to 254 devices (hosts 1–254) can exist on this same network.

Subnet masks are essential for subnetting — dividing a large network into smaller, more manageable pieces.

---

**Q8. What is the role of a router in a network?**
A **router** is a Layer 3 (Network Layer) device that forwards data packets between different networks. It reads the destination **IP address** of each incoming packet and, using its **routing table**, determines the best path to send it toward its destination.

Key functions:
- **Packet Forwarding:** Sends packets from the source network toward the destination.
- **Network Segmentation:** Separates different networks (e.g., your home network from the internet).
- **NAT:** Translates private IPs to a public IP for internet access.
- **DHCP Server:** Often also manages dynamic IP address assignment on home networks.

---

**Q9. What is DHCP? How does it work?**
**DHCP (Dynamic Host Configuration Protocol)** automatically assigns IP addresses and other network settings (subnet mask, gateway, DNS) to devices on a network so they don't need manual configuration.

**Process (DORA):**
1. **Discover:** New device broadcasts a DHCP Discover message.
2. **Offer:** DHCP server responds with an available IP address offer.
3. **Request:** Device requests that specific IP.
4. **Acknowledge:** Server confirms the assignment with a lease time.

Without DHCP, a network administrator would have to manually configure the IP of every single device — practically impossible in large networks.

---

**Q10. What is DNS? What happens during a DNS lookup?**
**DNS (Domain Name System)** is the internet's phone book — it translates human-readable domain names (like `www.google.com`) into machine-readable IP addresses (like `142.250.80.46`).

**DNS Lookup steps:**
1. Your browser checks its **local cache**.
2. If not found, asks the **OS** (which checks its own cache).
3. OS asks the **Recursive Resolver** (usually your ISP's DNS server).
4. Resolver asks a **Root Name Server** (which knows about TLDs like `.com`).
5. Root points to the **TLD Server** (`.com`).
6. TLD points to the **Authoritative Name Server** for `google.com`.
7. Authoritative server returns the IP address.
8. Your browser connects to that IP.

---

**Q11. What is a firewall? What are the types of firewalls?**
A **firewall** is a security system that monitors and controls incoming/outgoing network traffic based on predetermined security rules. It acts as a barrier between trusted internal networks and untrusted external networks.

**Types:**
- **Packet Filtering:** Inspects packets at the network layer and filters by IP, port, and protocol. Simple and fast but doesn't understand context.
- **Stateful Inspection:** Tracks the state of active connections and makes context-aware decisions.
- **Application Layer (Proxy) Firewall:** Operates at Layer 7, understands the application protocol (HTTP, FTP). Most powerful but slowest.
- **Next-Gen Firewall (NGFW):** Combines all above with deep packet inspection, IDS/IPS, and user identity awareness.

---

**Q12. What is the difference between a connection-oriented and a connectionless service?**
- **Connection-Oriented (TCP):** A connection (session) is established before data is sent (three-way handshake). Data is delivered reliably, in order, and with error correction. Overhead is higher. Used for HTTP, email, file transfer.
- **Connectionless (UDP):** Data is sent without establishing a connection first. No guarantee of delivery or order. Much faster and lower overhead. Used for video streaming, DNS, online gaming, VoIP — where some data loss is acceptable but speed is critical.

---

**Q13. What is the difference between unicast, multicast, and broadcast?**
These describe how network packets are addressed:
- **Unicast:** One-to-one communication. A packet is sent from one sender to one specific receiver. Most internet traffic is unicast (loading a webpage).
- **Broadcast:** One-to-all communication. A packet is sent to all devices on the same network segment. Used by protocols like ARP and DHCP discovery.
- **Multicast:** One-to-many (selected group) communication. A packet is sent to a group of interested receivers. Used for live video streaming and IPTV where you don't want to send separate unicast streams to each viewer.

---

**Q14. What is a proxy server and why is it used?**
A **proxy server** is an intermediary server that acts on behalf of clients when making requests to other servers.

**Uses:**
- **Anonymity:** The destination server sees the proxy's IP, not the client's real IP.
- **Content Filtering:** Organizations use proxies to block access to certain websites.
- **Caching:** Stores frequently requested web pages locally to reduce bandwidth usage and load time.
- **Security:** Can scan content for malware before it reaches the client.

A **Reverse Proxy** sits in front of web servers and distributes incoming client requests to backend servers (load balancing).

---

**Q15. Explain the concept of port numbers. What are well-known ports?**
A **port number** is a 16-bit number (0–65535) that identifies a specific process or service on a device. While an IP address identifies the device, a port identifies the application/service on that device.

**Categories:**
- **Well-Known Ports (0–1023):** Standardized for common services.
- **Registered Ports (1024–49151):** Registered for specific applications.
- **Dynamic/Private Ports (49152–65535):** Used temporarily by clients.

**Common Well-Known Ports:**
| Port | Service |
|------|---------|
| 80   | HTTP    |
| 443  | HTTPS   |
| 22   | SSH     |
| 21   | FTP     |
| 25   | SMTP    |
| 53   | DNS     |

---

**Q16. What is the difference between half-duplex and full-duplex communication?**
These terms describe the direction of data flow between two devices:
- **Simplex:** Communication is one-way only (like a TV broadcast — you can only receive, not transmit back).
- **Half-Duplex:** Both parties can communicate, but only one at a time. You must wait for the other to finish before sending. (Like a walkie-talkie — "Over.")
- **Full-Duplex:** Both parties can send and receive data simultaneously. (Like a telephone call — both people can talk and listen at the same time.)

Modern Ethernet and Wi-Fi networks use full-duplex for maximum efficiency.

---

**Q17. What is Network Address Translation (NAT)?**
**NAT** is a process performed by a router that modifies the IP address information in packet headers as they pass through, translating between private (internal) IP addresses and a public (external) IP address.

**Why it matters:**
- Your home has one public IP from your ISP, but many devices (phone, laptop, smart TV). NAT allows all of them to share that single public IP when accessing the internet.
- It also provides a basic layer of security, as internal devices are not directly reachable from the internet.

**Types:** Static NAT, Dynamic NAT, PAT (Port Address Translation / IP Masquerading).

---

**Q18. What is an SSL/TLS certificate and why do websites need it?**
An **SSL/TLS certificate** is a digital certificate that authenticates a website's identity and enables an encrypted (HTTPS) connection.

**Why it's needed:**
- **Encryption:** Prevents eavesdroppers from reading data transmitted between the user and the server (e.g., passwords, credit card numbers).
- **Authentication:** Assures users they are connecting to the legitimate website and not an impersonator (man-in-the-middle attack protection).
- **Trust:** Browsers show a padlock icon for HTTPS sites; browsers warn users about sites without valid certificates.
- **SEO:** Google ranks HTTPS sites higher.

---

**Q19. What is Wi-Fi and what are the common Wi-Fi standards?**
**Wi-Fi** (Wireless Fidelity) is a wireless networking technology that allows devices to connect to a network using radio waves instead of physical cables, based on the IEEE 802.11 family of standards.

| Standard | Common Name | Max Speed | Frequency |
|---------|------------|-----------|-----------|
| 802.11b | Wi-Fi 1    | 11 Mbps   | 2.4 GHz   |
| 802.11g | Wi-Fi 3    | 54 Mbps   | 2.4 GHz   |
| 802.11n | Wi-Fi 4    | 600 Mbps  | 2.4/5 GHz |
| 802.11ac| Wi-Fi 5    | 3.5 Gbps  | 5 GHz     |
| 802.11ax| Wi-Fi 6    | 9.6 Gbps  | 2.4/5/6 GHz|

---

**Q20. What is a VPN (Virtual Private Network) and how does it work?**
A **VPN** creates a secure, encrypted "tunnel" over a public network (like the internet), connecting a device or network to another private network as if they were directly connected.

**How it works:**
1. The VPN client on your device encrypts your data.
2. It sends the encrypted data to a VPN server.
3. The VPN server decrypts it and forwards it to the destination on your behalf.
4. The destination sees the VPN server's IP, not yours.

**Uses:** Remote work (access company resources), privacy (hide your IP), bypassing geo-restrictions, and security on public Wi-Fi.

---

# 🗄️ SUBJECT 2: DBMS (Database Management System)

**Q1. What is a database? Why do we use one?**
A **database** is an organized, structured collection of related data stored electronically so that it can be easily accessed, managed, and updated. Think of it as a digital filing cabinet that is incredibly fast and powerful.

**Why use a database instead of just files?**
- **Eliminates redundancy:** The same data is stored in one place.
- **Ensures consistency:** Changing a record updates it everywhere.
- **Enables concurrent access:** Multiple users can read/write safely at the same time.
- **Provides security:** Access control restricts who can see which data.
- **Supports powerful queries:** retrieve any combination of data instantly using SQL.

---

**Q2. What is the difference between a DBMS and an RDBMS?**
- **DBMS (Database Management System):** A software system that manages databases. Stores data as files with no strict relationship between them. Examples: XML databases, file systems.
- **RDBMS (Relational DBMS):** A specific type of DBMS based on the **relational model**, where data is stored in structured **tables** (called relations) that are linked to each other through keys. It enforces **ACID** properties. Examples: MySQL, PostgreSQL, Oracle, SQL Server.

In practice, almost all enterprise databases today are RDBMS.

---

**Q3. What is a table, row, and column in a database?**
In a relational database:
- **Table (Relation):** A structured collection of data organized into rows and columns, similar to a spreadsheet. Each table represents one type of entity (e.g., `Students`, `Orders`, `Products`).
- **Row (Tuple/Record):** A single entry in the table representing one instance of the entity (e.g., one student's data).
- **Column (Attribute/Field):** A specific property of the entity (e.g., `StudentName`, `RollNo`, `Age`). Every value in a column has the same data type.

Example `Students` table:
| RollNo | Name    | Age | Branch |
|--------|---------|-----|--------|
| 101    | Raju    | 20  | BCA    |
| 102    | Priya   | 21  | BSc    |

---

**Q4. What is SQL? Name its key categories of commands.**
**SQL (Structured Query Language)** is the standard language used to communicate with relational databases — to create structures, insert data, query, update, and control access.

| Category | Full Form | Purpose | Commands |
|---------|-----------|---------|----------|
| **DDL** | Data Definition Language | Defines/modifies schema | CREATE, ALTER, DROP, TRUNCATE |
| **DML** | Data Manipulation Language | Manipulates data | INSERT, UPDATE, DELETE |
| **DQL** | Data Query Language | Retrieves data | SELECT |
| **DCL** | Data Control Language | Manages permissions | GRANT, REVOKE |
| **TCL** | Transaction Control Language | Manages transactions | COMMIT, ROLLBACK, SAVEPOINT |

---

**Q5. What is a Primary Key? What are its characteristics?**
A **Primary Key** is a column (or group of columns) in a table that uniquely identifies every single row in that table.

**Characteristics:**
- **Uniqueness:** No two rows can have the same primary key value.
- **Not NULL:** A primary key column can never be empty (NULL).
- **Immutability:** It should never change after being assigned (best practice).
- **One per table:** A table can only have one primary key (though it can span multiple columns — called a Composite Primary Key).

Example: `StudentID`, `AadharNumber`, `OrderID` are natural primary key candidates.

---

**Q6. What is a Foreign Key? How does it enforce referential integrity?**
A **Foreign Key** is a column in one table (child table) that holds values matching the Primary Key of another table (parent table). It creates a link between the two tables.

**Referential Integrity:** Ensures the relationship between tables remains consistent:
- You cannot insert a value in the foreign key column that doesn't exist in the parent table's Primary Key.
- You cannot delete a record from the parent table if related records exist in the child table (unless `ON DELETE CASCADE` is configured).

```sql
-- 'DeptID' in Employees is a Foreign Key referencing Departments
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50),
    DeptID INT,
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);
```

---

**Q7. What is a SELECT statement? Explain with an example.**
The `SELECT` statement is the most fundamental SQL command, used to retrieve data from one or more tables.

**Basic Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition ORDER BY column;
```

**Examples:**
```sql
-- Get all columns for all students
SELECT * FROM Students;

-- Get only Name and Age of students older than 20
SELECT Name, Age FROM Students WHERE Age > 20;

-- Get students sorted by Name alphabetically
SELECT Name, Branch FROM Students ORDER BY Name ASC;

-- Get the count of students in each branch
SELECT Branch, COUNT(*) AS StudentCount FROM Students GROUP BY Branch;
```

---

**Q8. What is Normalization? Why is it important?**
**Normalization** is the process of systematically organizing a database to reduce data redundancy (storing the same data multiple times) and improve data integrity (accuracy and consistency of data).

**Why is it important?**
- **Eliminates redundancy:** Saves storage space.
- **Prevents anomalies:**
  - *Insert Anomaly:* Can't insert data without other unrelated data.
  - *Update Anomaly:* Changing one fact requires updating it in many places.
  - *Delete Anomaly:* Deleting one record accidentally removes other important data.
- **Ensures consistency:** Data exists in only one place, so there's only one version of the truth.

---

**Q9. Explain 1NF, 2NF, and 3NF with a simple example.**

**Starting table (Un-normalized):**
| StudentID | Name | Courses       | InstructorName |
|-----------|------|---------------|----------------|
| 1         | Raju | Math, Science | Dr. A, Dr. B   |

**1NF:** Each cell must contain one atomic (single) value. No repeating groups.
| StudentID | Name | Course  | InstructorName |
|-----------|------|---------|----------------|
| 1         | Raju | Math    | Dr. A          |
| 1         | Raju | Science | Dr. B          |

**2NF:** Must be in 1NF + No partial dependency (non-key fields must depend on the full Primary Key, not just part of it). Here PK is (StudentID, Course). `Name` depends only on `StudentID`, so it moves to a separate Students table.

**3NF:** Must be in 2NF + No transitive dependency (non-key fields must not depend on other non-key fields). If `InstructorName` depends on `Course` (not on the student), it moves to a Courses table.

---

**Q10. What is the difference between DELETE, TRUNCATE, and DROP?**

| Command | Type | Effect | WHERE Clause | Rollback |
|---------|------|--------|:---:|:---:|
| **DELETE** | DML | Removes specific or all rows based on condition | ✅ Yes | ✅ Yes |
| **TRUNCATE** | DDL | Removes all rows instantly; resets auto-increment | ❌ No | ❌ No (usually) |
| **DROP** | DDL | Removes the entire table (structure + data) | ❌ No | ❌ No |

**Rule of thumb:**
- Use **DELETE** when you want to remove specific rows or need to be able to undo the operation.
- Use **TRUNCATE** to quickly empty a table but keep its structure.
- Use **DROP** when you want to completely get rid of a table.

---

**Q11. What is a JOIN? Explain the types with examples.**
A **JOIN** combines rows from two or more tables based on a related column (usually a foreign key relationship).

Assume two tables: `Employees(EmpID, Name, DeptID)` and `Departments(DeptID, DeptName)`.

```sql
-- INNER JOIN: Only matching rows from both tables
SELECT e.Name, d.DeptName FROM Employees e INNER JOIN Departments d ON e.DeptID = d.DeptID;

-- LEFT JOIN: All rows from Employees, matched rows from Departments (NULLs if no match)
SELECT e.Name, d.DeptName FROM Employees e LEFT JOIN Departments d ON e.DeptID = d.DeptID;

-- RIGHT JOIN: All rows from Departments, matched rows from Employees
SELECT e.Name, d.DeptName FROM Employees e RIGHT JOIN Departments d ON e.DeptID = d.DeptID;

-- FULL OUTER JOIN: All rows from both tables
SELECT e.Name, d.DeptName FROM Employees e FULL OUTER JOIN Departments d ON e.DeptID = d.DeptID;
```

---

**Q12. What is an ER Diagram?**
An **Entity-Relationship (ER) Diagram** is a visual blueprint of a database that shows entities (things), their attributes (properties), and the relationships between them. It is created during the database design phase before any actual tables are built.

**Key symbols:**
- **Rectangle (□):** Entity (e.g., `Student`, `Course`)
- **Oval/Ellipse (○):** Attribute (e.g., `Name`, `Age`)
- **Diamond (◇):** Relationship (e.g., `Enrolls In`)
- **Lines:** Connect entities to relationships and attributes to entities; cardinality (1:1, 1:N, M:N) is shown on the lines.

---

**Q13. What is a View in SQL?**
A **View** is a virtual table defined by a stored SQL query. It does not store data physically — it dynamically retrieves data from underlying base table(s) every time it is queried.

```sql
-- Creating a view
CREATE VIEW HighSalaryEmployees AS
SELECT Name, Salary, Department FROM Employees WHERE Salary > 70000;

-- Using it like a table
SELECT * FROM HighSalaryEmployees;
```

**Benefits:**
- **Security:** Expose only specific columns/rows (hide sensitive data).
- **Simplicity:** Present complex multi-table joins as a single simple view.
- **Reusability:** Write the complex query once, use the view everywhere.

---

**Q14. What is a transaction in DBMS?**
A **transaction** is a logical unit of work comprising one or more SQL operations that must all succeed or all fail together — ensuring the database remains in a consistent state.

**Classic example (Bank Transfer):**
```sql
BEGIN TRANSACTION;
    UPDATE Accounts SET Balance = Balance - 5000 WHERE AccNo = 'A101'; -- Debit
    UPDATE Accounts SET Balance = Balance + 5000 WHERE AccNo = 'B202'; -- Credit
COMMIT; -- Make both changes permanent
-- ROLLBACK; -- To undo both if something fails
```

If the debit succeeds but the system crashes before the credit, a `ROLLBACK` undoes the debit — money is never lost.

---

**Q15. What are ACID properties?**
ACID properties guarantee that database transactions are processed reliably:

- **Atomicity:** "All or nothing." A transaction either completes entirely or not at all. If any step fails, all changes are rolled back.
- **Consistency:** A transaction brings the database from one valid state to another valid state. It cannot violate any defined rules or constraints.
- **Isolation:** Multiple concurrent transactions execute as if they were running one at a time. Partial results of a transaction are not visible to others.
- **Durability:** Once a transaction is committed, the changes are permanent — even if the system crashes immediately after. Achieved through write-ahead logging and backups.

---

**Q16. What is an index in a database? Why is it used?**
A database **index** is a separate data structure (like a B-Tree) that the database creates for one or more columns to allow it to find rows much faster — similar to the index at the back of a textbook.

**Without an index:** The database scans every single row (Full Table Scan = O(n)).
**With an index:** The database jumps directly to the relevant rows (O(log n)).

**Trade-offs:**
- ✅ Much faster `SELECT` queries.
- ❌ Slightly slower `INSERT`, `UPDATE`, `DELETE` (because the index must also be updated).
- ❌ Uses additional disk space.

Primary keys are always indexed automatically.

---

**Q17. What is the difference between a unique key and a primary key?**

| Feature | Primary Key | Unique Key |
|---------|:-----------:|:----------:|
| Uniqueness | ✅ Required | ✅ Required |
| NULL values | ❌ Not allowed | ✅ Allowed (one NULL per column) |
| Count per table | Only ONE | Multiple unique keys allowed |
| Creates index | Clustered index | Non-clustered index |

Example: In a `Students` table, `StudentID` is the Primary Key. `Email` and `AadharNumber` could each be Unique Keys — they must be unique but are not the main identifier.

---

**Q18. What is a Stored Procedure?**
A **Stored Procedure** is a pre-written, named, and saved SQL code block stored in the database that can be executed (called) on demand. Think of it as a function or subroutine for your database.

```sql
-- Creating a stored procedure
CREATE PROCEDURE GetStudentsByBranch(IN branchName VARCHAR(50))
BEGIN
    SELECT * FROM Students WHERE Branch = branchName;
END;

-- Calling it
CALL GetStudentsByBranch('BCA');
```

**Advantages:**
- Code reusability — write once, call many times.
- Better performance — precompiled and cached.
- Enhanced security — users can execute procedures without needing direct table access.

---

**Q19. Explain GROUP BY and HAVING clauses.**
- **`GROUP BY`:** Groups rows that have the same value in specified columns into summary rows. Always used with aggregate functions (`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`).
- **`HAVING`:** Filters the groups produced by `GROUP BY`. It's like `WHERE` but for groups.

```sql
-- Find branches with more than 30 students
SELECT Branch, COUNT(*) AS Total
FROM Students
GROUP BY Branch
HAVING COUNT(*) > 30;
```

**Execution Order:** `WHERE` (filters rows) → `GROUP BY` (groups them) → `HAVING` (filters groups) → `SELECT` (displays).

---

**Q20. What is data integrity and what are the different types?**
**Data integrity** refers to the accuracy, consistency, and reliability of data stored in a database throughout its entire lifecycle.

**Types:**
- **Entity Integrity:** Every row in a table must be uniquely identifiable — enforced by Primary Keys. No two rows can be identical.
- **Referential Integrity:** Relationships between tables must remain consistent — enforced by Foreign Keys. You cannot have an orphan child record (a record with a Foreign Key that has no matching parent).
- **Domain Integrity:** All values in a column must fall within a defined domain (allowed values) — enforced by data types, CHECK constraints, and NOT NULL.
- **User-Defined Integrity:** Business-specific rules enforced through triggers or stored procedures.

---

# 💻 SUBJECT 3: Operating Systems (OS)

**Q1. What is an Operating System? What are its main functions?**
An **Operating System (OS)** is system software that acts as an intermediary between computer hardware and users/applications. Without an OS, users would need to understand complex hardware details to run any program.

**Main Functions:**
- **Process Management:** Creates, schedules, and terminates processes.
- **Memory Management:** Allocates and deallocates memory to processes.
- **File System Management:** Organizes, stores, retrieves, and names files on storage.
- **Device Management:** Manages I/O devices through device drivers.
- **Security & Access Control:** Protects resources from unauthorized access.
- **User Interface:** Provides CLI (terminal) or GUI (graphical desktop) for user interaction.

---

**Q2. What is a process? Explain its components.**
A **process** is an actively executing program. When you double-click a program, the OS loads it into RAM, assigns resources, and creates a process.

**Components of a process:**
- **Code/Text Segment:** The actual compiled program instructions.
- **Data Segment:** Global and static variables.
- **Heap:** Dynamically allocated memory (during runtime via malloc/new).
- **Stack:** Local variables, function parameters, and return addresses.
- **Process Control Block (PCB):** A data structure maintained by the OS storing the process's state, PID, CPU registers, memory maps, and scheduling information.

---

**Q3. What are the different states of a process?**
A process transitions through multiple states during its lifetime:

```
New → Ready → Running → Waiting → Ready → Running → Terminated
```

- **New:** Process is being created.
- **Ready:** Process is loaded in memory and waiting for CPU time.
- **Running:** Process is currently being executed by the CPU.
- **Waiting/Blocked:** Process is waiting for an external event (e.g., disk I/O, user input) to complete.
- **Terminated:** Process has finished execution. Resources are released.

Only one process can be in the **Running** state per CPU core at any given time.

---

**Q4. What is a thread? How is it different from a process?**

| Feature | Process | Thread |
|---------|---------|--------|
| Definition | Independent program in execution | Smallest unit of execution within a process |
| Memory | Has its own separate memory space | Shares memory space with sibling threads |
| Creation Time | Slow (heavy) | Fast (lightweight) |
| Communication | Requires IPC (pipes, shared memory) | Easy — shared memory |
| Crash Impact | One process crash doesn't affect others | One thread crash can crash the entire process |
| Example | Two separate Chrome windows | Multiple tabs within one Chrome window |

Threads within the same process can communicate directly without overhead, making them ideal for responsive applications (e.g., one thread handles UI while another downloads data).

---

**Q5. What is the difference between multitasking, multiprogramming, and multithreading?**
- **Multiprogramming:** Multiple programs are kept in memory simultaneously. When one waits for I/O, the CPU switches to another. Goal: maximize CPU utilization.
- **Multitasking (Time-Sharing):** An extension of multiprogramming where the CPU is rapidly switched between processes (using time slices/quantum), creating the illusion that they run simultaneously. Goal: responsive user interaction.
- **Multithreading:** Multiple threads within a single process run concurrently, sharing the same address space. Goal: parallelism within a single program (e.g., a web server handling multiple requests at once).

---

**Q6. What is CPU scheduling? Why is it needed?**
**CPU Scheduling** is the OS mechanism that decides which process in the Ready Queue gets the CPU next and for how long.

**Why is it needed?** The CPU is a scarce, single resource (mostly), while many processes compete for it. Without scheduling, some processes might never get CPU time, others might hog it, and the system would feel unresponsive.

**Goals of scheduling:**
- Maximize CPU utilization (keep the CPU as busy as possible).
- Maximize throughput (number of processes completed per unit time).
- Minimize turnaround time, waiting time, and response time.

---

**Q7. Explain FCFS scheduling with an example.**
**First-Come, First-Served (FCFS)** is the simplest non-preemptive scheduling algorithm. Processes are executed in the exact order they arrive in the ready queue.

**Example:**
| Process | Arrival | Burst Time |
|---------|---------|-----------|
| P1 | 0 | 8 ms |
| P2 | 1 | 4 ms |
| P3 | 2 | 2 ms |

**Execution Order:** P1 → P2 → P3
- P1 finishes at 8 ms. P2 waits from 1ms to 8ms = 7ms wait. P3 waits from 2ms to 12ms = 10ms wait.
- Average waiting time = (0 + 7 + 10) / 3 = **5.67 ms**

**Problem:** The "Convoy Effect" — short processes wait a very long time behind long processes.

---

**Q8. What is Round Robin scheduling?**
**Round Robin (RR)** is a preemptive scheduling algorithm designed for time-sharing systems. Each process gets a small, fixed CPU time slot called a **time quantum (Q)**. If a process doesn't finish within its quantum, it's preempted and moved to the back of the ready queue.

**Example:** Q = 4ms, Processes: P1 (Burst=10), P2 (Burst=4), P3 (Burst=6)
- t=0: P1 runs 4ms (P1 remaining=6)
- t=4: P2 runs 4ms (P2 done)
- t=8: P3 runs 4ms (P3 remaining=2)
- t=12: P1 runs 4ms (P1 remaining=2)
- t=16: P3 runs 2ms (P3 done)
- t=18: P1 runs 2ms (P1 done)

**Pros:** Fair for all processes. **Cons:** Higher context-switching overhead.

---

**Q9. What is a deadlock? Give a real-life analogy.**
A **deadlock** is a situation where two or more processes are permanently blocked, each waiting for a resource held by the other.

**Real-life analogy:** A gridlock at a 4-way intersection where cars from all four directions have entered the intersection and are blocking each other in a circle. Nobody can move forward because everyone is waiting for the car in front of them to move first.

**In computing:** Process A holds File X and is waiting for File Y. Process B holds File Y and is waiting for File X. Neither can proceed — they are stuck forever.

---

**Q10. What are the four necessary conditions for a deadlock to occur?**
All four conditions must hold simultaneously for a deadlock:

1. **Mutual Exclusion:** At least one resource must be held in a non-shareable mode (only one process can use it at a time).
2. **Hold and Wait:** A process is holding at least one resource while waiting to acquire additional resources held by other processes.
3. **No Preemption:** Resources cannot be forcibly taken away from a process; they can only be voluntarily released.
4. **Circular Wait:** A circular chain of processes exists: P1 waits for P2, P2 waits for P3, P3 waits for P1.

Breaking even one of these conditions prevents deadlock.

---

**Q11. What is virtual memory?**
**Virtual memory** is a memory management technique where the OS creates the illusion of a much larger memory space than the actual physical RAM by using a portion of the hard disk (called the **swap space** or **page file**) as an extension of RAM.

**How it works:**
- Programs don't need all their pages in RAM at once.
- Inactive pages are temporarily stored on disk.
- When needed, the OS swaps them back into RAM (page fault mechanism).
- Each process sees its own large, continuous virtual address space.

**Benefits:** Run programs larger than physical RAM, better process isolation, and simplified memory management.

---

**Q12. What is paging?**
**Paging** is a memory management scheme that eliminates the need for contiguous memory allocation. Physical memory is divided into fixed-size blocks called **frames**. Logical memory (from the process's perspective) is divided into same-sized blocks called **pages**. The OS maintains a **Page Table** that maps each page to its corresponding frame in physical memory.

**Advantages:**
- Eliminates external fragmentation.
- Enables virtual memory.
- Simple allocation — just find any free frame.

**Disadvantage:** Can cause **internal fragmentation** (the last page of a process may not fill an entire frame).

---

**Q13. What is the difference between internal and external fragmentation?**
- **Internal Fragmentation:** Wasted memory **inside** an allocated block. Occurs when a process is allocated more memory than it actually needs. The extra allocated memory is wasted but cannot be used by others.
  - *Example:* Process needs 22 KB, OS gives 24 KB (due to fixed block size). 2 KB is wasted internally.
- **External Fragmentation:** Wasted memory **outside** allocated blocks. Occurs when free memory exists but is scattered in small non-contiguous blocks, and no single contiguous block can satisfy a large request.
  - *Solution:* **Compaction** (rearranging processes in memory to consolidate free space) or using Paging/Segmentation.

---

**Q14. What is a file system? What does it do?**
A **file system** is the OS component responsible for how data is stored, organized, named, and retrieved on storage devices (HDDs, SSDs, USBs).

**Functions:**
- Creates, reads, writes, and deletes files and directories.
- Manages file metadata (name, size, permissions, timestamps, owner).
- Provides a hierarchical directory structure (folders within folders).
- Manages disk space allocation (tracking which blocks are free/used).

**Common File Systems:**
| OS | File System |
|----|------------|
| Windows | NTFS, FAT32 |
| Linux | ext4, XFS |
| macOS | APFS, HFS+ |

---

**Q15. What is a semaphore? What are its types?**
A **semaphore** is a synchronization integer variable used to control access to shared resources in a concurrent environment, preventing race conditions.

**Operations:**
- **wait(S) / P(S):** If S > 0, decrement S (proceed). If S == 0, block (wait).
- **signal(S) / V(S):** Increment S, and if any process is waiting, wake it up.

**Types:**
- **Binary Semaphore (Mutex):** Value is only 0 or 1. Used for mutual exclusion (ensuring one process enters the critical section at a time).
- **Counting Semaphore:** Value ranges from 0 to N. Used to control access to a resource with multiple identical instances (e.g., a pool of 5 database connections).

---

**Q16. What is a critical section?**
A **critical section** is a segment of code that accesses a shared resource (like a shared variable, file, or memory) and must not be executed by more than one process/thread simultaneously.

**The Critical Section Problem** requires a solution that satisfies:
1. **Mutual Exclusion:** Only one process in the critical section at a time.
2. **Progress:** If no one is in the critical section, a waiting process should be able to enter.
3. **Bounded Waiting:** A process must not wait forever to enter its critical section.

Proper synchronization primitives (mutexes, semaphores, monitors) are used to protect critical sections.

---

**Q17. What is a kernel? What is the difference between user mode and kernel mode?**
The **kernel** is the core of the OS that has unrestricted access to all hardware resources. It manages everything below the user-visible level.

- **Kernel Mode (Privileged Mode):** The CPU can execute any instruction and access any memory/hardware. The OS kernel runs in this mode.
- **User Mode (Unprivileged Mode):** Restricted mode where regular applications run. They cannot directly access hardware or execute privileged instructions. They must request services from the kernel via **system calls**.

This separation is a fundamental **security boundary** — it prevents user applications from accidentally or maliciously crashing the system or accessing other processes' data.

---

**Q18. What are the different types of OS?**
- **Batch OS:** Processes jobs in groups (batches) without user interaction. Old mainframe systems.
- **Time-Sharing OS:** Multiple users/programs share CPU time. Interactive, responsive. (Unix, Linux)
- **Real-Time OS (RTOS):** Processes data and provides a response within a guaranteed time constraint. Used in embedded systems, aviation, medical equipment.
- **Distributed OS:** Manages a collection of different computers networked together and makes them appear as a single coherent system.
- **Mobile OS:** Designed for smartphones. (Android, iOS)

---

**Q19. What is thrashing?**
**Thrashing** is a state of severe OS performance degradation where the system spends more time swapping pages in and out of disk (between physical RAM and swap space) than actually executing user programs.

**Cause:** Too many processes are running simultaneously, and between them they need more memory than is physically available. Every process causes constant page faults, and the CPU is mostly idle while waiting for disk I/O.

**Solutions:**
- Reduce the degree of multiprogramming (run fewer processes).
- Add more physical RAM.
- Implement a working set model to track each process's active pages.

---

**Q20. What is the difference between preemptive and non-preemptive scheduling?**
- **Non-Preemptive Scheduling:** Once the CPU is allocated to a process, it cannot be taken away until the process completes or voluntarily gives up the CPU (e.g., waiting for I/O). Simple but can be unfair to short jobs.
  - *Examples:* FCFS, SJF (non-preemptive)

- **Preemptive Scheduling:** The OS can forcibly take the CPU away from a running process (e.g., when a higher-priority process arrives or when a time quantum expires). Ensures better responsiveness but requires context-switching overhead.
  - *Examples:* Round Robin, Priority Scheduling (preemptive), SRTF

---


# 🔵 SUBJECT 4: C Programming

**Q1. What is C? Why is it called a middle-level language?**
**C** is a general-purpose, procedural programming language created by Dennis Ritchie at Bell Labs in 1972. It is called a **middle-level language** because it combines features of both high-level and low-level languages:
- Like high-level languages, it has readable syntax, structured programming constructs, and is machine-independent (portable source code).
- Like low-level languages, it allows direct memory manipulation through pointers, bit-level operations, and close interaction with hardware — making it ideal for writing operating systems and embedded systems.

Linux, Windows, and the compilers for most modern languages are written in C.

---

**Q2. What is the difference between a compiler and an interpreter? How is C compiled?**
- **Compiler:** Translates the entire source code into machine code (executable) at once before the program runs. Resulting program is fast but compilation takes time.
- **Interpreter:** Translates and executes code line by line at runtime. Slower execution but easier to debug interactively.

**C compilation steps (compilation pipeline):**
1. **Preprocessor:** Processes `#include`, `#define` directives — expands macros and includes header files.
2. **Compiler:** Converts preprocessed C code into assembly language.
3. **Assembler:** Converts assembly into machine code (object file `.o`).
4. **Linker:** Combines object files and library code into a final executable.

---

**Q3. What are data types in C? List all primary data types.**
A **data type** defines the type of data a variable can hold and how much memory it occupies.

| Data Type | Size | Range (approx.) |
|-----------|------|-----------------|
| `char` | 1 byte | -128 to 127 |
| `int` | 4 bytes | -2,147,483,648 to 2,147,483,647 |
| `float` | 4 bytes | 6-7 decimal digit precision |
| `double` | 8 bytes | 15-16 decimal digit precision |
| `void` | No size | Represents absence of type |

Modifiers: `short`, `long`, `signed`, `unsigned` further refine these.

---

**Q4. What is a variable and what are the rules for naming one in C?**
A **variable** is a named storage location in memory that holds a value which can change during program execution. Every variable has a data type, name, and value.

**Naming Rules:**
- Can contain letters (A–Z, a–z), digits (0–9), and underscores (`_`).
- Must begin with a letter or underscore, NOT a digit.
- Cannot be a reserved keyword (e.g., `int`, `for`, `return`).
- C is case-sensitive (`count` and `Count` are different variables).
- No spaces or special characters allowed.

```c
int age = 20;       // Valid
float _salary = 50000.0; // Valid
int 2ndYear;        // INVALID - starts with digit
```

---

**Q5. Explain the different types of operators in C.**

| Category | Operators | Example |
|---------|-----------|---------|
| Arithmetic | `+`, `-`, `*`, `/`, `%` | `a + b`, `a % b` |
| Relational | `==`, `!=`, `<`, `>`, `<=`, `>=` | `a > b` |
| Logical | `&&`, `||`, `!` | `a > 0 && b > 0` |
| Assignment | `=`, `+=`, `-=`, `*=` | `a += 5` |
| Bitwise | `&`, `|`, `^`, `~`, `<<`, `>>` | `a & b` |
| Increment/Decrement | `++`, `--` | `a++`, `--b` |
| Conditional (Ternary) | `? :` | `max = (a>b) ? a : b` |
| Sizeof | `sizeof()` | `sizeof(int)` returns 4 |

---

**Q6. Explain the if-else and switch-case control structures.**

**if-else:** Executes different blocks based on a boolean condition.
```c
if (marks >= 90) {
    printf("Grade A");
} else if (marks >= 70) {
    printf("Grade B");
} else {
    printf("Grade C");
}
```

**switch-case:** For multi-way branching based on the value of an expression (works with integer/char types).
```c
switch(day) {
    case 1: printf("Monday"); break;
    case 2: printf("Tuesday"); break;
    default: printf("Other day");
}
```

**Key difference:** `switch` is cleaner and faster for multiple fixed-value comparisons; `if-else` handles ranges and complex conditions.

---

**Q7. What are loops in C? Explain for, while, and do-while.**

**for loop:** Best when the number of iterations is known.
```c
for(int i = 0; i < 5; i++) { printf("%d ", i); }
// Output: 0 1 2 3 4
```

**while loop:** Best when the number of iterations is unknown; loops as long as condition is true.
```c
int n = 5;
while(n > 0) { printf("%d ", n--); }
// Output: 5 4 3 2 1
```

**do-while loop:** Executes the body at least once, then checks the condition.
```c
int n;
do { scanf("%d", &n); } while(n < 0); // Keep asking until positive number
```

---

**Q8. What is a function in C? What are its components?**
A **function** is a self-contained, reusable block of code that performs a specific task. If you need to do the same task multiple times, write it as a function and call it rather than repeating the code.

**Components:**
```c
// Function Declaration (Prototype) - tells the compiler the function exists
int add(int a, int b);

// Function Definition
int add(int a, int b) {  // int = return type, add = name, (int a, int b) = parameters
    return a + b;         // return statement
}

// Function Call
int result = add(10, 20); // Passing arguments
```

**Benefits:** Code reusability, modularity, easier debugging, and shorter programs.

---

**Q9. What is an array in C? How is it declared and initialized?**
An **array** is a collection of elements of the **same data type** stored in contiguous (sequential) memory locations, accessed using a single name and an index.

```c
// Declaration (size must be constant)
int scores[5];

// Declaration + Initialization
int scores[5] = {95, 87, 76, 88, 90};
float prices[] = {9.99, 14.50, 3.75}; // Size inferred as 3

// Access elements (0-indexed)
printf("%d", scores[0]); // 95 (first element)
printf("%d", scores[4]); // 90 (last element)

// Traversal with loop
for(int i = 0; i < 5; i++) { printf("%d ", scores[i]); }
```

**Limitation:** Fixed size at compile time; all elements must be the same type.

---

**Q10. What is a pointer in C? How do you declare and use one?**
A **pointer** is a variable that stores the memory address of another variable, rather than a data value directly.

```c
int x = 10;
int *ptr;      // Declare a pointer to int
ptr = &x;      // & = "address of" operator; ptr now holds the address of x

printf("%d", x);    // 10 (value of x)
printf("%p", ptr);  // 0x7ffd... (address of x, printed as hex)
printf("%d", *ptr); // 10 (* = dereference operator; gets value at the address)

*ptr = 99;     // Changes the value of x through the pointer
printf("%d", x);    // 99
```

Pointers are fundamental to dynamic memory, arrays, strings, and passing by reference in C.

---

**Q11. Explain `malloc()`, `calloc()`, `realloc()`, and `free()` for dynamic memory.**

All from `<stdlib.h>`, used for **dynamic memory allocation** (allocating memory at runtime on the heap):

| Function | Purpose |
|---------|---------|
| `malloc(size)` | Allocates `size` bytes of uninitialized memory. Returns `void*`. |
| `calloc(n, size)` | Allocates `n` elements of `size` bytes each, initialized to **0**. |
| `realloc(ptr, newSize)` | Resizes a previously allocated block. Can grow or shrink. |
| `free(ptr)` | Releases previously allocated memory back to the OS. |

```c
int *arr = (int*) malloc(5 * sizeof(int));  // Allocate array of 5 ints
if(arr == NULL) { /* Always check for allocation failure */ }
arr[0] = 42;
free(arr);  // Always free when done!
arr = NULL; // Prevent dangling pointer
```

---

**Q12. What is a string in C? How is it stored?**
In C, there is no built-in `string` data type. A string is simply an array of `char` values terminated by a **null character `'\0'`**. The null terminator tells string functions where the string ends.

```c
char name[] = "Raju";
// Stored as: ['R', 'a', 'j', 'u', '\0']
// Size = 5 bytes (4 chars + 1 null terminator)

char name2[10] = "Raju"; // Extra space is fine
// Use string.h functions:
// strlen(name) → 4 (not counting '\0')
// strcpy(dest, src) → copies a string
// strcmp(s1, s2) → compares strings (0 if equal)
// strcat(dest, src) → concatenates strings
```

---

**Q13. What is a structure (`struct`) in C?**
A **structure** is a user-defined data type that groups together variables of different data types under a single name, representing a real-world entity.

```c
// Define the structure
struct Student {
    int rollNo;
    char name[50];
    float cgpa;
};

// Create a variable of type struct Student
struct Student s1;
s1.rollNo = 101;
strcpy(s1.name, "Raju");
s1.cgpa = 9.2;

printf("Name: %s, CGPA: %.1f", s1.name, s1.cgpa);
```

**Use case:** Structures are the building blocks of object-oriented concepts in C, and are used to represent records like student info, employee details, coordinates, etc.

---

**Q14. What is the difference between `struct` and `union`?**

| Feature | `struct` | `union` |
|---------|---------|---------|
| Memory | Each member gets its own memory | All members share the same memory block |
| Size | Sum of all member sizes (+ padding) | Size of the largest member |
| Access | All members can hold values simultaneously | Only one member holds a valid value at a time |
| Use case | Grouping related data | Memory-efficient storage of alternative data types |

```c
union Data {
    int i;
    float f;
    char c;
};  // Size = sizeof(float) = 4 bytes (largest member)
```

---

**Q15. What are preprocessor directives in C?**
**Preprocessor directives** are instructions processed by the C preprocessor **before** the actual compilation begins. They begin with `#` and don't end with a semicolon.

| Directive | Purpose | Example |
|-----------|---------|---------|
| `#include` | Insert a header file | `#include <stdio.h>` |
| `#define` | Define a macro/constant | `#define PI 3.14159` |
| `#ifdef` / `#endif` | Conditional compilation | `#ifdef DEBUG` |
| `#ifndef` | Compile only if NOT defined | `#ifndef HEADER_H` |
| `#undef` | Undefine a macro | `#undef PI` |
| `#pragma` | Compiler-specific instructions | `#pragma once` |

---

**Q16. What is recursion in C? Write a recursive function for factorial.**
**Recursion** is when a function calls itself to solve a smaller version of the same problem. Every recursive function must have a **base case** (to stop recursion) and a **recursive case**.

```c
int factorial(int n) {
    if (n == 0 || n == 1)  // Base case: stop recursion
        return 1;
    return n * factorial(n - 1);  // Recursive case
}
/* Call stack for factorial(4):
   factorial(4) = 4 * factorial(3)
                = 4 * 3 * factorial(2)
                = 4 * 3 * 2 * factorial(1)
                = 4 * 3 * 2 * 1 = 24 */
```

**Warning:** Without a proper base case, recursion leads to infinite calls and a stack overflow.

---

**Q17. What is a file in C? How do you read and write files?**
C provides file I/O through the `<stdio.h>` library using `FILE` pointers.

```c
// Writing to a file
FILE *fp = fopen("data.txt", "w");  // "w" = write mode
if (fp == NULL) { printf("Error!"); }
fprintf(fp, "Hello, Raju!\n");
fclose(fp);  // Always close the file

// Reading from a file
FILE *fp2 = fopen("data.txt", "r");  // "r" = read mode
char buffer[100];
while (fgets(buffer, 100, fp2) != NULL) {
    printf("%s", buffer);
}
fclose(fp2);
```

**File modes:** `"r"` read, `"w"` write (creates/truncates), `"a"` append, `"r+"` read+write.

---

**Q18. What is the `const` keyword? How is it used with pointers?**
`const` prevents a variable or what a pointer points to from being modified.

```c
const int MAX = 100;  // MAX cannot be changed

// Pointer to const: cannot change the value it points to
const int *ptr1 = &x;  // *ptr1 = 5 is ILLEGAL; ptr1 = &y is OK

// Const pointer: the pointer address itself cannot change
int * const ptr2 = &x;  // ptr2 = &y is ILLEGAL; *ptr2 = 5 is OK

// Const pointer to const: nothing can change
const int * const ptr3 = &x;  // Both are ILLEGAL
```

---

**Q19. What is the difference between `scanf` and `gets` for reading strings?**
Both read string input from the user, but:
- **`scanf("%s", str)`:** Reads a word (stops at whitespace). Relatively safe if length is specified (e.g., `%49s`).
- **`gets(str)`:** Reads an entire line including spaces until newline. **DANGEROUS** — no bounds checking, can cause buffer overflow. **Removed from C11 standard.**
- **`fgets(str, n, stdin)`:** Safe alternative to `gets`. Reads at most `n-1` characters, preventing overflow.

```c
char name[50];
fgets(name, 50, stdin);  // SAFE - always use this instead of gets
```

---

**Q20. What is the difference between `exit()` and `return` in C?**
- **`return` (from `main`):** Ends the `main` function and returns control to the calling environment (OS). Cleanup functions registered with `atexit()` are called. Local destructors are called.
- **`exit(code)`:** Immediately terminates the entire program from anywhere in the code (not just `main`). Calls `atexit()` registered functions. Flushes and closes all open `stdio` streams.
- **`_exit(code)`:** Terminates immediately without any cleanup — used in special cases like after `fork()` in Unix.

Exit codes: `0` = success, non-zero = some error.

---


# 🟠 SUBJECT 5: C++

**Q1. What is C++ and how does it differ from C?**
**C++** is a general-purpose programming language created by Bjarne Stroustrup in 1985 as an extension of C. The key addition is full support for **Object-Oriented Programming (OOP)**, along with templates, operator overloading, exception handling, the Standard Template Library (STL), and many other modern features.

| Feature | C | C++ |
|---------|---|-----|
| Paradigm | Procedural | Multi-paradigm (Procedural + OOP + Generic) |
| Structs | No member functions | Structs can have member functions |
| Classes | No | Yes (core feature) |
| Namespaces | No | Yes |
| Function overloading | No | Yes |
| Standard Library | `<stdio.h>`, `<stdlib.h>` | STL (`<iostream>`, `<vector>`, etc.) |

---

**Q2. What is a class in C++? Write a simple class example.**
A **class** is a user-defined blueprint (template) that bundles data (member variables) and the functions that operate on that data (member functions/methods) into a single logical unit.

```cpp
class Car {
private:             // Data members (attributes)
    string brand;
    int speed;

public:              // Member functions (methods)
    Car(string b, int s) {  // Constructor
        brand = b;
        speed = s;
    }
    void display() {
        cout << brand << " goes " << speed << " km/h" << endl;
    }
};

// Creating an object (instance)
Car myCar("Toyota", 180);
myCar.display();  // Toyota goes 180 km/h
```

---

**Q3. What are the four pillars of OOP?**

- **Encapsulation:** Bundling data and methods into one unit (class) and restricting direct access to internal data using access specifiers (`private`, `protected`). Forces use of public methods (getters/setters) to interact with data, protecting data integrity.

- **Abstraction:** Hiding complex implementation details and exposing only what is necessary. A user of a `Car` class doesn't need to know how the engine works internally — they just call `accelerate()`.

- **Inheritance:** A new class (derived/child class) inherits properties and behaviors from an existing class (base/parent class), promoting code reuse. `ElectricCar` inherits from `Car` and adds `batteryLevel`.

- **Polymorphism:** The ability for the same function name or operator to behave differently based on context (overloading) or the actual object type at runtime (overriding with virtual functions).

---

**Q4. What is inheritance in C++? What are its types?**
**Inheritance** allows a derived class to inherit all public and protected members from a base class.

```cpp
class Animal {          // Base/Parent class
public:
    void eat() { cout << "Eating..."; }
};

class Dog : public Animal {  // Derived/Child class
public:
    void bark() { cout << "Woof!"; }
};

Dog d;
d.eat();  // Inherited from Animal
d.bark(); // Dog's own method
```

**Types of Inheritance:**
1. **Single:** A derives from B.
2. **Multiple:** C derives from A and B.
3. **Multilevel:** C derives from B, which derives from A.
4. **Hierarchical:** B and C both derive from A.
5. **Hybrid:** Combination of the above.

---

**Q5. What is a constructor? How many types are there?**
A **constructor** is a special member function that is automatically called when an object of a class is created. It has the same name as the class and no return type.

**Types:**
- **Default Constructor:** Takes no parameters. Compiler provides one if you don't define any constructor.
- **Parameterized Constructor:** Takes arguments to initialize members with specific values.
- **Copy Constructor:** Takes a reference to another object of the same class and creates a copy. `Car(const Car &src)`.

```cpp
class Point {
    int x, y;
public:
    Point() { x = 0; y = 0; }           // Default
    Point(int a, int b) { x=a; y=b; }   // Parameterized
    Point(const Point &p) { x=p.x; y=p.y; } // Copy
};
```

---

**Q6. What is a destructor? When is it called?**
A **destructor** is a special member function prefixed with a tilde (`~`) that is automatically called when an object:
- Goes out of scope (local object at end of block).
- Is explicitly deleted using the `delete` keyword (for heap-allocated objects).
- The program terminates (for global/static objects).

```cpp
class FileManager {
public:
    FileManager() { cout << "File opened."; }
    ~FileManager() { cout << "File closed."; } // Cleanup resources
};
// When F goes out of scope, destructor is called automatically
{ FileManager F; }  // "File opened." then "File closed."
```

Destructors are crucial for releasing dynamically allocated memory, closing files, releasing network connections — preventing resource leaks.

---

**Q7. What are access specifiers in C++?**
**Access specifiers** control the visibility and accessibility of class members:

| Specifier | Same Class | Derived Class | Outside Class |
|-----------|:---------:|:-------------:|:------------:|
| `public` | ✅ | ✅ | ✅ |
| `protected` | ✅ | ✅ | ❌ |
| `private` | ✅ | ❌ | ❌ |

**Best practice:** Make data members `private` (data hiding/encapsulation) and provide controlled access through `public` getter and setter methods.

```cpp
class BankAccount {
private:
    double balance;  // Cannot be accessed directly from outside
public:
    double getBalance() { return balance; }        // Getter
    void deposit(double amount) { balance += amount; } // Controlled access
};
```

---

**Q8. What is function overloading in C++?**
**Function overloading** allows you to define multiple functions with the same name but different parameter lists (different number, type, or order of parameters) within the same scope.

The compiler determines which version to call at **compile time** based on the arguments provided.

```cpp
void print(int x)    { cout << "Integer: " << x; }
void print(double x) { cout << "Double: " << x; }
void print(string x) { cout << "String: " << x; }

print(42);        // Calls print(int)
print(3.14);      // Calls print(double)
print("Hello");   // Calls print(string)
```

**Note:** You CANNOT overload functions that differ only in return type — the parameter list must be different.

---

**Q9. What is a virtual function in C++?**
A **virtual function** is a function declared in a base class using the `virtual` keyword that is intended to be **overridden** in derived classes. When called through a base class pointer or reference, the version that runs is determined at **runtime** (dynamic dispatch) based on the actual object's type — enabling runtime polymorphism.

```cpp
class Shape {
public:
    virtual void draw() { cout << "Drawing a Shape"; }
};
class Circle : public Shape {
public:
    void draw() override { cout << "Drawing a Circle"; }
};
class Square : public Shape {
public:
    void draw() override { cout << "Drawing a Square"; }
};

Shape *s = new Circle();
s->draw();  // "Drawing a Circle" — not "Drawing a Shape" (runtime decision!)
```

---

**Q10. What is an abstract class and a pure virtual function?**
- **Pure Virtual Function:** A virtual function declared with `= 0`. It has no implementation in the base class, forcing every derived class to provide its own.
  ```cpp
  virtual void draw() = 0;  // Pure virtual function
  ```
- **Abstract Class:** Any class containing at least one pure virtual function. You **cannot create an object** of an abstract class — it is only meant to be used as a base class interface.

```cpp
class Shape {  // Abstract class
public:
    virtual double area() = 0;  // Forces derived classes to implement area()
};
class Circle : public Shape {
    double r;
public:
    Circle(double r) : r(r) {}
    double area() override { return 3.14 * r * r; }
};
```

---

**Q11. What is operator overloading?**
**Operator overloading** redefines the built-in behavior of C++ operators (`+`, `-`, `*`, `==`, `<<`, etc.) for user-defined types (classes), making code using those types feel natural and readable.

```cpp
class Complex {
public:
    int real, imag;
    Complex(int r, int i) : real(r), imag(i) {}
    // Overload the + operator
    Complex operator+(const Complex &c) {
        return Complex(real + c.real, imag + c.imag);
    }
    // Overload << for output
    friend ostream& operator<<(ostream &out, const Complex &c) {
        out << c.real << "+" << c.imag << "i";
        return out;
    }
};
Complex c1(2,3), c2(1,4);
cout << c1 + c2;  // "3+7i"
```

---

**Q12. What is the `this` pointer in C++?**
**`this`** is a hidden pointer automatically available inside every non-static member function. It points to the object for which the member function was called.

**Uses:**
- Distinguish between a member variable and a parameter with the same name.
- Return a reference to the current object (enables method chaining).

```cpp
class Box {
    int length;
public:
    Box& setLength(int length) {
        this->length = length;  // this->length is member; length is parameter
        return *this;           // Return current object reference
    }
};
```

---

**Q13. What are templates in C++?**
**Templates** allow writing generic, type-independent code. The compiler generates the specific version of the code for each data type used.

**Function Template:**
```cpp
template <typename T>
T maxVal(T a, T b) {
    return (a > b) ? a : b;
}
cout << maxVal(5, 10);     // Works with int → 10
cout << maxVal(3.5, 2.7);  // Works with double → 3.5
```

**Class Template:**
```cpp
template <typename T>
class Stack {
    T arr[100];
    int top = -1;
public:
    void push(T val) { arr[++top] = val; }
    T pop() { return arr[top--]; }
};
Stack<int> intStack;
Stack<string> strStack;
```

---

**Q14. What is the Standard Template Library (STL)?**
The **STL** is a powerful collection of ready-to-use, generic C++ template classes and functions for common data structures and algorithms.

**Key STL components:**

| Component | Examples |
|-----------|---------|
| Containers | `vector`, `list`, `deque`, `stack`, `queue`, `set`, `map`, `unordered_map` |
| Algorithms | `sort()`, `find()`, `binary_search()`, `reverse()`, `count()` |
| Iterators | Point to elements in containers, enabling traversal |

```cpp
#include <vector>
#include <algorithm>
vector<int> v = {5, 2, 8, 1, 9};
sort(v.begin(), v.end());  // v = {1, 2, 5, 8, 9}
```

---

**Q15. What is the difference between `vector` and an array in C++?**

| Feature | Array | `std::vector` |
|---------|-------|--------------|
| Size | Fixed at compile time | Dynamic; grows/shrinks at runtime |
| Bounds checking | None (unsafe) | `.at()` method does bounds checking |
| STL algorithms | Manual | Directly compatible |
| Memory management | Manual (if dynamic) | Automatic |
| Functions | None | `.push_back()`, `.size()`, `.erase()`, etc. |

Always prefer `vector` over arrays in modern C++ unless you have a specific performance need for raw arrays.

---

**Q16. What is exception handling in C++? Explain `try`, `throw`, `catch`.**

```cpp
#include <stdexcept>

double divide(double a, double b) {
    if (b == 0)
        throw std::invalid_argument("Cannot divide by zero!");
    return a / b;
}

int main() {
    try {
        cout << divide(10, 0);       // Throws exception
    }
    catch (const std::invalid_argument &e) {
        cout << "Error: " << e.what(); // Caught here
    }
    catch (...) {
        cout << "Unknown error!";    // Catches any other exception
    }
    return 0;
}
```

- **`try`:** Marks the guarded block of code.
- **`throw`:** Raises (throws) an exception object.
- **`catch`:** Handles a specific type of exception.

---

**Q17. What is namespace in C++? Why is `using namespace std;` used?**
A **namespace** is a declarative region that provides a scope to identifiers (names of types, functions, variables) to avoid naming conflicts.

```cpp
namespace MathLib { double PI = 3.14159; }
namespace PhysicsLib { double PI = 3.14159265; }

// Access unambiguously:
cout << MathLib::PI;
cout << PhysicsLib::PI;
```

**`using namespace std;`** brings all names from the `std` (Standard) namespace into scope, so you can write `cout` instead of `std::cout` and `string` instead of `std::string`. While convenient for small programs, it can cause naming conflicts in large projects.

---

**Q18. What are `new` and `delete` operators in C++?**
`new` and `delete` are C++ operators for dynamic memory management on the heap:

```cpp
// Allocate a single integer
int *p = new int(42);  // Allocates memory + initializes to 42
delete p;              // Frees memory

// Allocate an array
int *arr = new int[10]; // Allocate array of 10 ints
arr[0] = 5;
delete[] arr;          // Use delete[] for arrays, NOT delete

p = nullptr;   // Good practice: prevent dangling pointer
arr = nullptr;
```

**Key difference from C's `malloc`/`free`:** `new`/`delete` automatically call constructors/destructors, making them the correct choice in C++.

---

**Q19. What is the difference between `struct` and `class` in C++?**
In C++, `struct` and `class` are almost identical — both can have member functions, constructors, destructors, inheritance, and access specifiers. The **only difference** is the default access level:

| Feature | `struct` | `class` |
|---------|---------|---------|
| Default access | `public` | `private` |
| Default inheritance mode | `public` | `private` |

**Convention:** Use `struct` for simple data holders (POD — Plain Old Data). Use `class` for entities with behavior, invariants, and data hiding.

---

**Q20. What is `inline` function? What are its advantages?**
An `inline` function is a suggestion to the compiler to insert the function's body directly at the call site instead of performing a regular function call (which involves creating a stack frame, jumping, returning, etc.).

```cpp
inline int square(int x) { return x * x; }

// Calling square(5) is treated like writing 5*5 directly
cout << square(5);  // Likely compiled as: cout << (5 * 5);
```

**Advantages:**
- Eliminates function call overhead (for very small functions called frequently).
- Can improve cache performance.

**Disadvantages:**
- Increases code size (code bloat) if overused.
- The compiler may ignore the `inline` suggestion for complex functions.

---


# 🐍 SUBJECT 6: Python

**Q1. What is Python? What are its key features?**
**Python** is a high-level, interpreted, dynamically-typed, general-purpose programming language created by Guido van Rossum and released in 1991. Its design philosophy emphasizes code readability using significant whitespace indentation.

**Key Features:**
- **Easy to learn:** Clean, English-like syntax.
- **Interpreted:** Runs line by line; no separate compilation step needed.
- **Dynamically typed:** No need to declare variable types explicitly.
- **Garbage collected:** Automatic memory management.
- **Huge standard library:** "Batteries included" philosophy.
- **Versatile:** Used in web development (Django/Flask), data science, AI/ML, automation, scripting, and more.

---

**Q2. How do you declare variables in Python? What is dynamic typing?**
In Python, you do not need to declare a variable's type. Just assign a value and Python infers the type automatically.

```python
name = "Raju"          # str
age = 21               # int
gpa = 9.2              # float
is_student = True      # bool
grades = [9, 8, 7]     # list

# Dynamic typing: a variable can change type
x = 10          # x is int
x = "Hello"     # Now x is str — perfectly valid in Python
x = [1, 2, 3]  # Now x is list

# Check type anytime
print(type(x))  # <class 'list'>
```

---

**Q3. What are Python's built-in data types?**

| Category | Data Types |
|---------|-----------|
| **Numeric** | `int`, `float`, `complex` |
| **Boolean** | `bool` (`True` / `False`) |
| **Sequence** | `str`, `list`, `tuple`, `range` |
| **Mapping** | `dict` |
| **Set** | `set`, `frozenset` |
| **Binary** | `bytes`, `bytearray` |
| **None** | `NoneType` (`None`) |

```python
x = 10          # int
y = 3.14        # float
s = "Python"    # str
l = [1, 2, 3]  # list
t = (1, 2, 3)  # tuple
d = {"a": 1}   # dict
st = {1, 2, 3} # set
n = None        # NoneType
```

---

**Q4. What is the difference between a list, tuple, and set?**

| Feature | List | Tuple | Set |
|---------|------|-------|-----|
| Syntax | `[1, 2, 3]` | `(1, 2, 3)` | `{1, 2, 3}` |
| Mutable | ✅ Yes | ❌ No | ✅ Yes |
| Ordered | ✅ Yes | ✅ Yes | ❌ No |
| Allows Duplicates | ✅ Yes | ✅ Yes | ❌ No |
| Indexable | ✅ Yes | ✅ Yes | ❌ No |
| Use case | General-purpose dynamic collection | Fixed data, dictionary key | Unique elements, set operations |

```python
my_list = [1, 2, 2, 3]   # Allows duplicates, ordered
my_tuple = (1, 2, 3)      # Immutable; use for fixed records
my_set = {1, 2, 2, 3}     # → {1, 2, 3} (duplicates removed)
```

---

**Q5. What is a dictionary in Python? How do you create and use one?**
A **dictionary** is an unordered collection of **key-value pairs**, where each key is unique and maps to a value. It provides O(1) average-time lookups.

```python
# Create a dictionary
student = {
    "name": "Raju",
    "age": 21,
    "branch": "BCA",
    "cgpa": 9.2
}

# Access value by key
print(student["name"])       # Raju
print(student.get("age"))    # 21 (.get() returns None if key missing)

# Add / Update
student["email"] = "raju@example.com"  # Add new key-value
student["age"] = 22                     # Update existing

# Delete
del student["cgpa"]

# Loop through
for key, value in student.items():
    print(f"{key}: {value}")

# Check if key exists
if "name" in student:
    print("Key found!")
```

---

**Q6. What are Python control flow statements? Explain with examples.**

**if-elif-else:**
```python
marks = 85
if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")   # This runs
else:
    print("Grade C")
```

**for loop:** Iterates over any iterable (list, string, range, dict, etc.)
```python
for i in range(1, 6):  # 1 to 5
    print(i, end=" ")  # 1 2 3 4 5
```

**while loop:**
```python
count = 0
while count < 5:
    print(count, end=" ")
    count += 1          # 0 1 2 3 4
```

**break / continue:**
```python
for i in range(10):
    if i == 3: continue   # Skip 3
    if i == 7: break      # Stop at 7
    print(i, end=" ")     # 0 1 2 4 5 6
```

---

**Q7. What are functions in Python? How do you define and call one?**

```python
# Define a function
def greet(name, greeting="Hello"):  # 'greeting' has a default value
    """This is a docstring — documents the function."""
    return f"{greeting}, {name}!"

# Call the function
print(greet("Raju"))             # Hello, Raju!
print(greet("Priya", "Namaste")) # Namaste, Priya!

# Return multiple values
def min_max(lst):
    return min(lst), max(lst)

lo, hi = min_max([3, 1, 9, 2, 7])
print(lo, hi)  # 1 9
```

Functions are **first-class citizens** in Python — they can be passed as arguments, returned from other functions, and assigned to variables.

---

**Q8. What is a lambda function? Give examples.**
A **lambda** is a small, anonymous, one-line function using the `lambda` keyword. It can take multiple arguments but only has one expression (which is implicitly returned).

```python
# Syntax: lambda arguments: expression
square = lambda x: x ** 2
print(square(5))  # 25

add = lambda a, b: a + b
print(add(3, 4))  # 7

# Most useful when passed as argument to higher-order functions:
numbers = [5, 2, 9, 1, 7]
numbers.sort(key=lambda x: x)         # Sort ascending
print(numbers)  # [1, 2, 5, 7, 9]

words = ["banana", "apple", "cherry"]
words.sort(key=lambda s: len(s))      # Sort by string length
print(words)  # ['apple', 'banana', 'cherry']
```

---

**Q9. What are list comprehensions? Why are they useful?**
A **list comprehension** is a concise, Pythonic way to create a new list by applying an expression to each element of an iterable, with an optional filter.

**Syntax:** `[expression for item in iterable if condition]`

```python
# Traditional for-loop approach
squares = []
for x in range(1, 11):
    if x % 2 == 0:
        squares.append(x**2)

# List comprehension — same result in one line:
squares = [x**2 for x in range(1, 11) if x % 2 == 0]
print(squares)  # [4, 16, 36, 64, 100]

# Other examples:
upper = [word.upper() for word in ["apple", "banana", "cherry"]]
flat = [x for row in [[1,2], [3,4], [5,6]] for x in row]  # Flatten 2D list
```

---

**Q10. What is a module in Python? How do you import one?**
A **module** is a Python file (`.py`) containing functions, classes, and variables that can be imported and reused in other programs.

```python
# Importing the full module
import math
print(math.pi)           # 3.141592653589793
print(math.sqrt(16))     # 4.0

# Import specific items
from math import pi, sqrt, factorial
print(factorial(5))      # 120

# Import with alias
import numpy as np        # Common for large libraries
arr = np.array([1, 2, 3])

# Import everything (not recommended — pollutes namespace)
from math import *
```

**Built-in modules:** `math`, `os`, `sys`, `datetime`, `random`, `json`, `re`, `collections`, etc.

---

**Q11. What is the difference between `append()`, `extend()`, and `insert()` in a list?**

```python
a = [1, 2, 3]

# append(): Adds a SINGLE element to the end
a.append(4)           # [1, 2, 3, 4]
a.append([5, 6])      # [1, 2, 3, 4, [5, 6]]  ← list added as one element

b = [1, 2, 3]
# extend(): Unpacks an iterable and adds each element individually
b.extend([4, 5])      # [1, 2, 3, 4, 5]
b.extend("Hi")        # [1, 2, 3, 4, 5, 'H', 'i']  ← iterates over string

c = [1, 2, 3]
# insert(index, value): Inserts at a specific position
c.insert(1, 99)       # [1, 99, 2, 3]
c.insert(0, 0)        # [0, 1, 99, 2, 3]
```

---

**Q12. How does exception handling work in Python?**

```python
try:
    # Code that might raise an exception
    numerator = int(input("Enter number: "))
    result = 100 / numerator
except ValueError:
    # Runs if user enters non-integer
    print("Please enter a valid integer.")
except ZeroDivisionError:
    # Runs if user enters 0
    print("Cannot divide by zero!")
except Exception as e:
    # Catches any other exception
    print(f"Unexpected error: {e}")
else:
    # Runs ONLY if no exception occurred
    print(f"Result: {result}")
finally:
    # ALWAYS runs, exception or not (good for cleanup)
    print("Program finished.")
```

**Common built-in exceptions:** `ValueError`, `TypeError`, `IndexError`, `KeyError`, `FileNotFoundError`, `AttributeError`, `ZeroDivisionError`.

---

**Q13. What is the difference between `is` and `==`?**

```python
# == checks VALUE equality
a = [1, 2, 3]
b = [1, 2, 3]
print(a == b)   # True  — same values

# is checks IDENTITY (same object in memory)
print(a is b)   # False — different objects at different memory addresses

c = a           # c is just another reference to the SAME object
print(a is c)   # True  — same object

# Python caches small integers and short strings:
x = 5; y = 5
print(x is y)   # True  (CPython optimization: cached integers -5 to 256)
```

**Rule:** Use `==` to compare values. Use `is` only to check for `None` (e.g., `if x is None:`).

---

**Q14. What are `*args` and `**kwargs`?**
They allow functions to accept a variable number of arguments:

```python
# *args: Collects extra positional arguments into a TUPLE
def total(*args):
    print(type(args))  # <class 'tuple'>
    return sum(args)

print(total(1, 2, 3, 4, 5))  # 15

# **kwargs: Collects extra keyword arguments into a DICT
def display(**kwargs):
    print(type(kwargs))  # <class 'dict'>
    for key, val in kwargs.items():
        print(f"{key} = {val}")

display(name="Raju", age=21, city="Chennai")

# Combining both:
def demo(a, b, *args, **kwargs):
    print(a, b, args, kwargs)

demo(1, 2, 3, 4, 5, x=10, y=20)
# Output: 1 2 (3, 4, 5) {'x': 10, 'y': 20}
```

---

**Q15. What is a class and object in Python? Write a simple OOP example.**

```python
class BankAccount:
    # Class variable (shared by all instances)
    bank_name = "Python Bank"
    
    # Constructor (__init__)
    def __init__(self, owner, balance=0):
        self.owner = owner        # Instance variable
        self.balance = balance    # Instance variable
    
    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited ₹{amount}. Balance: ₹{self.balance}")
    
    def withdraw(self, amount):
        if amount > self.balance:
            print("Insufficient funds!")
        else:
            self.balance -= amount
            print(f"Withdrew ₹{amount}. Balance: ₹{self.balance}")
    
    def __str__(self):  # String representation
        return f"Account({self.owner}, ₹{self.balance})"

# Create objects
acc1 = BankAccount("Raju", 1000)
acc1.deposit(500)    # "Deposited ₹500. Balance: ₹1500"
acc1.withdraw(200)   # "Withdrew ₹200. Balance: ₹1300"
print(acc1)          # "Account(Raju, ₹1300)"
```

---

**Q16. What are Python decorators? Give a simple example.**
A **decorator** is a function that wraps another function to modify or extend its behavior without changing its original code.

```python
# Define a decorator
def timer_decorator(func):
    import time
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)           # Call the original function
        end = time.time()
        print(f"{func.__name__} took {end-start:.4f} seconds")
        return result
    return wrapper

# Apply decorator using @ syntax
@timer_decorator
def slow_sum(n):
    return sum(range(n))

result = slow_sum(1000000)
# Automatically prints: "slow_sum took 0.0421 seconds"
```

**Common built-in decorators:** `@staticmethod`, `@classmethod`, `@property`.

---

**Q17. What is a generator in Python? How is it different from a regular function?**
A **generator** is a function that uses the `yield` keyword instead of `return`. It produces values one at a time, pausing and resuming execution — making it extremely memory-efficient for large sequences.

```python
# Regular function — creates entire list in memory at once
def normal_range(n):
    result = []
    for i in range(n): result.append(i)
    return result  # Creates list of 1M items in memory

# Generator — produces values one at a time (lazy evaluation)
def gen_range(n):
    for i in range(n):
        yield i    # Pauses here, returns i, resumes on next() call

# Only one value exists in memory at a time!
gen = gen_range(1000000)
print(next(gen))   # 0
print(next(gen))   # 1
# or use in for loop:
for val in gen_range(5):
    print(val)     # 0, 1, 2, 3, 4
```

---

**Q18. What is file handling in Python?**

```python
# WRITE to a file
with open("data.txt", "w") as f:
    f.write("Hello, Raju!\n")
    f.write("Python file handling.\n")

# READ entire file
with open("data.txt", "r") as f:
    content = f.read()
    print(content)

# READ line by line (memory efficient for large files)
with open("data.txt", "r") as f:
    for line in f:
        print(line.strip())

# APPEND to existing file
with open("data.txt", "a") as f:
    f.write("Appended line.\n")
```

**File modes:** `"r"` read, `"w"` write (overwrites), `"a"` append, `"rb"` binary read, `"x"` create (fails if exists).
**Always use `with` —** it guarantees the file is closed even if an error occurs.

---

**Q19. What are Python's string methods? List the most important ones.**

```python
s = "  Hello, World!  "

# Case methods
s.upper()       # "  HELLO, WORLD!  "
s.lower()       # "  hello, world!  "
s.title()       # "  Hello, World!  "

# Strip whitespace
s.strip()       # "Hello, World!"  (both sides)
s.lstrip()      # "Hello, World!  " (left only)
s.rstrip()      # "  Hello, World!" (right only)

# Search
s.find("World")    # Returns index of first occurrence (8)
s.count("l")       # Returns count of "l" in string (3)
"World" in s       # True

# Replace & Split
s.replace("World", "Python")  # "  Hello, Python!  "
"a,b,c".split(",")             # ['a', 'b', 'c']
", ".join(["a", "b", "c"])     # "a, b, c"

# Check
"123".isdigit()    # True
"abc".isalpha()    # True
s.startswith("  Hello")  # True
```

---

**Q20. What is the difference between shallow copy and deep copy?**

```python
import copy

original = [[1, 2, 3], [4, 5, 6]]

# Shallow Copy: copies the outer list, but inner lists are SHARED references
shallow = copy.copy(original)
shallow[0].append(99)
print(original)  # [[1, 2, 3, 99], [4, 5, 6]] ← original CHANGED!

# Deep Copy: recursively copies everything — completely independent
original2 = [[1, 2, 3], [4, 5, 6]]
deep = copy.deepcopy(original2)
deep[0].append(99)
print(original2) # [[1, 2, 3], [4, 5, 6]] ← original UNCHANGED!
```

**Rule of thumb:**
- Use **shallow copy** when object contains only immutable elements (int, str, tuples).
- Use **deep copy** when object contains mutable nested objects (like lists inside lists).

---


# 📊 SUBJECT 7: Data Structures and Algorithms (DSA)

**Q1. What is a Data Structure? Why is it important?**
A **data structure** is a particular way of organizing and storing data in memory so that it can be accessed and used efficiently. The right choice of data structure can make the difference between a program that runs in milliseconds and one that takes hours.

**Why important?**
- Every program deals with data — how you store and organize it determines how fast you can find, insert, or delete it.
- Different problems require different data structures (e.g., a stack for undo functionality, a queue for print spooling, a hash table for a phone book).
- Understanding data structures is fundamental to writing efficient algorithms.

---

**Q2. What is an Algorithm? What are the properties of a good algorithm?**
An **algorithm** is a finite, step-by-step procedure to solve a specific problem. It is independent of any programming language.

**Properties of a good algorithm:**
- **Correctness:** Produces the correct output for all valid inputs.
- **Finiteness:** Terminates after a finite number of steps.
- **Definiteness:** Each step is precisely and unambiguously defined.
- **Input/Output:** Has zero or more inputs and at least one output.
- **Efficiency:** Uses minimal time (time complexity) and memory (space complexity).
- **Generality:** Solves a broad class of problems, not just one specific case.

---

**Q3. What is Big O notation? Explain the common complexities.**
**Big O notation** describes the worst-case growth rate of an algorithm's time or space requirement as the input size `n` grows. It helps compare algorithm efficiency independent of hardware.

| Big O | Name | Example |
|-------|------|---------|
| O(1) | Constant | Accessing array element by index |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Linear search, traversing array |
| O(n log n) | Linearithmic | Merge sort, quick sort (avg) |
| O(n²) | Quadratic | Bubble sort, nested loops |
| O(2ⁿ) | Exponential | Recursive Fibonacci (naive) |
| O(n!) | Factorial | Generating all permutations |

**From fastest to slowest:** O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ) < O(n!)

---

**Q4. What is an Array? What are its advantages and disadvantages?**
An **array** is a collection of elements of the same data type stored in contiguous memory locations, accessible by an index.

**Advantages:**
- **O(1) random access:** Directly access any element by index (e.g., `arr[5]`).
- **Cache-friendly:** Contiguous memory means good cache performance.
- **Simple:** Easy to implement and understand.

**Disadvantages:**
- **Fixed size:** Size must be defined at creation (in static arrays).
- **Slow insert/delete in middle:** Requires shifting all subsequent elements — O(n).
- **Wasted space:** May allocate more than needed (or need costly resizing).

---

**Q5. What is a Linked List? Name its types.**
A **Linked List** is a linear data structure where elements (called **nodes**) are stored in non-contiguous memory locations. Each node contains a **data field** and a **pointer** to the next node.

```
[Data|Next] → [Data|Next] → [Data|Next] → NULL
  Head
```

**Types:**
- **Singly Linked List:** Each node points to the next node only. Traversal is one-way.
- **Doubly Linked List:** Each node has pointers to both the next AND previous node. Traversal is two-way.
- **Circular Linked List:** The last node's pointer connects back to the head, forming a circle (singly or doubly).

---

**Q6. How does a Linked List compare to an Array?**

| Feature | Array | Linked List |
|---------|-------|------------|
| Memory | Contiguous | Non-contiguous (scattered) |
| Random Access | O(1) by index | O(n) — must traverse |
| Insert at beginning | O(n) — shift elements | O(1) — just update pointer |
| Insert at end | O(1)* | O(n)** |
| Delete at beginning | O(n) | O(1) |
| Memory Overhead | Low | Higher (extra pointer per node) |
| Cache Performance | Excellent | Poor (pointer chasing) |

*Amortized for dynamic arrays. **O(1) if tail pointer maintained.

---

**Q7. What is a Stack? Explain with a real-world example.**
A **Stack** is a linear data structure that follows the **LIFO (Last In, First Out)** principle — the last item added is the first to be removed, like a stack of plates.

**Primary Operations (all O(1)):**
- **Push:** Add an element to the top.
- **Pop:** Remove the top element.
- **Peek/Top:** View the top element without removing it.
- **isEmpty:** Check if the stack is empty.

**Real-world examples:**
- **Browser back button:** Pages you visit are pushed; back button pops them.
- **Undo function (Ctrl+Z):** Each action is pushed; undo pops the last action.
- **Function call stack:** When you call a function, its context is pushed; when it returns, it's popped.
- **Balanced parentheses checker:** Push opening brackets, pop when closing bracket found.

---

**Q8. What is a Queue? How is it different from a Stack?**
A **Queue** is a linear data structure that follows the **FIFO (First In, First Out)** principle — the first item added is the first to be removed, like a queue at a ticket counter.

**Primary Operations:**
- **Enqueue:** Add an element to the rear.
- **Dequeue:** Remove an element from the front.
- **Front:** View the front element.

| Feature | Stack | Queue |
|---------|-------|-------|
| Principle | LIFO | FIFO |
| Insert from | Top | Rear |
| Remove from | Top | Front |
| Example | Undo history | Printer queue |

**Types of Queues:** Simple Queue, Circular Queue, Priority Queue, Deque (Double-Ended Queue).

---

**Q9. What is a Binary Tree? Define the key terms.**
A **Binary Tree** is a hierarchical tree-based data structure where each node has at most **two children**, referred to as the **left child** and the **right child**.

**Key Terms:**
- **Root:** The topmost node with no parent.
- **Leaf Node:** A node with no children.
- **Parent/Child:** A node connected above/below another node.
- **Height of tree:** The number of edges on the longest path from root to a leaf.
- **Depth of a node:** The number of edges from the root to that node.
- **Subtree:** A node and all its descendants.

```
        10        ← Root
       /  \
      5    20     ← Internal Nodes
     / \     \
    3   7     25  ← Leaf Nodes (3, 7, 25)
```

---

**Q10. What is a Binary Search Tree (BST)? What are its properties?**
A **Binary Search Tree** is a binary tree with an important ordering property:
- For every node, all values in the **left subtree are smaller** than the node's value.
- For every node, all values in the **right subtree are greater** than the node's value.
- This property holds recursively for every node.

This ordering enables **efficient search, insert, and delete operations**.

```
        50
       /  \
      30   70
     / \   / \
    20 40 60  80
```

**Average Time Complexity:** Search, Insert, Delete → O(log n)
**Worst Case (skewed tree):** O(n)

---

**Q11. What are the tree traversal methods?**
Tree traversal is the process of visiting every node in a specific order. For a binary tree, three systematic DFS traversals exist:

- **In-Order (Left → Root → Right):** Visits nodes in ascending sorted order in a BST.
- **Pre-Order (Root → Left → Right):** Used to make a copy/serialize the tree.
- **Post-Order (Left → Right → Root):** Used to delete a tree (process children before parent).

```
    Tree:    1
            / \
           2   3
          / \
         4   5

In-Order:   4 → 2 → 5 → 1 → 3
Pre-Order:  1 → 2 → 4 → 5 → 3
Post-Order: 4 → 5 → 2 → 3 → 1
```

**Level-Order (BFS):** Visits nodes level by level using a Queue: 1 → 2 → 3 → 4 → 5

---

**Q12. What is a Hash Table (Hash Map)? How does it work?**
A **Hash Table** is a data structure that maps **keys to values** for extremely fast lookups — O(1) average case. It uses a **hash function** to compute an index (called a hash code) into a fixed-size array of slots, where the value is stored.

```
key: "Raju"  →  hash("Raju")  →  index 4  →  store value at arr[4]
```

**Collision:** When two different keys hash to the same index.

**Collision Resolution:**
- **Chaining:** Each slot holds a linked list of all key-value pairs that hashed to that index.
- **Open Addressing (Linear Probing):** If the slot is occupied, look linearly for the next empty slot.

**Real-world uses:** Python dictionaries, database indexes, caches, phone books.

---

**Q13. What is sorting? Name the common sorting algorithms.**
**Sorting** is the process of arranging elements in a specific order (ascending or descending). It is one of the most fundamental operations in computer science as many other algorithms work on sorted data.

| Algorithm | Best | Average | Worst | Stable? | Notes |
|-----------|------|---------|-------|---------|-------|
| Bubble Sort | O(n) | O(n²) | O(n²) | ✅ | Simple, used for learning |
| Selection Sort | O(n²) | O(n²) | O(n²) | ❌ | Min selections |
| Insertion Sort | O(n) | O(n²) | O(n²) | ✅ | Good for nearly sorted data |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | ✅ | Consistent, uses extra space |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | ❌ | Fastest in practice, in-place |
| Heap Sort | O(n log n) | O(n log n) | O(n log n) | ❌ | Uses heap structure |

---

**Q14. Explain Bubble Sort with an example.**
**Bubble Sort** repeatedly steps through the list and compares adjacent elements. If they are in the wrong order, they are swapped. Larger elements "bubble up" to the end with each pass.

```
Array: [64, 34, 25, 12, 22]

Pass 1: [34, 25, 12, 22, 64]  ← 64 bubbled to end
Pass 2: [25, 12, 22, 34, 64]  ← 34 bubbled to correct place
Pass 3: [12, 22, 25, 34, 64]
Pass 4: [12, 22, 25, 34, 64]  (no swaps = sorted!)

Time: O(n²) | Space: O(1) | Stable: Yes
```

**Use case:** Only practical for educational purposes or tiny datasets. For real use, prefer Merge Sort or Quick Sort.

---

**Q15. What is searching? Explain Linear Search and Binary Search.**

**Linear Search:** Checks every element one by one until the target is found.
- **Time:** O(n) | Works on **unsorted** arrays.

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # Found at index i
    return -1  # Not found
```

**Binary Search:** Divides the array in half each time, eliminating half the remaining elements.
- **Time:** O(log n) | **Requires sorted array.**

```python
def binary_search(arr, target):
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = (lo + hi) // 2
        if arr[mid] == target: return mid
        elif arr[mid] < target: lo = mid + 1
        else: hi = mid - 1
    return -1
```

---

**Q16. What is recursion? How does the call stack work with recursion?**
**Recursion** is when a function calls itself to solve a smaller subproblem. Each call adds a new **stack frame** to the call stack, which stores local variables and return address.

```python
def factorial(n):
    if n == 0: return 1       # Base case — stop recursion
    return n * factorial(n-1) # Recursive case

# Call stack for factorial(3):
# factorial(3) → 3 * factorial(2)
#                     2 * factorial(1)
#                             1 * factorial(0)
#                                     1 (base case)
# Unwinds: 1 → 1 → 2 → 6
```

**Two essential parts:**
1. **Base Case:** Termination condition — prevents infinite recursion.
2. **Recursive Case:** Makes the problem smaller each step.

**Warning:** Too many recursive calls → Stack Overflow!

---

**Q17. What is a Graph? Explain with a real-life example.**
A **Graph** is a non-linear data structure consisting of:
- **Vertices (V):** Nodes/points (e.g., cities)
- **Edges (E):** Connections between nodes (e.g., roads between cities)

**Real-life examples:** Google Maps (cities as vertices, roads as edges), Social networks (users as vertices, friendships as edges), the Internet (routers as vertices, links as edges).

**Types:**
- **Directed Graph (Digraph):** Edges have a direction (A → B but not B → A). Example: Twitter follows, one-way streets.
- **Undirected Graph:** Edges have no direction (A—B means both can reach each other). Example: Facebook friends.
- **Weighted Graph:** Edges have associated weights (e.g., road distances or travel costs).

---

**Q18. What is the difference between BFS and DFS?**
Both are graph traversal algorithms that visit all vertices of a graph:

| Feature | BFS (Breadth-First Search) | DFS (Depth-First Search) |
|---------|--------------------------|--------------------------|
| Data Structure | Queue | Stack (or recursion) |
| Traversal Style | Level by level | As deep as possible before backtracking |
| Shortest Path | ✅ Finds shortest path (unweighted) | ❌ Not guaranteed |
| Memory | More (stores all nodes at current level) | Less |
| Use Cases | Shortest path, social network "degrees of separation" | Topological sort, maze solving, cycle detection |

**BFS:** Start → visit all neighbors → visit their neighbors → ...
**DFS:** Start → go deep on first neighbor → backtrack → go deep on next neighbor → ...

---

**Q19. What is Dynamic Programming (DP)?**
**Dynamic Programming** is an algorithmic optimization technique for solving problems that have:
1. **Overlapping Subproblems:** The same smaller subproblems are solved repeatedly (unlike Divide & Conquer where subproblems are independent).
2. **Optimal Substructure:** The optimal solution can be built from optimal solutions to its subproblems.

DP solves each subproblem **once** and stores the result to avoid redundant computation.

**Two approaches:**
- **Memoization (Top-Down):** Use recursion but cache results in a memo table.
- **Tabulation (Bottom-Up):** Iteratively fill a DP table from the smallest subproblem up.

**Classic DP Problems:** Fibonacci numbers, Longest Common Subsequence, Knapsack problem, Shortest Path.

---

**Q20. What is a Heap data structure? Explain Min-Heap and Max-Heap.**
A **Heap** is a specialized **complete binary tree** that satisfies the **Heap Property**. It is typically stored as an array (parent at index `i`, left child at `2i+1`, right child at `2i+2`).

- **Max-Heap:** Parent node ≥ both children. The maximum element is always at the root.
  ```
       90
      /  \
    80    70
   / \   / \
  60 50 40  30
  ```

- **Min-Heap:** Parent node ≤ both children. The minimum element is always at the root.

**Key operations:**
- `insert`: Add element → O(log n) (heapify up)
- `extract-max/min`: Remove root → O(log n) (heapify down)
- `peek`: View max/min → O(1)

**Applications:** Priority Queues, Heap Sort, Dijkstra's shortest path algorithm, scheduling systems.

---

> ✅ **End of Set 3 — 20 Easy Questions per Subject**
>
> 📚 **Covered Subjects (20 Questions Each):**
> 1. Computer Networks
> 2. DBMS
> 3. Operating Systems
> 4. C Programming
> 5. C++
> 6. Python
> 7. DSA
>
> 💡 **Tip:** Understand each concept deeply rather than memorizing. Sketch diagrams for tree/graph questions. Write code on paper for programming questions. Good luck! 🚀

