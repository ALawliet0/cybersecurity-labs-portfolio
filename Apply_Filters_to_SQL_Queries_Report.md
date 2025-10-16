# Apply Filters to SQL Queries
### Portfolio Project — Google Cybersecurity Professional Certificate

---

## Project Description

As a security analyst, I used SQL queries to investigate suspicious login activity and retrieve specific employee information from organizational databases. This project demonstrates how I applied filters using `AND`, `OR`, `NOT`, and `LIKE` operators to identify patterns, exclude specific data, and analyze potential cybersecurity incidents.

Through this activity, I simulated real-world threat investigations by querying login attempts, identifying failed logins after hours, and filtering employee data for security maintenance tasks.

---

## Retrieve after hours failed login attempts

### SQL Query
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
  AND (success = 0 OR success = FALSE);
```

### Explanation
This query retrieves all failed login attempts that occurred after 6:00 PM.
- The condition `login_time > '18:00'` filters records that happened after business hours.
- The condition `(success = 0 OR success = FALSE)` identifies unsuccessful login attempts.
- The `AND` operator ensures both conditions must be true, returning only failed attempts after 18:00.

---

## Retrieve login attempts on specific dates

### SQL Query
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09'
   OR login_date = '2022-05-08';
```

### Explanation
This query investigates suspicious events that occurred on May 9th and May 8th, 2022.
- The `OR` operator is used to include both dates in the results.
- This helps analysts review logs from multiple days surrounding the event for potential correlations.

---

## Retrieve login attempts outside of Mexico

### SQL Query
```sql
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE '%MEX%';
```

### Explanation
This query identifies all login attempts not originating from Mexico.
- The `NOT LIKE '%MEX%'` condition excludes both `MEX` and `MEXICO` entries, since the `%` wildcard matches any characters before or after “MEX”.
- Using `NOT` ensures we only retrieve activity from other countries.

---

## Retrieve employees in Marketing (East building)

### SQL Query
```sql
SELECT *
FROM employees
WHERE department LIKE '%Marketing%'
  AND office LIKE 'East%';
```

### Explanation
This query filters for employees who:
- Work in the Marketing department (`department LIKE '%Marketing%'`), and
- Are located in the East building (`office LIKE 'East%'`, which includes East-170, East-320, etc.).
- The `AND` operator ensures both filters apply together.

---

## Retrieve employees in Finance or Sales

### SQL Query
```sql
SELECT *
FROM employees
WHERE department LIKE '%Finance%'
   OR department LIKE '%Sales%';
```

### Explanation
This query retrieves all employees from either the Finance or Sales departments.
- The `OR` operator allows for inclusion of both departments in the same search.
- Using `LIKE` makes it flexible in case there are variations in department names.

---

## Retrieve all employees not in IT

### SQL Query
```sql
SELECT *
FROM employees
WHERE department NOT LIKE '%Information Technology%';
```

### Explanation
This query returns all employees except those in the Information Technology department.
- The `NOT LIKE` operator excludes records where the department field matches "Information Technology".
- This is useful for targeting departments that still need a system update.

---

## Summary

In this project, I used SQL filters to analyze login and employee data for potential security incidents. I applied logical operators like `AND`, `OR`, and `NOT` to combine multiple conditions, and the `LIKE` operator with wildcards (`%`) to search for text patterns.

These queries helped identify after-hours failed logins, filter by date ranges, exclude specific regions, and isolate employees by department and office location. This demonstrates how SQL filtering is crucial for incident response, threat investigation, and IT asset management in cybersecurity.

---

**Key Skills Demonstrated:**
- SQL filtering with `WHERE`, `AND`, `OR`, and `NOT`
- Pattern matching with `LIKE` and `%`
- Date and time filtering
- Practical application in cybersecurity investigations
