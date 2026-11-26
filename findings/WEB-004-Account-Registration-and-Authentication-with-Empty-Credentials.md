## Severity:
High

## Vulnerability Category:
Improper Input Validation/Authentication Weakness (CWE-287)

## Affected Functionality:
User Registration and Authentication

## Summary
The application allows users to register and authenticate with empty email and password values due to insufficient server side validation.

An attacker can bypass frontend validation by modifying registration and login requests, allowing an account to be created and accessed using empty credentials.

## Steps to Reproduce
1. Navigate to the registration page.
2. Enter valid values into the email and password fields.
3. Intercept the registration request using a proxy.
4. Send the request to Repeater.
5. Remove the email and password values.
6. Resend the modified request.
7. Observe that the application successfully creates an account.
8. Attempt to login using the empty credentials.
9. Intercept a login request and remove the email and password values.
10. Resend the modified request.
11. Observe that authentication succeeds and access is granted.


## Expected Behavior
The application should enforce server side validation to ensure that email and password fields contain valid, non-empty values during registration.
Authentication requests containing empty credentials should be rejected.

## Actual Behavior
The backend accepts registration requests containing empty email and password values and successfully creates a normal user account.

This authentication functionality subsequently accepts the same empty credentials, granting access to the account and its normal user functionality.


## Security Impact
An attacker can create accounts without supplying the required registration credentials and subsequently authenticate into those accounts using empty values.

This undermines the application's registration and authentication requirements and may allow account creation that bypasses intended identity and credential requirements.


## Recommended Remediation
1. Enforce mandatory email and password validation on the server side.
2. Reject registration requests containing empty or invalid required fields.
3. Ensure authentication requests reject empty credentials.
4. Apply consistent validation across frontend and backend
5. Ensure account creation and authentication rely on properly validated credentials  
