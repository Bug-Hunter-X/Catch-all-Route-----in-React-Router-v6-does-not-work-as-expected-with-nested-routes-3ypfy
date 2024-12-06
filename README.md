# React Router v6 Catch-all Route Issue

This repository demonstrates a subtle issue with React Router v6's catch-all route (`*`) when used with nested routes.  The catch-all route unintentionally intercepts all navigation attempts, even when a more specific route should match.

## Problem

The provided `App.js` component uses nested routes to create a simple navigation system. However, the catch-all route (`<Route path="*" ... />`) interferes with the expected behavior.  No matter what path is entered, the NotFound component is always rendered, even if the '/about' route should correctly display the About component.

## Solution

The solution involves restructuring the routes to place the catch-all route as the last child of the Routes component, ensuring it only matches if no other routes are matched.  See `AppSolution.js` for the corrected implementation. This avoids the unintended overriding of other paths.