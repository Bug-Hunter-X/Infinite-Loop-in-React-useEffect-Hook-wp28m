# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook. The bug causes an infinite loop due to improper dependency management.

## Bug Description

The `MyComponent` component uses `useEffect` to increment a counter. However, the `count` state is included in the dependency array, creating a loop: the effect runs, updates `count`, which triggers a re-render, which triggers the effect again, and so on.

## Bug Solution

The solution corrects the `useEffect` dependency array. By removing `count`, the effect only runs once after the initial render and does not create an infinite loop.  Alternatively, using `useCallback` can also mitigate this issue.