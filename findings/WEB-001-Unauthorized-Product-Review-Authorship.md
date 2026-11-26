## Severity:
Medium

## Vulnerability Category:
Broken Access Control (CWE-639)

## Affected Endpoint:
```PUT /rest/product/1/reviews```

## Summary
The product review functionality allows an authenticated user to submit reviews with client controlled author identity.

Testing revealed that a authenticated user can manipulate the author parameter in a review submission request to publish a review under another existing user's
identity, including an administrator's account.

## Steps to Reproduce
1. Authenticate using a standard customer account.
2. Initiate a product review and inspect the associated HTTP request
3. Modify the author parameter to reference another existing user's email address.
4. Submit the modified request.
5. Observe that the review is created under the specified user's identity.

## Expected Behavior
The application should associate submitted reviews with the current user's identity.

## Actual Behavior
The application accepts the client supplied author identity without adequately validating it against the authenticated user.

A review submitted using a different user's identity is successfully created and displayed under that user's account.

## Security Impact
This vulnerability allows an authenticated user to impersonate another user's identity.

An attacker could:
* Publish reviews under another users identity.
* Falsely attribute statements or opinions to administrators or other users
* Damage the reputation of impersonated accounts.
* Undermine the integrity and trustworthiness of product reviews.

## Recommended Remediation
The application should derive the review author's identity from the authenticated server side user context rather than accepting a client controlled identity.

The server should enforce this validation on every review creation request and reject or ignore attempts to assign reviews to unauthorized identities.
