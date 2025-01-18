# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the example shows a route that fetches a user by ID.  The code attempts to parse the ID as an integer but doesn't handle cases where the ID is not a valid integer (e.g., it's a string, contains non-numeric characters, or is null/undefined). This can lead to unexpected behavior or crashes.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides a corrected version with improved error handling.

## How to reproduce the bug

1. Clone the repository.
2. Run `npm install express`
3. Run `node bug.js`
4. Access the route with an invalid user ID (e.g., `/users/abc`, `/users/123a`, `/users`).

You will likely see an error in the console or unexpected behavior.

## Solution

The `bugSolution.js` file demonstrates how to improve error handling by checking for the validity of the `userId` before attempting to parse it and use it. The improved code includes checks to ensure the userId is defined and is a number before proceeding, returning a 400 Bad Request if validation fails.