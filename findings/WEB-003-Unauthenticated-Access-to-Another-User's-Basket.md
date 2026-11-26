## Severity:
Medium

## Vulnerability Category:
Broken Access Control (IDOR/BOLA) (CWE-639)

## Affected Functionality:
Shopping Basket

## Summary
The shopping basket functionality contains an object-level authorization vulnerability (IDOR/BOLA).
Although the endpoint requires a valid authenticated session, it fails to verify that the requested basket belongs to the current logged-in user. By changing the basket identifier from 6 to 1 in the HTTP request, an authenticated user can view another user's basket.

## Steps to Reproduce
1. Authenticate using a standard user account.
2. Open your shopping basket and intercept the associated HTTP request using Burp Suite.
3. Identify the basket identifier in your request.
4. Change the basket identifier from yours to 1 or any valid identifier.
5. Resend the modified request.
6. Observe that the response contains the contents of another user's basket.

## Expected Behavior
The application should verify that the requested basket belongs to the currently authenticated user before returning its contents.
Users should only be able to access baskets they are authorized to view

## Actual Behavior 
The application accepts a modified basket identifier and returns the contents of another user's basket without adequately enforcing ownership restrictions.

## Security Impact
An authenticated attacker could access other users' shopping basket contents by manipulating basket identifiers.
This exposes information about other users' shopping activity, including the products they have added to their baskets.

## Recommended Remediation
1. Enforce server-side ownership checks whenever a basket is accessed.
2. Derive the authenticated user's identity from the server-side authentication context.
3. Verify that the requested basket belongs to that user before returning its contents.
4. Reject unauthorized requests rather than relying on unpredictable or difficult-to-guess basket identifiers.
