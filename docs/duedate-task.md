# Due Date Task (PRD-003)

## Step-by-step plan
1. Update the task model in `src/App.jsx` to include `dueDate` when creating and editing tasks.
2. Update `src/components/Form.jsx` to add `dueDate` state and a date input labeled "Due date (optional)".
3. Submit the due date value from the form to `addTask(name, dueDate)` and clear it after submit.
4. Update `src/components/Todo.jsx` to accept a `dueDate` prop and display it in view mode only when present.
5. Add a date input to the edit template, pre-filled with the existing due date, and allow clearing it.
6. Update `editTask(id, newName, newDueDate)` in `src/App.jsx` to persist due date changes.
7. Add styling for the due date display in `src/index.css`.
8. Optionally add a sample due date to one entry in `src/main.jsx` for demo purposes.
9. Verify add, edit, and display flows for tasks with and without due dates.

## Playwright-based testing plan
- Add Playwright tests to cover due date entry, display, and edit behavior.
- Test cases:
  1. Create a task with a due date and verify the due date displays in the task item.
  2. Create a task without a due date and verify no due date text is rendered.
  3. Edit a task to add or change the due date and verify the updated display.
  4. Clear a due date during edit and verify it is removed from the display.
- Use `input[type="date"]` locators within the form and edit view to set dates.
- Assert the rendered due date text matches the expected format used by the UI.
