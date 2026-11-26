## Severity:
Critical

## Vulnerability Category: Authentication Bypass/ Improper JWT Signature Verification (CWE-345)

## Affected Functionality: JWT Based Authentication

## Summary
The application fails to properly verify JSON Web Token (JWT) signatures, allowing an attacker to modify token claims and authenticate using a forged, unsigned token.
By changing the JWT signing algorithm to none, modifying the email claim and removing the signature, an attacker can submit a forged token that the application
accepts as valid authentication credentials.

## Steps to Reproduce 
1. Obtain a valid JWT from the application.
2. Modify the JWT header to specify the none signing algorithm.
3. Modify the email claim in the JWT payload to an identity that does not exist in the application.
4. Remove the JWT signature.
5. Submit the modified token in an authenticated API request.
6. Observe that the application accepts the unsigned token and authenticates the request as the identity specified in the token.

 ## Expected Behavior
 The application should cryptographically verify JWT signatures before accepting tokens for authentication.

 Tokens using the unsupported or unsecured signing algorithms, including none, should be rejected.

 The application should also validate the token's claims and ensure that the identity represented by the token corresponds to a legitimate account.

 ## Actual Behavior
 The application accepts JWTs with signing algorithm set to none without requiring a valid cryptographic signature.

 A modified token containing an arbitrary email identity is accepted, allowing authentication as a user who does not exist in the application.

 ## Security Impact
 An attacker can forge authentication tokens and bypass the application authentication mechanism.

 This undermines the integrity of JWT based authentication and may allow attackers to impersonate other identities.

 If the vulnerability affects the platform's authentication API endpoints, it could potentially expose protected functionality and resources to unauthenticated attackers.

 ## Recommended Remediation
 * Enforce cryptographic JWT signature verification on the server.
 * Explicitly allow list supported signing algorithms.
 * Reject tokens using the none algorithm.
 * Validate token claims, including issuer, audience, expiration and subject.
 * Ensure that authenticated identities correspond to legitimate application accounts.
 * Apply consistent JWT verification across all API endpoints and authentication middleare.
