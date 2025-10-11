# Linux Authorization Lab

## Project Description
In this lab, we explored **Linux file and directory permissions** and learned how to manage access using commands like `ls` and `chmod`. Authorization is essential to restrict who can read, write, or execute files and directories. Correct permissions protect sensitive information and maintain overall system security.

The scenario focused on the `/home/researcher2/projects` directory. The researcher2 user is part of the `research_team` group. The objective was to inspect and correct file permissions to ensure only authorized users could access specific files and directories.

---

## Explanations of Commands

- `cd projects`  
  Navigate into the `projects` directory.

- `ls -l`  
  List files and directories with detailed permissions, ownership, and size.

- `ls -la`  
  List all files including hidden files, with full details.

- `chmod o-w project_k.txt`  
  Remove write permission from the "other" user type for `project_k.txt`.

- `chmod g-r project_m.txt`  
  Remove read permission from the group for `project_m.txt`.

- `chmod u-w,g-w,g+r .project_x.txt`  
  Modify permissions of a hidden file: remove write for user and group, ensure group can read.

- `chmod g-x drafts`  
  Remove execute permission for the group on the `drafts` directory.

---

## Steps Performed

### 1. Inspecting Permissions
- Used `ls -l` to list file and directory permissions.
- Interpreted the 10-character permission string:
  - 1st character: file type (`d` = directory, `-` = file)
  - 2nd-4th: user permissions (r/w/x)
  - 5th-7th: group permissions
  - 8th-10th: other permissions
- Checked the group owner (`research_team`) and identified hidden files with `ls -la`.

### 2. Correcting File Permissions
- Identified files with excessive permissions:
  - `project_k.txt` allowed write for others → `chmod o-w project_k.txt`
  - `project_m.txt` allowed read for group → `chmod g-r project_m.txt`
- Ensured that only the intended user could read/write restricted files.

### 3. Updating Hidden Files
- Checked `.project_x.txt` and removed unauthorized write permissions for user and group, keeping read access:  
  `chmod u-w,g-w,g+r .project_x.txt`

### 4. Adjusting Directory Permissions
- Inspected `/home/researcher2/projects/drafts` with `ls -l`.
- Removed execute permissions for the group to restrict access:  
  `chmod g-x drafts`

---

## Hidden Files and Directories
- Hidden files start with a dot `.` (e.g., `.project_x.txt`).  
- Hidden files are listed using `ls -la`.  
- Permissions for hidden files follow the same rules as normal files.

---

## Summary / Conclusion
This lab reinforced the importance of **authorization** and **file permissions** in Linux. Key takeaways:

- The 10-character permission string provides a quick view of who can read, write, or execute files and directories.  
- The `chmod` command allows fine-grained control over permissions for **user**, **group**, and **other**.  
- Hidden files require the same security checks as visible files.  
- Proper permission management prevents unauthorized access and protects sensitive data.

By completing this lab, we ensured that the `/home/researcher2/projects` directory and its contents follow proper authorization standards, strengthening the security of the system.

---

 **License:** Licensed under the [MIT License](../LICENSE)
