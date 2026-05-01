# Product Requirements Document (PRD) - TODO App MVP Upgrade

## 1. Overview

We are upgrading the basic TODO app to make it more useful while keeping the implementation simple and teachable. The MVP adds due dates, priority levels, and date-based filters so users can better manage urgent work without introducing backend changes or broader product complexity. The scope is intentionally limited to a frontend-focused enhancement with local storage only.

---

## 2. MVP Scope

- Add an optional `dueDate` field to tasks using ISO format `YYYY-MM-DD`.
- Add a `priority` field with allowed values `P1`, `P2`, and `P3`.
- Default `priority` to `P3` when no value is provided.
- Require `title` when creating a task.
- Treat invalid `dueDate` values as absent rather than blocking the task.
- Provide three task filters: `All`, `Today`, and `Overdue`.
- Show all tasks in the `All` filter, including completed tasks.
- Show only incomplete tasks due on the current local date in the `Today` filter.
- Show only incomplete tasks with a valid due date earlier than the current local date in the `Overdue` filter.
- Persist task data locally.
- Keep the MVP frontend-only with no backend API or storage changes.

---

## 3. Post-MVP Scope

- Visually highlight overdue tasks.
- Add task sorting with this order: overdue first, then priority from `P1` to `P3`, then due date ascending, then undated tasks last.
- Consider color-coded priority badges as a UI enhancement if the team decides to formalize that behavior beyond the initial scope discussions.

---

## 4. Out of Scope

- Notifications
- Recurring tasks
- Multi-user support
- Keyboard navigation enhancements
- External storage
- Backend persistence changes
