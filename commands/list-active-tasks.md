# /list-active-tasks

## Purpose
Retrieves inbox tasks, tasks due today, and overdue tasks from Todoist to provide immediate action context for daily planning and reviews.

## Usage
```
/list-active-tasks
```

## What it does

### Active Task Extraction
Gathers all tasks needing current attention:
- All tasks in the Inbox project
- Tasks due today across all projects
- Overdue tasks across all projects
- Includes project name, priority level, and labels for context

## Command Implementation

When this command is invoked:

1. **Get inbox tasks:**
   ```
   mcp__todoist-mcp__get-tasks(projectId: "inbox_project_id")
   ```

2. **Get tasks due today:**
   ```
   mcp__todoist-mcp__get-tasks-by-filter("today")
   ```

3. **Get overdue tasks:**
   ```
   mcp__todoist-mcp__get-tasks-by-filter("overdue")
   ```

4. **Format with full context:**
   - Task content
   - Project name
   - Priority level (P1-P4)
   - Labels (@NOW, @NEXT, etc.)

## Example Output Format

```
## Active Tasks

**Inbox (3 tasks):**
- [P2] Review quarterly goals | Labels: @NEXT | Project: Inbox
- [P1] Schedule dentist appointment | Labels: none | Project: Inbox
- [P3] Research vacation destinations | Labels: @LATER | Project: Inbox

**Due Today (2 tasks):**
- [P4] Submit expense report | Labels: @NOW | Project: Home Chef Admin
- [P2] Call mom about dinner plans | Labels: none | Project: Personal

**Overdue (1 task):**
- [P3] Update LinkedIn profile | Labels: @NOW | Project: Find a new job
  *Due: 2025-08-25*
```

## Integration with Review Workflow

This command supports daily planning by:
- Providing immediate visibility into time-sensitive tasks
- Including project context for better decision-making
- Showing priority levels for task sequencing
- Displaying labels for workflow management
- Highlighting overdue items that need attention

## Notes

- Always ignores subtasks per project rules
- Shows priority using P1-P4 notation (P4 = highest priority)
- Includes "none" when tasks have no labels
- Sorts by priority within each category
- Highlights overdue tasks with original due dates