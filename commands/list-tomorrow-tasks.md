# /list-tomorrow-tasks

## Purpose
Retrieves all tasks scheduled for tomorrow from Todoist to support next-day planning and workload assessment.

## Usage
```
/list-tomorrow-tasks
```

## What it does

### Tomorrow's Task Extraction
Gathers all tasks due tomorrow for planning purposes:
- Gets all tasks with tomorrow's due date
- Includes project name, priority level, and labels
- Shows task distribution and workload
- Supports next-day preparation and time blocking

## Command Implementation

When this command is invoked:

1. **Calculate tomorrow's date:**
   ```
   Get current date and add 1 day
   ```

2. **Get tomorrow's tasks:**
   ```
   mcp__todoist-mcp__get-tasks-by-filter("tomorrow")
   ```

3. **Format with full context:**
   - Task content with project name
   - Priority level (P1-P4)  
   - Labels (@NOW, @NEXT, etc.)
   - Estimated time if available

## Example Output Format

```
## Tomorrow's Tasks (August 28, 2025)

**Total: 5 tasks across 3 projects**

**High Priority (P3-P4):**
- [P4] Submit expense report | Labels: @NOW | Project: Home Chef Admin
- [P3] Prepare quarterly presentation | Labels: @NOW | Project: Home Chef Admin

**Medium Priority (P2):**
- [P2] Review client feedback | Labels: @NEXT | Project: Find a new job
- [P2] Update project timeline | Labels: @NOW | Project: Personal Assistant Maintenance

**Low Priority (P1):**
- [P1] Research new productivity tools | Labels: @LATER | Project: Personal

## Workload Assessment
- **High Priority:** 2 tasks (focus items)
- **Medium Priority:** 2 tasks (standard work)  
- **Low Priority:** 1 task (if time permits)
- **@NOW tasks:** 3 tasks (current week focus)
- **Estimated time:** ~4-5 hours of focused work

## Planning Recommendations
- Block morning time for P4 expense report (deadline sensitive)
- Schedule client feedback review before end of business
- Consider moving P1 research task if day gets busy
```

## Integration with Review Workflow

This command supports next-day planning by:
- Providing clear visibility into tomorrow's commitments
- Supporting workload assessment and time blocking
- Identifying high-priority items that need early attention
- Helping balance scheduled tasks with meeting commitments
- Supporting realistic daily planning and expectations

## Notes

- Shows only tasks specifically due tomorrow (not just @NOW tasks)
- Groups by priority for better planning sequence
- Includes labels to understand task context and urgency
- Provides workload assessment for capacity planning
- Suggests planning recommendations based on task priorities
- Supports integration with calendar planning for realistic scheduling