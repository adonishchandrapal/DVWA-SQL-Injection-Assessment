# DVWA SQL Injection Security Assessment

Hands-on web application security assessment and SQL injection testing using DVWA and SQLMap in a controlled local laboratory environment.

## 📌 Project Overview

This project demonstrates a practical web application security assessment against Damn Vulnerable Web Application (DVWA).

The assessment focused on:

- Manual SQL Injection
- SQLMap-based vulnerability detection
- Database and table enumeration
- Users table data extraction
- GET parameter tampering
- Boolean-based Blind SQL Injection
- Time-based Blind SQL Injection
- Authentication bypass testing
- Security impact and remediation

All testing was performed against a locally hosted DVWA instance in a controlled laboratory environment. 

## 🛠️ Environment

| Component | Details |
|---|---|
| Application | Damn Vulnerable Web Application (DVWA) |
| Target | Local DVWA |
| Security Level | Low |
| Database | MySQL / MariaDB |
| Tools | Firefox, SQLMap |
| Environment | Controlled local laboratory |

## 🔍 Key Findings

### 1. SQL Injection — GET Parameter

SQL injection was successfully confirmed in the `id` GET parameter through both manual testing and SQLMap.

### 2. SQLMap Enumeration

SQLMap identified the backend as MySQL/MariaDB and successfully enumerated the `dvwa` database and its tables.

### 3. Users Table Exposure

The `users` table was successfully extracted. Credential-related information was present, so sensitive credential material was redacted from the public evidence.

### 4. GET Parameter Tampering

Changing the user-controlled `id` parameter returned a different user record, demonstrating insufficient protection of the identifier.

### 5. Boolean-Based Blind SQL Injection

True and false SQL conditions produced distinguishable application responses, confirming boolean-based blind SQL injection.

### 6. Time-Based Blind SQL Injection

SQLMap identified a MySQL time-based blind SQL injection technique using delayed responses.

### 7. Authentication Bypass

An SQL injection authentication-bypass attempt was tested against the DVWA login form, but a successful bypass was **not reproduced**.

## 📸 Evidence

The `Evidence/` directory contains screenshots documenting the assessment:

1. Manual SQL Injection
2. SQLMap table enumeration
3. Redacted users-table extraction
4. GET parameter tampering
5. Blind SQL Injection baseline
6. Blind SQL Injection true condition
7. Blind SQL Injection false condition
8. SQLMap time-based blind SQL Injection

## 📄 Report

The complete assessment report is available in:

`Report/DVWA_SQL_Injection_Final_Report_.pdf`

The report contains the methodology, detailed findings, impact analysis, remediation recommendations, conclusion, and evidence index. 

## 🛡️ Remediation

Recommended security controls include:

- Use parameterized queries / prepared statements.
- Never concatenate user input directly into SQL queries.
- Implement strict server-side input validation.
- Use least-privilege database accounts.
- Store passwords using modern password-hashing algorithms.
- Implement proper authorization checks.
- Use secure session and authentication controls.
- Log and monitor suspicious SQL injection activity.
- Retest the application after remediation. 

## ⚠️ Disclaimer

This project was performed exclusively against an intentionally vulnerable DVWA instance hosted in a controlled local laboratory environment.

Do not use these techniques against systems or applications without explicit authorization.

## 👨‍💻 Author

**Chandrapal Singh Panwar**

BCA Graduate | Cyber Security Learner

GitHub: https://github.com/adonishchandrapal

LinkedIn: https://www.linkedin.com/in/chandrapal-singh-panwar-965733386
