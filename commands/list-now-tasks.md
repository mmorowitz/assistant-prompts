# /list-now-tasks

## Purpose
Retrieves all tasks tagged with @NOW label from Todoist to provide focus for current week planning and execution.

## Usage
```
/list-now-tasks
```

## What it does

### @NOW Task Extraction
Gathers all tasks marked for current week execution:
- Gets all tasks with @NOW label across all projects
- Includes project name, priority level, and due dates
- Shows task distribution across projects
- Identifies potential overcommitment or focus issues

## Command Implementation

When this command is invoked:

1. **Get @NOW tasks:**
   ```
   mcp__todoist-mcp__get-tasks-by-filter("@NOW")
   ```

2. **Group by project:**
   - Organize tasks by containing project
   - Show priority levels and due dates
   - Calculate total @NOW task count

3. **Format with full context:**
   - Task content with project name
   - Priority level (P1-P4)
   - Due dates if assigned
   - Additional labels

## Example Output Format

```
## @NOW Tasks (Current Week Focus)

**Total: 8 tasks across 4 projects**

**Home Chef Admin (3 tasks):**
- [P4] Submit Q3 expense report | Due: Aug 29 | Project: Home Chef Admin
- [P2] Update team meeting notes template | Labels: @NOW | Project: Home Chef Admin  
- [P1] Schedule quarterly review meetings | Due: Aug 30 | Project: Home Chef Admin

**Find a new job (2 tasks):**
- [P3] Update LinkedIn profile with recent projects | Labels: @NOW | Project: Find a new job
- [P2] Research target companies in Chicago | Labels: @NOW | Project: Find a new job

**Personal Assistant Maintenance (2 tasks):**
- [P2] Refine the daily review process | Labels: @NOW | Project: Personal Assistant Maintenance
- [P1] Update command documentation | Labels: @NOW | Project: Personal Assistant Maintenance

**BikeFriendly Site (1 task):**
- [P2] Design initial site mockups | Labels: @NOW | Project: BikeFriendly Site

## Weekly Workload Analysis
- High Priority (P3-P4): 2 tasks
- Medium Priority (P2): 4 tasks  
- Low Priority (P1): 2 tasks
- Tasks with deadlines: 2 tasks
```

## Integration with Review Workflow

This command supports weekly planning by:
- Providing clear visibility into weekly commitments
- Showing task distribution across projects
- Identifying overcommitment before it becomes a problem
- Supporting priority-based task sequencing
- Highlighting deadline-driven tasks that need immediate attention

## Notes

- Only shows tasks with @NOW label (current week focus)
- Groups by project for better context understanding
- Shows priority distribution for workload assessment
- Includes due dates to identify time-sensitive items
- Provides total count for capacity planning
- Highlights potential focus or overcommitment issues