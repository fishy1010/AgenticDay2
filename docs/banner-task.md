# Banner Task (PRD-002)

## Step-by-step plan
1. Create a new `Banner` component in `src/components/Banner.jsx` with props `title`, `subtitle`, and `infoText`.
2. Add banner markup with a container element and two regions: left for title/subtitle and right for info text.
3. Update `src/App.jsx` to import and render `Banner` above the main heading.
4. Pass `title="TodoMatic"`, `subtitle="React + Vite demo"`, and `infoText` using the existing task count string.
5. Add banner styles in `src/index.css` for layout, spacing, and background.
6. Add an `aria-live="polite"` region for info text if the count changes dynamically.
7. Verify the banner renders on all screens and the info text updates when tasks change.

## Playwright-based testing plan
- Add Playwright tests to verify the banner is visible and updates with task changes.
- Test cases:
  1. Banner renders with title and subtitle text.
  2. Info text shows task count when tasks are added or removed.
  3. Banner remains visible after filter changes.
- Use role-based selectors or text locators for the banner content.
- For dynamic updates, add a task, then assert the info text changes to reflect the new count.
