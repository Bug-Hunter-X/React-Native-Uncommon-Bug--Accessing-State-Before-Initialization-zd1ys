# React Native Uncommon Bug: Asynchronous State Access

This repository demonstrates a common but often overlooked bug in React Native: attempting to access a state variable before it has been fully initialized. This typically occurs when dealing with asynchronous operations, such as API calls, where the state update might not be immediate.

## Bug Description

The core issue lies in accessing `data.name` within the `return` statement *before* the `setData` function has finished updating the `data` state variable. Since `fetch` is asynchronous, this access can occur while `data` is still `null` or `undefined`, leading to the error "Cannot read properties of undefined (reading 'name')".

## Solution

The solution involves handling the potential `null` or `undefined` state during rendering.  This can be done using conditional rendering or optional chaining.