# Unhandled error: Accessing state before initialization in React Native

This repository demonstrates a common error in React Native functional components: accessing state variables before they've been initialized by the `useState` hook.

## The Problem

The `useState` hook is asynchronous; it doesn't instantly set the initial state value. Attempting to use the state variable immediately within the component's body before it is initialized can lead to unexpected behavior or errors.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npx react-native run-android` or `npx react-native run-ios` to run the app. 
4. Observe the console logs and the initial state of the counter.

## The Solution

The solution is to only access the state *after* it's been set.  This can be achieved by placing any state-dependent operations within a conditional statement that checks if the state is ready.  We can improve the readability of the conditional statements by using Optional Chaining. For cases with more complex logic, the useEffect hook provides a cleaner solution.

## Fixing the Bug

The `bugSolution.js` file demonstrates a correctly handled scenario.