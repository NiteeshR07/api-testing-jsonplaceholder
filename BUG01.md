# BUG01: Newly created post cannot be retrieved after successful POST

**Severity:** Medium
**Status:** Open (observed behavior)
**Tool:** Postman
**API:** https://jsonplaceholder.typicode.com

## Steps to reproduce
1. Send POST to `/posts` with body `{"title": "my test post", "body": "hello world", "userId": 1}`
2. Note the response: status 201 Created, `"id": 101`
3. Send GET to `/posts/101`

## Expected result
Status 200, and the post data returned.

## Actual result
Status 404 Not Found, with an empty `{}` body.

## Evidence
- Automated check `BUG01_step2` fails: "expected response to have status code 200 but got 404"
- See `bug01-failing-check.png` and `run-results-final.png`

## Business impact
A user would believe their data was saved when it was not.

## Note
JSONPlaceholder states that it is a practice API and does not save changes,
so this is documented as observed behavior, not a production defect.
