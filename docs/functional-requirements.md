# Functional Requirements for TODO App

This document reflects the scoped requirements discussed in the Sept. 16 meeting and then locked in the Sept. 17 Slack follow-up. Where the two sources differ, the later Slack decisions take precedence.

## MVP Scope

The MVP is a lean frontend-only upgrade to the existing TODO app.

### In Scope

1. Users can create tasks with a required `title`.
2. Users can assign an optional `dueDate` using ISO format `YYYY-MM-DD`.
3. Users can assign a `priority` value of `P1`, `P2`, or `P3`.
4. Tasks created without an explicit priority default to `P3`.
5. Users can view tasks in three filters: `All`, `Today`, and `Overdue`.
6. The app stores task data locally only.
7. The MVP does not require backend changes.

### Data Rules

1. `title` is required.
2. `priority` must be one of `P1`, `P2`, or `P3`.
3. Missing `priority` values default to `P3`.
4. `dueDate` is optional.
5. Invalid `dueDate` values are ignored and treated as absent.

### Filter Rules

1. `All` shows all tasks, including completed tasks.
2. `Today` shows incomplete tasks due on the current local date.
3. `Overdue` shows incomplete tasks with a valid due date earlier than the current local date.

## MVP Acceptance Criteria

1. A user can add a task with only a title and the task is stored without a due date and with priority `P3`.
2. A user can add a task with a valid due date in `YYYY-MM-DD` format and that value is preserved.
3. A user can add a task with priority `P1`, `P2`, or `P3` and the selected value is preserved.
4. If a task is created or loaded with an invalid due date, the app behaves as if the task has no due date.
5. Switching to `All` shows every task regardless of completion status.
6. Switching to `Today` shows only incomplete tasks due today.
7. Switching to `Overdue` shows only incomplete tasks whose due date is before today.
8. Task data remains available through local storage only.
9. No backend API or persistence changes are required for MVP completion.

## Post-MVP

The following items were discussed in the meeting but explicitly moved out of MVP in the Sept. 17 Slack scope lock:

1. Visually highlight overdue tasks.
2. Sort tasks using this order: overdue tasks first, then priority from `P1` to `P3`, then due date ascending, then undated tasks last.

## Out of Scope

1. Notifications
2. Recurring tasks
3. Multi-user functionality
4. Keyboard navigation enhancements
5. External storage or any non-local persistence

## Notes on Earlier Discussion

The Sept. 16 meeting also mentioned color-coded priority badges and overdue highlighting. Overdue highlighting was later moved to Post-MVP. Priority color treatment may be added as a UI choice, but it is not required to satisfy the MVP scope lock unless it is added to a separate story or acceptance criteria document.
