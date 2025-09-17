# /list-stalled-projects

## Purpose
Identifies projects that lack clearly defined next actions (@NOW or @NEXT tasks) to highlight projects needing attention or potential cancellation.

## Usage
```
/list-stalled-projects
```

## What it does

### Stalled Project Detection
Finds projects without clear forward momentum:
- Gets all projects and their tasks
- Identifies projects lacking @NOW or @NEXT labeled tasks
- Excludes storage-only projects (REMINDERS, Lists, etc.)
- Shows project purposes from DESCRIPTION tasks
- Flags projects that may need evaluation or cancellation

## Command Implementation

When this command is invoked:

1. **Get all projects:**
   ```
   mcp__todoist-mcp__get-projects()
   ```

2. **For each active project:**
   ```
   mcp__todoist-mcp__get-tasks(projectId)
   ```

3. **Check for @NOW or @NEXT tasks:**
   - Search tasks for @NOW or @NEXT labels
   - Identify projects without these action labels
   - Exclude storage projects based on descriptions

4. **Format with context:**
   - Project name and description
   - Count of total tasks in project
   - Last activity date if available

## Example Output Format

```
## Stalled Projects (No @NOW/@NEXT Tasks)

**Projects Needing Attention (3 projects):**

**Media Monitor App** - 4 tasks
- *Purpose: Build app to monitor media coverage of bike infrastructure*
- *Last activity: 3 weeks ago*
- *Status: Has tasks but no clear next actions defined*

**Write a Novel** - 7 tasks  
- *Purpose: Complete first draft of science fiction novel*
- *Last activity: 1 week ago*
- *Status: Multiple ideas but no current momentum*

**Career** - 2 tasks
- *Purpose: Long-term career development and planning*
- *Last activity: 5 days ago*  
- *Status: Strategic project lacking immediate actions*

**Active Projects (5 projects have clear next actions)**
- Home Chef Admin: 2 @NOW tasks
- Find a new job: 3 @NOW, 1 @NEXT tasks  
- Personal Assistant Maintenance: 1 @NOW task
- BikeFriendly Site: 1 @NOW, 2 @NEXT tasks
- 2025 Q4 Planning: 2 @NEXT tasks

**Storage Projects (ignored):**
- REMINDERS (date-based tasks only)
- Lists (reference storage)
- Checklists (template storage)
```

## Integration with Review Workflow

This command supports project maintenance by:
- Identifying projects that may have stalled or lost momentum
- Highlighting projects that need next action definition
- Supporting project evaluation and potential cancellation decisions
- Providing context for project portfolio management
- Ensuring all active projects have clear forward movement

## Notes

- Ignores REMINDERS project (uses dates instead of @NOW/@NEXT)
- Excludes storage-only projects based on DESCRIPTION content
- Shows project purposes for context when evaluating
- Provides task counts to understand project scope
- Suggests projects that may need attention or cancellation
- Confirms which projects do have clear next actions