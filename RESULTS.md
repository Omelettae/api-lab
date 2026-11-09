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
1.
2.
3.
4.
5.
6.
7.
8.