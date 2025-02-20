# React Router Dom v6 - Nested Routes and Wildcard Route Conflict

This repository demonstrates a common issue encountered when using nested routes and a wildcard route (*) in React Router Dom v6.  The wildcard route unintentionally intercepts routes intended for nested components, resulting in unexpected routing behavior.  The solution provided shows how to correctly structure the routes to avoid this conflict.

## Problem
The wildcard route `/*` in a `Routes` component always matches, and therefore always takes precedence even if a nested route matches.  This is because the order of routes in the `Routes` component dictates the matching order, and a wildcard route effectively sits at the bottom, always ready to receive unmatched paths.

## Solution
The solution involves restructuring the routes to prioritize the nested routes. This ensures that nested routes are checked before the wildcard route, solving the problem without needing to change the wildcard route's position.