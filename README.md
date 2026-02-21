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
