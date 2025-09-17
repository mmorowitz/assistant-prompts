# /list-recent-journal

## Purpose
Retrieves recent journal entries from the last 7-30 days to provide context about recent activity, decisions, and patterns for review sessions.

## Usage
```
/list-recent-journal [days]
```

**Parameters:**
- `days` (optional): Number of recent days to include (default: 7, max: 30)

## What it does

### Journal Entry Extraction
Gathers recent journal entries to provide activity context:
- Reads journal files from ./journal directory
- Looks back specified number of days (default 7)
- Shows entry dates, key activities, and decisions
- Highlights patterns and recurring themes

## Command Implementation

When this command is invoked:

1. **Get current date:**
   ```
   Calculate date range based on days parameter
   ```

2. **Search for journal files:**
   ```
   Glob("./journal/*.md") for files in date range
   ```

3. **Read and summarize entries:**
   ```
   Read(journal_file_path) for each file in range
   ```

4. **Format chronologically:**
   - Show date and key activities
   - Highlight important decisions or patterns
   - Note any incomplete items or follow-ups

## Example Output Format

```
## Recent Journal Entries (Last 7 days)

**2025-08-27 (Today):**
- Created new slash commands for productivity workflow
- Completed project descriptions command implementation
- Note: Still need to test command functionality in practice

**2025-08-26:**
- Refined daily review process with new task labeling
- Completed quarterly goals review
- Decision: Focus on Home Chef admin tasks this week
- Follow-up: Schedule meeting with Conor about project priorities

**2025-08-25:**
- Weekend planning session - reorganized project structure
- Added descriptions to 3 missing projects
- Note: BikeFriendly site needs more attention next week

**No entries found for:** 2025-08-24, 2025-08-23, 2025-08-22, 2025-08-21
```

## Integration with Review Workflow

This command supports structured reviews by:
- Providing context on recent activity and decisions
- Identifying patterns in work habits and focus areas
- Highlighting incomplete items that need follow-up
- Supporting continuity between review sessions
- Surfacing important decisions that may impact current planning

## Notes

- Reads from ./journal directory using YYYY-MM-DD.md format
- Shows entries in reverse chronological order (most recent first)
- Indicates days with no journal entries
- Highlights action items and decisions for easy scanning
- Supports custom day ranges for deeper historical context