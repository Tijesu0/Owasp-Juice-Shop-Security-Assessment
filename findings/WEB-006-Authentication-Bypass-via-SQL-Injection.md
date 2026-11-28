## Severity:
Critical

## Vulnerability Category:
SQL Injection / Authentication Bypass (CWE-89)

## Affected Functionality:
User Authentication ```POST /rest/user/login```

## Summary
The user authentication functionality is vulnerable to SQL injection due to unsanitized user input being concatenated  directly into a backend SQLite Query.
By Injection a single quote into the email field, the application leaks a verbose SQLite database error. Using an administrator email address disclosed in a public
product review (admin@juice-sh-op) alongside the payload ```admin@juice-sh.op'--```, a unauthenticated attacker can bypass password verification and gain full
administrative access to the application.

## Steps to Reproduce
1. Navigate to the login page, enter dummy credentials, and intercept the ```POST /rest/user/login``` request using Burp Suite proxy.
2. Send the intercepted login request to Burp Repeater.
3. Submit a single quote (') in the email parameter and observe that the server responds with a verbose SQLite syntax error, confirming SQL injection.
4. Browse the application's product reviews to identify the administrator's exposed email address (admin@juice-sh.op).
5. Return to Burp Repeater and set the email parameter to ```admin@juice-sh.op'--``` while leaving an arbitrary value in the password field.
6. Send the modified request and observe that the server returns a ```200 ok``` response containing a valid bearer token for the administrator
account.

## Expected Behavior
The application should use parameterized queries (prepared statements) to safely handle user input during authentication and verify the user's
password hash before issuing an bearer token. Database error details should never be exposed in HTTP responses.

## Actual behavior
The backend concatenates the email input directly into an SQLite query, exposing database error messages on malformed input and allowing the 
```--```SQL comment operator to truncate the password check, granting unauthenticated administrative access.

## Recommended Remediation 
1. Replace dynamically concatenated SQL strings with parameterized queries (prepared statements) or a secure ORM with bound parameters.
2. Configure genetic error handling in production so raw SQLite errors and stack traces are logged internally rather than returned to client
(CWE-209)
3. Avoid exposing full user email addresses publicly in product reviews or frontend responses to reduce target enumeration. 
