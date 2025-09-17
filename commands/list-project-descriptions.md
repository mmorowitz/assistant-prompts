# /list-project-descriptions

## Purpose
Retrieves DESCRIPTION tasks from all Todoist projects to provide context about project purposes for review and planning sessions.

## Usage
```
/list-project-descriptions
```

## What it does

### Project Description Extraction
Retrieves all projects from Todoist and finds the "DESCRIPTION" task in each project to understand project purposes:
- Gets all projects from Todoist
- For each project, searches for tasks containing "DESCRIPTION" 
- Returns project name with corresponding description content
- Flags projects missing descriptions for follow-up

## Command Implementation

When this command is invoked:

1. **Get all projects:**
   ```
   mcp__todoist-mcp__get-projects()
   ```

2. **For each project, get tasks and find DESCRIPTION:**
   ```
   mcp__todoist-mcp__get-tasks(projectId)
   ```

3. **Extract and format descriptions:**
   - Search tasks for ones with "DESCRIPTION" in the title
   - Pair project name with description content
   - Flag projects without descriptions

## Example Output Format

```
## Project Descriptions

**Active Projects:**
- **Work - Client Management:** Manage ongoing client relationships, contracts, and deliverables
- **Personal - Health Goals:** Track fitness routines, meal planning, and health appointments
- **Home - Renovation:** Coordinate kitchen renovation project timeline and contractors

**Projects Missing Descriptions:**
- Marketing Campaign Q4 (needs description)
- Side Project Ideas (needs description)

**Ignored Projects:**
- REMINDERS (storage only)
- Archive (storage only)
```

## Integration with Review Workflow

This command supports structured reviews by:
- Providing context on all active project purposes
- Identifying projects that need description updates
- Loading project context into conversation for decision-making
- Supporting project prioritization and resource allocation decisions

## Notes

- Ignores projects marked as storage-only in their descriptions
- Highlights projects without DESCRIPTION tasks for maintenance
- Filters out completed/archived projects unless specifically requested