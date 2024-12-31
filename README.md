# Express.js Route Handler: Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the example shows a route that retrieves a user by ID but doesn't handle cases where the ID is not a valid integer. This can lead to unexpected behavior or application crashes.

The `bug.js` file contains the code with the error.  The `bugSolution.js` file provides a corrected version with robust error handling.

## Bug:
The primary issue is the absence of error handling when attempting to parse the user ID as an integer using `parseInt()`.  If `req.params.id` cannot be parsed into an integer (e.g., it's a string or contains non-numeric characters), `parseInt()` will return `NaN`, leading to a potential error or unexpected results when searching the `users` array.

## Solution:
The `bugSolution.js` file demonstrates the correct approach.  It explicitly checks if `parseInt(userId)` returns `NaN` before proceeding. This prevents potential crashes and provides a more user-friendly error response.