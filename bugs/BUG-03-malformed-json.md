# BUG-03: API accepts malformed JSON and returns success

**Severity:** High  
**Category:** API / Input validation  
**Status:** Reproduced

## Environment
- Application: Reading List v2.0
- Method: `POST`
- Endpoint: `/api/books`
- Content-Type: `application/json`
- Server: `http://localhost:3000`

## Steps to reproduce
1. Start the application.
2. Send a POST request with incomplete JSON:
   ```bash
   curl -i -X POST http://localhost:3000/api/books \
     -H 'Content-Type: application/json' \
     --data '{"title":"Malformed Test","author":'
   ```
3. Inspect the HTTP status and response body.

## Expected result
The API rejects the malformed JSON with an appropriate client error, such as HTTP `400 Bad Request`, and does not report success.

## Actual result
The API returns:
- HTTP status: `200 OK`
- Response body: `{"result":"OK"}`

The server reports success even though the submitted JSON is syntactically incomplete.

## Evidence
- Raw response: `evidence/malformed-json-response.txt`

## Impact
Clients may incorrectly believe malformed requests were processed successfully. This makes API errors difficult to detect and can undermine data integrity.

## Reproducibility
Reproduced three times with the same malformed request.