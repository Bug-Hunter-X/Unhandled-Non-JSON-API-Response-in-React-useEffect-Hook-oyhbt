# Unhandled Non-JSON API Response in React useEffect Hook

This repository demonstrates a common error in React applications: improperly handling non-JSON responses from API calls within the `useEffect` hook.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides the corrected version.

## Bug Description:

The provided React component fetches data from an API.  However, it does not explicitly check if the response is actually JSON before attempting to parse it using `response.json()`.  If the server returns a non-JSON response (e.g., an error message in plain text), the application will crash with a `SyntaxError`. This is because `response.json()` will fail to parse the response resulting in the program breaking.

## Solution:

The solution involves adding a check to ensure the `response.ok` status before attempting to parse the response as JSON. Additionally, a more robust error handling mechanism is implemented to catch and display errors to the user effectively.

## How to Reproduce:

1. Clone this repository.
2.  Run `npm install` to install dependencies (if any).
3. Run the code (e.g. using `create-react-app`).
4. Simulate a server returning a non-JSON response to trigger the bug.