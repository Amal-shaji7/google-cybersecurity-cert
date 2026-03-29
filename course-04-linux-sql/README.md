# Course 4 — Tools of the Trade: Linux and SQL

## Overview

This folder contains all deliverables completed during 
**Course 4: Tools of the Trade: Linux and SQL** of the 
Google Cybersecurity Professional Certificate.

This course covered two foundational tools used daily 
in cybersecurity operations — the Linux command line 
for system navigation and permission management, and 
SQL for querying and analysing security-relevant data. 
Both are core technical skills expected in SOC analyst 
and penetration testing roles.

---

## Contents

| Folder | Description |
|--------|-------------|
| `linux-labs/` | Linux file permission management — examining and updating authorisation using chmod and ls -la |
| `sql-labs/` | SQL security investigation — filtering login attempts and employee data using AND, OR, NOT, and LIKE operators |

---

## Key Concepts Covered

### Linux

- Linux file system navigation 
- File and directory permissions
- Reading and interpreting the permission 
string
- Modifying permissions 
- Managing hidden files and directories 
- Applying the principle of least privilege through 
permission management
- Managing users and groups 

### SQL

- Basic SELECT queries — retrieving data from single 
and multiple columns
- Filtering with WHERE using AND, OR, NOT operators
- Pattern matching with LIKE and `%` wildcard
- Joins — INNER JOIN and LEFT JOIN across related tables
- Sorting and grouping — ORDER BY, GROUP BY, HAVING
- Aggregate functions — COUNT, AVG, SUM, MIN, MAX
- Applying SQL in a security context — querying login 
attempt logs and employee access records

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Linux CLI | File navigation, permission management, user administration |
| SQL / MySQL | Database querying and security data analysis |

---

## Portfolio Projects

### Linux — File Permissions Management
Examined existing file system permissions for a research 
team and applied targeted modifications using `chmod` to 
align permissions with correct authorisation levels. 
Reviewed hidden files, adjusted read, write, and execute 
permissions across multiple files and directories, and 
applied the principle of least privilege throughout.

📁 [View Lab](./linux-labs/)

---

### SQL — Security Investigation Using Filters
Investigated potential security issues involving 
suspicious login activity and employee machine access 
by querying the organisation's `log_in_attempts` and 
`employees` tables. Wrote six targeted SQL queries 
applying AND, OR, NOT, LIKE, and comparison operators 
to retrieve specific datasets supporting the security 
review.

📁 [View Lab](./sql-labs/)

---

## Skills Demonstrated

- Linux command line proficiency for file navigation 
and permission management
- Reading and modifying Linux permission strings 
accurately
- Writing SQL queries to retrieve and filter 
security-relevant data
- Applying logical operators to isolate specific 
records in a security investigation
- Using pattern matching to handle inconsistent 
data entries in security logs
- Identifying suspicious patterns in login attempt 
and employee access data through targeted queries
- Applying the principle of least privilege in a 
real-world Linux environment

---

*Completed by Amal Shaji — Google Cybersecurity 
Professional Certificate, Course 4: Tools of the 
Trade: Linux and SQL*
