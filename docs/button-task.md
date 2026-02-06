# Button Styling Task (PRD-001)

## Step-by-step plan
1. Review current button classes in `src/index.css` and note existing `.btn`, `.btn__primary`, `.btn__danger`, and `.toggle-btn` styles.
2. Define primary button styles for Add and Save using a distinct background and text color, ensuring contrast.
3. Ensure destructive buttons (Delete) keep a strong red background and white text.
4. Add hover styles for all buttons, including slight color change or brightness shift.
5. Add a clear selected state for filter buttons using `.toggle-btn[aria-pressed="true"]` with darker background or border.
6. Verify focus-visible styling remains readable and accessible after the changes.
7. Run lint and visually verify button styles in the browser.

## Playwright-based testing plan
- Add or update Playwright tests that load the app and verify button styles are applied via computed styles or class presence.
- Test cases:
  1. Primary buttons: verify Add and Save buttons render with the primary class and computed background color differs from default.
  2. Destructive buttons: verify Delete button uses the danger class and expected color.
  3. Filter buttons: click a filter and verify `aria-pressed="true"` on the active filter and selected styling is applied.
  4. Hover state: simulate hover on Add and Delete buttons and verify computed styles change.
- Use Playwright locators by role and name (e.g., `getByRole('button', { name: 'Add' })`).
- Keep tests deterministic by asserting class names or style tokens rather than exact RGB values if CSS variables are used.
