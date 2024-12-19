# Node.js Server Unresponsiveness: Blocking Event Loop

This repository demonstrates a common issue in Node.js applications where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive. The `server.js` file contains the buggy code. The `serverSolution.js` shows how to fix it using asynchronous operations.

## Problem

The `server.js` example uses a `while` loop to simulate a 5-second task.  This blocks the event loop, meaning no other requests can be processed during this time.  This leads to poor server responsiveness and ultimately unavailability if multiple requests arrive while the loop runs.

## Solution

The `serverSolution.js` file illustrates how to address the issue using asynchronous operations.  Instead of blocking the event loop, it uses `setTimeout` to perform the long-running task asynchronously, keeping the server responsive.