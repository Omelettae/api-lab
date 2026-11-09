# API lab results
## Part 0
- Step 0.1, the number of pizza names: 18
- Step 0.3, status code of the request without a token: 401 Unauthorized
- Step 0.4, the name of your pizza: A Sweet Calzone
- Step 0.12, results of the three runs without a session (optional):
- Step 0.16, blocks of "how many of the three tools are excluded": none, one, two, all three excluded
## Defect report
- Title: Excluding all three tools makes POST /api/pizza fail with 500 and an empty body
- Request: POST https://quickpizza.grafana.com/api/pizza
- Expected result: status 400 and a JSON body with an error message
- Actual result: status 500 and an empty body
- Severity: Medium
## Part A
- Step A4, status codes when the other user reads, changes and deletes:
    Read: 404
    Change: 400
    Delete: 400
## Part B
1. Two failures a real-server test can find: wrong server configuration or deployment (for example the load balancer and cookie problem), and problems in how the parts work together (for example a 500 from a database or backend error). Unit tests with stubs are still worth writing because they are fast, run offline and point to the exact function that broke.
2. Each test makes its own user so that no test depends on another test or on data that other students change. In Project 2 I will create test data with unique names
3.
4. The block "all three tools excluded" revealed the defect. A 500 with an empty body gives the app no reason and no way to tell a client mistake from a server crash, while a 400 with a message can be shown to the user. The test stays as xfail so the defect stays visible
5. Base choice: 1 + 2 + 3 + 1 + 2 = 9 tests. All combinations: 3 × 4 × 2 × 3 = 72 tests.
6. I got read 404, change 400, delete 400. I would expect 403.
7. The server returned a list of 50 ratings (HTTP 200) for a made-up token that no user ever got by logging in. This is a defect and on a real system a stranger could guess or invent a token and read other people's private data, and possibly change it.
8. An API test checks speed, status codes and exact data faster and more reliably than a UI test. Only a test through the web pages can check what the user sees: layout, buttons, text and the browser behavior.