# setTimeout Loop Bug in TypeScript

This repository demonstrates a common error when using `setTimeout` within a loop in TypeScript.  The issue arises from the closure over the loop variable `i`. By the time the `setTimeout` callbacks finally execute, the loop has already finished, and `i` holds its final value.

## Bug

The `printNumbers2` function attempts to print numbers 1 through `n` using `setTimeout` to simulate asynchronous behavior. However, it incorrectly prints the final value of `i` multiple times.

## Solution

The solution utilizes an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, effectively capturing the value of `i` at each step.