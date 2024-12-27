# TypeScript Closure Issue with setTimeout in Loop

This repository demonstrates a common closure-related bug in JavaScript (and TypeScript) when using `setTimeout` within a loop.

The issue arises because the inner function within `setTimeout` does not capture the value of `i` at the time of its creation but rather references the variable `i` itself. By the time `setTimeout` executes, the loop has already finished, and `i` holds its final value.

## How to reproduce

1. Clone this repository.
2. Run `tsc bug.ts` to compile the TypeScript code.
3. Run `node bug.js` to observe the unexpected output.

## Solution

The solution involves creating a closure using an immediately invoked function expression (IIFE) or `let` instead of `var` to create a new scope for each iteration of the loop.

The solution is provided in `bugSolution.ts`.