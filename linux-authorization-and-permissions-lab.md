# Linux Authorization and File Permissions Management

## Project Description
This project demonstrates how to manage authorization and file permissions in a Linux environment using Bash commands.

As part of a cybersecurity training scenario, the objective was to ensure that sensitive research files and directories in `/home/researcher2/projects` had appropriate access permissions, protecting them from unauthorized modification or exposure.

Through this exercise, I practiced:
- Checking file details  
- Interpreting permission strings  
- Modifying permissions using `chmod`  
- Identifying hidden files  
- Strengthening the system’s security posture  

---

## Explanations of Commands

| Command | Description |
|----------|--------------|
| `cd projects` | Navigates into the projects directory. |
| `ls -l` | Lists files and directories in long format, showing detailed information including permissions, ownership, and modification time. |
| `ls -la` | Lists all files, including hidden ones (those starting with a dot `.`), with detailed information. |
| `chmod` | Changes file permissions. Can grant (+) or remove (-) read (r), write (w), or execute (x) rights for user (u), group (g), or others (o). |

---

## Checking File Permissions with `ls -la`

The command:

```bash
ls -la
```

Displays all files in the directory, including hidden ones.  
Each file line begins with a 10-character string that represents its type and permissions.

**Example output:**
```
drwx--x--- 2 researcher2 research_team 4096 Oct 14 18:40 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Oct 14 18:40 project_k.txt
```

---

## Interpreting the 10-Character Permission String

Each file or directory entry begins with 10 characters, like:

```
drwxr-xr--
```

**1st character → type of file:**  
- `d` = directory  
- `-` = regular file  

**2nd–4th → user (owner) permissions:** `r` (read), `w` (write), `x` (execute)  
**5th–7th → group permissions**  
**8th–10th → other users’ permissions**  

**Example:** `-rw-r--r--` → a regular file where:  
- User can read and write  
- Group can only read  
- Others can only read  

---

## Updating File Permissions with `chmod`

The `chmod` command changes who can read, write, or execute a file.

**Syntax:**
```bash
chmod [owner_type][+ or -][permission] [filename]
```

**Where:**
- `u` = user (owner)  
- `g` = group  
- `o` = others  
- `r` = read  
- `w` = write  
- `x` = execute  

**Examples from the lab:**
```bash
chmod o-w project_k.txt          # removes write permission from others
chmod g-r project_m.txt          # removes read permission from group
chmod u-w,g-w,g+r .project_x.txt # adjusts permissions for hidden file
chmod g-x drafts                 # removes execute permission from group on a directory
```

These changes ensure that only authorized users have the necessary access — an essential step in maintaining confidentiality and system integrity.

---

## Hidden Files and Directories

Hidden files or directories start with a period (`.`).  
They are not shown in normal directory listings.  

To view them, use:
```bash
ls -la
```

**Example:** `.project_x.txt` is a hidden file.  
Even though it’s hidden, it can still have permissions changed and should be secured if it contains sensitive information.

---

## Summary

In this project, I:
- Verified permissions of visible and hidden files  
- Used `ls -la` to identify ownership and permission settings  
- Interpreted 10-character permission strings to understand file access levels  
- Applied `chmod` commands to remove unnecessary write or execute permissions  
- Secured hidden files and restricted directory access to authorized users only  

By completing this activity, I strengthened my understanding of Linux file authorization — an essential skill for cybersecurity analysts responsible for protecting critical systems and data.

---

## Author
**ALawliet0**  
Aspiring Red Team & Pentest professional specializing in AI-driven cybersecurity.
