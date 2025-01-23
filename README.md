# Node.js HTTP Server Hanging Issue

This repository demonstrates a subtle bug in a Node.js HTTP server where omitting the `Content-Type` header in the response can cause the server to hang.  The issue is often difficult to track down because it doesn't produce immediate error messages.

## Bug Description

The provided `bug.js` file contains a simple HTTP server.  If you run this server and make a request, the connection will hang unless the `Content-Type` header is explicitly set.  This behavior is unexpected and can lead to significant debugging challenges.

## Solution

The `bugSolution.js` file shows the corrected code.  By simply adding `res.setHeader('Content-Type', 'text/plain');`, the issue is resolved, and the server responds correctly.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Make a request to `http://localhost:3000/` using a tool like `curl` or your browser.
5. Observe that the connection hangs.
6. Repeat steps 3-5 with `bugSolution.js`. You'll see the server works correctly.

This example highlights the importance of setting the appropriate headers in HTTP responses to ensure proper communication and prevent unexpected behavior.