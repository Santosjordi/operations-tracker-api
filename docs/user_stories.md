# User Stories

## Epic: Process Templates (SOPs)

### 1. Create Template

**As a** process owner
**I want** to create a reusable template with defined steps and instructions
**So that** my team can execute this workflow consistently.

**Acceptance Criteria**

* I can name a template and add a description.
* I can add steps with titles, instructions, dependencies, and expected duration.
* I can reorder steps.
* Template is saved as “Draft” initially.

---

### 2. Edit Template Version

**As a** process owner
**I want** to version-control templates
**So that** I can update a process without affecting ongoing executions.

**Acceptance Criteria**

* Editing a published template automatically creates a new version.
* Old template versions remain readable but not editable.
* New executions always use the latest published version unless otherwise specified.

---

### 3. Parameterized Templates

**As a** process owner
**I want** to define parameters (e.g., month, SKU list, target values)
**So that** I can customize each execution without modifying the template.

**Acceptance Criteria**

* I can define template parameters with types: text, number, date, list.
* When starting a process run, the system asks for parameter values.
* Steps can reference parameters.

---

### 4. Template Library

**As a** user
**I want** to browse all available templates
**So that** I can instantiate or edit one when needed.

**Acceptance Criteria**

* Templates listed with name, version, last updated.
* Filters: owner, category, tags.
* Ability to archive and restore templates.

---

## Epic: Process Executions (Runs)

### 5. Start a Process from Template

**As a** process operator
**I want** to instantiate a new process run
**So that** I can execute its tasks sequentially.

**Acceptance Criteria**

* Selecting a template prompts for parameters.
* System generates tasks based on template steps.
* The execution appears with status = "Not started."

---

### 6. View Execution Timeline

**As a** user
**I want** to view the current execution timeline and status
**So that** I understand what has been done and what is pending.

**Acceptance Criteria**

* See steps with statuses (Not Started / In Progress / Done / Blocked).
* See due dates derived from expected durations.
* Visual timeline or checklist layout.

---

### 7. Update Execution Status

**As a** task owner
**I want** to mark steps as complete, blocked, or needing review
**So that** others know the progress of the process.

**Acceptance Criteria**

* Step status updates immediately.
* Time of completion is stored.
* If blocked, a reason/comment is required.

---

### 8. Attach Notes, Files, and Data

**As a** operator
**I want** to add supporting info to a process run
**So that** context is preserved for auditability.

**Acceptance Criteria**

* Notes can be attached to either the run or a specific step.
* File attachments accepted (PDF, XLSX, images).
* Custom data inputs can be added depending on parameters.

---

### 9. Close a Process Run

**As a** process owner
**I want** to formally close a run
**So that** the cycle is archived and analytics can be generated.

**Acceptance Criteria**

* Only when all steps are done or force-completed.
* Closing stores final metrics: duration, delays, participants.

---

## Epic: Scheduling & Recurring Runs

### 10. Schedule Recurring Executions

**As a** operations manager
**I want** to set a template to auto-run weekly/monthly/quarterly
**So that** standard cycles start without manual action.

**Acceptance Criteria**

* Cron-like schedule definition.
* System instantiates new run automatically.
* Notifications sent to assigned owners.

---

### 11. Edit or Pause a Schedule

**As a** process owner
**I want** to modify or temporarily pause a recurring schedule
**So that** I can adapt operations without deleting configurations.

**Acceptance Criteria**

* I can pause/unpause schedules.
* Editing a schedule applies to future runs only.
* Clear indicator if a schedule is paused.

---

## Epic: Project & Task Management (tududi-style)

### 12. Create Areas, Projects, and Tasks

**As a** user
**I want** to manage standalone projects and tasks
**So that** I can use the system for daily work as well as processes.

**Acceptance Criteria**

* Areas → Projects → Tasks hierarchy exists.
* Tasks have: title, description, due date, priority, tags, attachments.
* This layer is fully independent of process runs.

---

### 13. Link Tasks to Process Steps

**As a** user
**I want** to reference or create ad-hoc tasks from a process step
**So that** unplanned work can be tracked without leaving the run.

**Acceptance Criteria**

* Steps can generate tasks.
* Tasks show backlink to the step.
* Closing the task does not auto-complete the step unless configured.

---

### 14. Project Views

**As a** user
**I want** Kanban, List, and Calendar views
**So that** I can visualize my tasks however I prefer.

**Acceptance Criteria**

* Project tasks render in all three views.
* Switching views preserves filters.

---

## Epic: Collaboration & Permissions

### 15. Assign Step Owners

**As a** process owner
**I want** to assign steps to people or roles
**So that** responsibilities are clear.

**Acceptance Criteria**

* Step assignment optional per step.
* Default assignee can be defined in the template.
* Assignees get notifications on step activation.

---

### 16. Comment and Discuss Steps

**As a** contributor
**I want** to comment on a step or run
**So that** we can collaborate and resolve issues.

**Acceptance Criteria**

* Markdown-style comments.
* Threaded discussions.
* Mentions/notifications supported.

---

### 17. Permissions System

**As a** administrator
**I want** control over who can create/edit templates and runs
**So that** process governance is maintained.

**Acceptance Criteria**

* Roles: Admin, Process Owner, Operator, Viewer.
* Permissions vary for templates, executions, projects.

---

## Epic: Reporting & Analytics

### 18. Process Performance Dashboard

**As a** operations manager
**I want** insights about process performance over time
**So that** I can improve operational efficiency.

**Acceptance Criteria**

* Metrics per run: lead time, on-time completion, delays, blockers.
* Trend over time for recurring processes.
* Export to CSV.

---

### 19. Bottleneck Identification

**As a** manager
**I want** to identify steps that frequently delay execution
**So that** I can focus improvement efforts.

**Acceptance Criteria**

* Aggregate step performance across runs.
* Highlight steps with most overdue instances.
* Capability to drill down into runs.

---

## Epic: API & Integrations

### 20. GraphQL API for All Entities

**As a** developer
**I want** full CRUD APIs for templates, runs, tasks, and schedules
**So that** I can integrate the system with other automation tools.

**Acceptance Criteria**

* GraphQL schema documented.
* Authentication token-based.
* Query complexity limits enforced.

---

### 21. Webhooks

**As a** technical user
**I want** outgoing webhooks on key events
**So that** I can automate external systems.

**Events**: run created, step started, step completed, run closed.

---

### 22. Import/Export Templates

**As a** admin
**I want** template import/export
**So that** I can share SOPs across environments.

**Acceptance Criteria**

* JSON/YAML format.
* Version metadata included.

---
