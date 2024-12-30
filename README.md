# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the example shows a route that fetches a user by ID, but fails to handle cases where the ID is not a valid number.

## Bug

The `bug.js` file contains the erroneous code. It attempts to parse the user ID as an integer without any error handling. If a non-numeric ID is provided, the `parseInt()` function will return `NaN`, causing the `users.find()` method to fail silently, or throw an error depending on how the `users` array is structured.

## Solution

The `bugSolution.js` file provides a corrected version of the code.  It includes explicit checks to ensure the user ID is a valid number before attempting to parse it. If the ID is invalid, an appropriate error response (400 Bad Request) is returned.