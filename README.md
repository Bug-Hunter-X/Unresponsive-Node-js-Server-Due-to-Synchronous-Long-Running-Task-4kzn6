# Unresponsive Node.js Server

This repository demonstrates a common Node.js issue: an unresponsive server caused by a long-running synchronous operation within the request handler.  The included `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## Problem

Node.js is single-threaded.  When a long-running synchronous operation is performed in the main event loop (like the 5-second loop in `bug.js`), it blocks the event loop and prevents Node from handling other requests.  This leads to an unresponsive server.

## Solution

The solution is to use asynchronous operations.  In `bugSolution.js`, the long-running task is simulated using `setTimeout`, which doesn't block the event loop.