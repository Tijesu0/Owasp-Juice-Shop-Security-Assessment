## Summary
The product review functionality allows authenticated users to submit reviews with client controlled author identity.

Testing revealed that a authenticated user can manipulate the author parameter i a review submission request to publish a review under another existing user's
identity, icluding an admiistrator's account.

## Affected Endpoint:
```PUT /rest/product/1/reviews```

## Vulnerability Category: Broken Access Control

## Steps to Reproduce
1. Authenticate usig a standard customer account.
2. Initiate a product review and inspect the associated HTTP request
3. Modify the author parameter to refrence another existing usersemail address.
4. Submit the modified request.
5. Observe that the review is created under the specified user's identity.

## Expected Behaviour
The application should associate submitted reviews with the identity of the current user's idetity.

## Actual Behaviour
The application accepts the client supplied author identity without adequately validating it agaist the authenticated user.

A review submitted usig a different user's identity is successfully created and displayed under that user's account.

## Securiy Impact
This vulnerability allows authenticated users to impersonate other accounts within the product review system.

An attacker could:
* Publish reviews under another users identity.
* Falsely attribute statmets or opinions toadmiistrators or other users
* Damage the reputation of impersonated accounts.
* Udermine the integrity and trustworthiness of product reviews.

## Recommended Remediation
The application should derive the review author's identity from the autheticated server side user context rather than accepting a client controlled identity.

The server should enforce this validation on every review creation request and reject or ignore attempts to assign reviews to unauthorized identities.
