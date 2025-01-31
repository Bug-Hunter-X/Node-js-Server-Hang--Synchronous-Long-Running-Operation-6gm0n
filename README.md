# Node.js Server Hang: Synchronous Long-Running Operation

This repository demonstrates a common error in Node.js where a long-running synchronous operation in the request handler causes the server to hang.  The `bug.js` file contains the problematic code, while `bugSolution.js` provides a corrected version using asynchronous operations.

## Problem

The problem lies in the synchronous `while` loop within the request handler. This blocks the event loop, preventing the server from responding to further requests.  This leads to a server hang, where clients experience delays or timeouts.

## Solution

The solution involves refactoring the code to use asynchronous operations. This allows the event loop to continue processing other requests while the long-running operation completes in the background. The `bugSolution.js` file demonstrates this using `setTimeout`.  For longer operations, consider using promises, async/await, or worker threads.