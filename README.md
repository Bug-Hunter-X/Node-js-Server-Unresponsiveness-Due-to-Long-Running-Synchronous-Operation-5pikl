# Node.js Server Unresponsiveness Bug

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Description

The problem arises when a request handler performs a time-consuming task synchronously. This blocks the Node.js event loop, preventing it from processing other requests or events.  Consequently, the server appears to freeze or become unresponsive.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node server.js`.
4. Open multiple browser tabs and try to access `http://localhost:3000`.  You'll notice that only the first request will be processed quickly, while subsequent requests will hang indefinitely.

## Solution

The solution, as demonstrated in `serverSolution.js`, involves using asynchronous operations (e.g., `setTimeout`, promises, or async/await) to avoid blocking the event loop.  This allows the server to remain responsive even during long-running tasks.