# Express.js JSON Parsing Bug
This repository demonstrates a common bug in Express.js applications where JSON payloads in POST requests are not parsed correctly.  The issue arises from a missing middleware component to handle JSON body parsing.

## Bug Description
The provided `bug.js` file sets up a simple Express.js server that attempts to handle a POST request containing JSON data.  However, it incorrectly logs an empty object for `req.body` because it lacks the `express.json()` middleware. This leads to the application failing to process the incoming JSON data.

## Solution
The `bugSolution.js` file provides a corrected version that includes the `express.json()` middleware. This middleware parses the incoming request body and makes the JSON data accessible via `req.body`.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/data` with a JSON payload (e.g., using curl or Postman).
5. Observe that the server logs an empty object in `bug.js`.
6. Run `node bugSolution.js` and repeat steps 4 and 5. Observe that the server correctly logs the JSON payload this time.

## Lessons Learned
Always include the appropriate middleware (e.g., `express.json()` for JSON) in Express.js to handle incoming request bodies correctly.  Missing middleware is a frequent source of unexpected behavior when dealing with HTTP requests.