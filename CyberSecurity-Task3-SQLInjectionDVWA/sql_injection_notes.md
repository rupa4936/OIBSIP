# SQL Injection on DVWA — Low Security

## 1. Objective

The objective of this task is to demonstrate a classic SQL Injection vulnerability using Damn Vulnerable Web Application (DVWA) in a local environment with Low security enabled.

## 2. Environment Used

* Operating System: Windows
* Web Server: XAMPP
* Database: MySQL
* Vulnerable Application: DVWA
* Security Level: Low
* Browser: Web Browser
* Target: Local DVWA installation

## 3. What is SQL Injection?

SQL Injection is a web application vulnerability that occurs when user input is directly included in an SQL query without proper validation or parameterization.

An attacker can manipulate the SQL query by entering specially crafted input. This can cause the application to return data that was not intended to be returned.

## 4. Payload 1

### Payload

```text
' OR '1'='1
```

### Result

The application returned multiple database records:

| First Name | Surname |
| ---------- | ------- |
| admin      | admin   |
| Gordon     | Brown   |
| Hack       | Me      |
| Pablo      | Picasso |
| Bob        | Smith   |

### Observation

The condition `'1'='1'` is always true. Because the application accepts the input as part of the SQL query, the query returns multiple records instead of only the requested user.

### Screenshot

![SQL Injection Payload 1](sql_injection_payload1.png)

## 5. Payload 2

### Payload

```text
' OR 1=1 #
```

### Result

The application again returned multiple database records:

| First Name | Surname |
| ---------- | ------- |
| admin      | admin   |
| Gordon     | Brown   |
| Hack       | Me      |
| Pablo      | Picasso |
| Bob        | Smith   |

### Observation

The payload creates a condition that evaluates as true and uses `#` to comment out the remaining part of the SQL statement. This demonstrates that the application is vulnerable to SQL Injection.

### Screenshot

![SQL Injection Payload 2](sql_injection_payload2.png)

## 6. Data Exposed

The SQL Injection demonstration exposed the following names stored in the DVWA database:

* admin admin
* Gordon Brown
* Hack Me
* Pablo Picasso
* Bob Smith

This demonstrates how improperly handled user input can allow unintended database records to be retrieved.

## 7. Why the Payload Works

The application uses the value entered in the User ID field as part of an SQL query.

The injected conditions are designed to make the query condition evaluate as true. As a result, the database can return multiple records rather than restricting the result to the intended user.

## 8. Prevention

SQL Injection can be prevented by:

1. **Using parameterized queries / prepared statements**
   User input should be passed as data rather than being directly concatenated into an SQL query.

2. **Validating user input**
   Applications should validate that input matches the expected format and type.

3. **Using appropriate database permissions**
   The application database account should have only the permissions it actually needs.

4. **Avoiding direct SQL string concatenation**
   SQL queries should not be constructed by directly joining untrusted user input with SQL commands.

## 9. Example of Safer Code

A parameterized query can separate SQL instructions from user-provided data.

Example in PHP:

```php
$stmt = $db->prepare("SELECT first_name, last_name FROM users WHERE user_id = ?");
$stmt->bind_param("s", $user_id);
$stmt->execute();
```

Here, the user input is treated as a value rather than being interpreted as part of the SQL command.

## 10. Conclusion

The DVWA Low Security SQL Injection module successfully demonstrated how specially crafted input can manipulate an unsafe SQL query and return multiple database records.

The two payloads produced multiple results, confirming the vulnerability in the intentionally insecure DVWA application.

The main lesson is that applications should use parameterized queries or prepared statements, validate input, and follow the principle of least privilege for database accounts.

## 11. Ethical Considerations

This demonstration was performed only on a locally installed DVWA training environment.

SQL Injection testing should only be performed on systems that you own or have explicit authorization to test. Real websites, production systems, and third-party services should not be tested without permission.
