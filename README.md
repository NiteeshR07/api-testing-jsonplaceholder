# API Testing: JSONPlaceholder

Manual and automated testing of the JSONPlaceholder REST API using Postman.

## What I tested
- GET, POST, PUT and DELETE requests
- Status codes (200, 201, 404)
- Response fields and data validity (email format, record counts)
- Filtering with query parameters
- One negative test (non-existent resource)

## Results
8 test cases (15 automated checks) all passing, plus 1 defect documented (BUG01).

TC08 first failed because my request was missing the `userId` query
parameter. I read the assertion error, found the cause was my test and
not the API, corrected the request, and re-ran successfully.

## Files
- `collection.json`: Postman collection with automated assertions
- `test-cases.xlsx`: test cases and results
- `BUG01.md`: defect report
- `run-results-final.png`: collection run
- `bug01-failing-check.png`: failing check that proves the defect

## Tools
Postman, JavaScript (assertions), REST APIs, Excel
