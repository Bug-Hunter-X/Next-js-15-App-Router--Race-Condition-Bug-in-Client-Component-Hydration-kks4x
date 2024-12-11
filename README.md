# Next.js 15 App Router Race Condition Bug

This repository demonstrates a subtle race condition bug that can occur in Next.js 15's App Router when combining server components, client components, and rapid navigation.  The bug is particularly tricky to diagnose because it doesn't always produce clear error messages, instead manifesting as unexpected behavior or silent failures.

## Bug Description

The issue arises from a race condition between the server-side rendering of server components and the client-side hydration of client components that perform intensive data fetching or complex UI manipulations.  When navigating quickly, the client-side hydration may not complete before the next navigation starts, leading to inconsistencies and potential errors.

## Reproduction Steps

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Rapidly navigate between different routes.  You might observe inconsistent UI updates or unexpected behavior.

## Solution

The proposed solution employs techniques such as data loading indicators and proper promise handling to mitigate the race condition by ensuring that client-side operations complete before subsequent navigations occur.