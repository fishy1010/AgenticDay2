# Button Task Code Review

## Findings (ordered by severity)
- High: Playwright tests were not added or executed, so the documented test plan is unimplemented and coverage is missing. No Playwright config or specs exist in the repo. (See [docs/button-task.md](docs/button-task.md))
- Medium: Hover states rely solely on color changes, which conflicts with the NFR guidance to avoid color-only hover feedback. Consider adding a subtle border/shadow change for `.btn:hover` and `.btn__primary:hover` / `.btn__danger:hover`. (See [src/index.css](src/index.css#L78-L126))

## Correctness vs requirements
- Primary and destructive button styles are distinct, and filter buttons have a selected state. (See [src/index.css](src/index.css#L78-L126))
- Hover states exist, but rely only on color change. (See [src/index.css](src/index.css#L88-L126))

## Edge cases
- No functional edge cases identified for CSS-only changes.

## Accessibility
- Hover feedback is color-only; add a non-color cue (border, shadow, underline) to align with guidance. (See [src/index.css](src/index.css#L88-L126))
- Focus-visible outline remains unchanged and visible. (See [src/index.css](src/index.css#L5-L9))

## Performance/regressions
- CSS-only changes; no measurable performance risk expected.

## Lint/build status
- Not run for this change set.

## Test coverage
- No automated tests exist for the button styling changes; Playwright tests were not added or run.

## Risks and follow-ups
- Risk: UI regressions in button states could go unnoticed without Playwright coverage.
- Follow-up: Add Playwright configuration and tests per the plan in [docs/button-task.md](docs/button-task.md).
- Follow-up: Add a non-color hover cue (e.g., subtle shadow or border change) for `.btn:hover` and variants. (See [src/index.css](src/index.css#L88-L126))
