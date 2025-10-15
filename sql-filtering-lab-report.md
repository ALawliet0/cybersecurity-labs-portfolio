# SQL Filtering Practice — Lab Report

## Activity Overview
This project demonstrates practical SQL filtering skills applied in a relational database environment.  
As a security analyst, the goal was to query and filter data efficiently to locate specific security-related information about employees, their departments, and their assigned machines.

---

## Objective
Apply basic SQL filters (`WHERE`, `LIKE`) to retrieve specific data from an organizational database, simulating real-world data retrieval tasks in a cybersecurity context.

---

## Scenario
In this scenario, an organization needs to locate detailed information about employees, machines, and departments for security maintenance and system updates.  
The task involved querying the **organization** database to:
1. List all machines and their operating systems.  
2. Identify all machines running a specific OS version.  
3. Retrieve employees from certain departments.  
4. Identify machines and employees in specific office locations.

---

## Tasks and Solutions

### Task 1 — List all organization machines
Retrieve all machines and their operating systems from the `machines` table.

```sql
SELECT device_id, operating_system 
FROM machines;
```

**Result:**  
200 rows returned.

---

### Task 2 — Retrieve machines with OS 2
Filter machines running `OS 2`.

```sql
SELECT device_id, operating_system 
FROM machines 
WHERE operating_system = 'OS 2';
```

**Result:**  
80 machines use the OS 2 operating system.

---

### Task 3 — List employees in Finance and Sales
Retrieve all employees from the **Finance** department:

```sql
SELECT * 
FROM employees 
WHERE department = 'Finance';
```

**First employee_id:** `1003`

Retrieve all employees from the **Sales** department:

```sql
SELECT * 
FROM employees 
WHERE department = 'Sales';
```

**Result:**  
33 employees work in the Sales department.

---

### Task 4 — Identify employee machines
Find the employee who works in office `South-109`:

```sql
SELECT * 
FROM employees 
WHERE office = 'South-109';
```

**Result:**  
The user ID of the employee is `jlansky`.

Now retrieve all employees located in the **South** building using a pattern match:

```sql
SELECT * 
FROM employees 
WHERE office LIKE 'South%';
```

**Result:**  
The first employee listed belongs to the Finance department.

---

## Summary of Concepts Practiced

| Concept | Description |
|----------|--------------|
| `SELECT` | Retrieve specific columns from a table |
| `WHERE` | Filter query results based on specific conditions |
| `LIKE` + `%` | Match patterns within text columns |
| Query Optimization | Using precise filters to minimize unnecessary data retrieval |

---

## Tools Used
- SQL Shell / Database Console
- Organization Database (sample lab environment)

---

## Learning Outcomes
After completing this activity, I learned how to:
- Use SQL filters to refine and target data queries efficiently.
- Apply the `LIKE` operator for flexible pattern matching.
- Understand real-world applications of SQL filtering in security analysis and system auditing.

---

## Author
**DexterCyberSec**  
Aspiring Red Team & Pentest professional specializing in AI-driven cybersecurity.

---

## Tags
`#SQL` `#Cybersecurity` `#DataFiltering` `#PentestLearning` `#GoogleCybersecurityCourse`
