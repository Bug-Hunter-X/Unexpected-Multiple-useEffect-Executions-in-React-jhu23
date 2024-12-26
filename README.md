# Unexpected Multiple useEffect Executions in React

This repository demonstrates a common issue in React applications where the `useEffect` hook executes multiple times despite having an empty dependency array.  This can lead to performance problems and unexpected behavior.

The `bug.js` file contains the problematic code.  The `bugSolution.js` file offers a corrected version.

## Problem

The `useEffect` hook with an empty dependency array `[]` is intended to run only once after the initial render. However, in certain scenarios (like unexpected re-renders from parent component changes or other subtle issues), it may execute multiple times.

## Solution

The solution is to ensure that all dependencies are correctly listed in the dependency array. While not directly evident in this simple example, this issue often arises when a component's state or props change indirectly. Proper dependency management can prevent this issue.

If the effect should only run once, use an empty dependency array `[]` to ensure it runs only on mount.  Otherwise, include all relevant variables and values that might cause the effect to re-run.
