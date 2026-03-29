# File Permissions Management 
## Managing Authorization 

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Environment** | Linux CLI |
| **Commands Used** | ls -la, chmod |
| **Objective** | Examine and update file system permissions to ensure users are authorised appropriately |

---

## Project Description

As a security professional working with a research team 
at a large organisation, part of the role involves 
ensuring that users have the correct permissions on the 
file system — no more and no less than what their role 
requires. This directly supports the principle of least 
privilege, a core security control that limits access 
to only what is necessary for each user to perform 
their job.

This lab involves examining existing permissions on the 
file system, determining whether they match the intended 
authorisation levels, and using `chmod` to correct any 
mismatches — removing unauthorised access and granting 
appropriate permissions where missing.

---

## Understanding the 10-Character Permission String

Before modifying permissions, it is essential to 
correctly interpret what the existing permissions show. 
Every file and directory in Linux displays a 
10-character permission string when viewed with 
`ls -la`.
```
-rwxr-xr--
```

| Position | Character | Meaning |
|----------|-----------|---------|
| 1 | `-` or `d` | File type — `-` = file, `d` = directory |
| 2–4 | `rwx` | Owner permissions — read, write, execute |
| 5–7 | `r-x` | Group permissions — read, write, execute |
| 8–10 | `r--` | Other permissions — read, write, execute |

Each position uses:
- `r` — read permission granted
- `w` — write permission granted
- `x` — execute permission granted
- `-` — permission not granted

Misinterpreting this string leads to incorrect 
permission changes — which can either leave 
vulnerabilities open or break legitimate access. 
Reading it accurately is the first step before 
any modification.

---

## Step 1 — Check Existing File and Directory Permissions

The first step is to examine the current state of 
permissions across the file system using `ls -la`.

![Checking existing permissions with ls -la](./linux-screenshot1.png)
```bash
ls -la
```

The `-l` flag displays the long format — showing the 
permission string, ownership, file size, and last 
modification date for every item. The `-a` flag ensures 
hidden files are included in the output. Hidden files 
begin with a `.` prefix and are not shown by a standard 
`ls` command.

This step establishes the baseline — what permissions 
currently exist before any changes are made. Every 
permission modification in the following steps is 
based on what this output reveals. Any file showing 
broader access than the role requires is a candidate 
for immediate remediation.

---

## Step 2 — Remove Write Permission from Other on project_k.txt

**Issue identified:** `project_k.txt` had write 
permission granted to other — meaning any user outside 
the owner and group could modify the file. This 
exceeded the authorisation level required and posed 
a direct risk to data integrity.

![Removing write permission from other on project_k.txt](./linux-screenshot2.png)
```bash
chmod o-w project_k.txt
```

**Command breakdown:**
- `o` — targets other — all users outside the owner 
and group
- `-` — removes the specified permission
- `w` — write permission

Removing write access from other ensures that only 
authorised users — the file owner and group members — 
can modify `project_k.txt`. Unauthorised users retain 
no ability to alter the file's contents.

---

## Step 3 — Remove Read Permission from Group on project_m.txt

**Issue identified:** `project_m.txt` had read 
permission granted to the group. This file contains 
research data that the group should not have visibility 
into based on their authorisation level.

![Removing read permission from group on project_m.txt](./linux-screenshot3.png)
```bash
chmod g-r project_m.txt
```

**Command breakdown:**
- `g` — targets the group
- `-` — removes the specified permission
- `r` — read permission

Removing group read access ensures that only the file 
owner can view the contents of `project_m.txt`. Group 
members no longer have any visibility into this file, 
aligning permissions with the correct authorisation 
level for this research document.

---

## Step 4 — Update Permissions on Hidden File .project_x.txt

**Issue identified:** `.project_x.txt` is a hidden 
file — indicated by the `.` prefix — with write 
permissions granted to both the user and group, and 
insufficient read access for the group. Hidden files 
carry the same security risk as visible files when 
misconfigured and must not be overlooked in a 
permissions review.

![Updating permissions on hidden file .project_x.txt](./linux-screenshot4.png)
```bash
chmod u-w,g-w,g+r .project_x.txt
```

**Command breakdown:**
- `u-w` — removes write permission from the user
- `g-w` — removes write permission from the group
- `g+r` — adds read permission for the group

Multiple permission changes are applied in a single 
command by separating them with a comma. This ensures 
all modifications are applied together, avoiding any 
intermediate state where the file is partially 
configured and temporarily insecure.

The `.` prefix in `.project_x.txt` designates it as 
a hidden file. It does not appear in a standard `ls` 
output — only when `ls -la` is used with the `-a` 
flag. From a security standpoint hidden files must 
always be included in permission reviews. They are 
only hidden from casual directory listings, not from 
users with appropriate access.

---

## Step 5 — Remove Execute Permission from Group on drafts Directory

**Issue identified:** The `drafts` directory had 
execute permission granted to the group. Execute 
permission on a directory controls whether a user 
can navigate into it and access its contents. The 
group did not require this level of access to the 
drafts directory based on their role.

![Removing execute permission from group on drafts directory](./linux-screenshot5.png)
```bash
chmod g-x drafts
```

**Command breakdown:**
- `g` — targets the group
- `-` — removes the specified permission
- `x` — execute permission

Removing group execute access on the `drafts` 
directory prevents group members from navigating 
into it. Even if a group member holds read 
permission on the directory, without execute 
permission they cannot `cd` into it or access 
any files contained within.

---

## Summary

This lab examined existing file system permissions 
for a research team and applied targeted modifications 
to align them with correct authorisation levels. The 
following actions were completed:

| Step | File / Directory | Action |
|------|-----------------|--------|
| 1 | All files | Reviewed existing permissions with `ls -la` |
| 2 | `project_k.txt` | Removed write permission from other — `o-w` |
| 3 | `project_m.txt` | Removed read permission from group — `g-r` |
| 4 | `.project_x.txt` | Removed write from user and group, added read for group — `u-w,g-w,g+r` |
| 5 | `drafts` | Removed execute permission from group — `g-x` |

Correct permission management is a direct application 
of the principle of least privilege. Ensuring users 
have only the access they need — and no more — reduces 
the attack surface and limits the potential damage 
from compromised accounts or insider threats. Hidden 
files and directories must always be included in any 
permissions review — misconfigured hidden files carry 
identical risk to visible ones.

---

*Completed by Amal Shaji — Google Cybersecurity 
Professional Certificate, Course 4: Tools of the 
Trade: Linux and SQL*
