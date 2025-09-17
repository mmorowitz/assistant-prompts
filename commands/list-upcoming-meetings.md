# /list-upcoming-meetings

## Purpose
Retrieves remaining meetings today (after current time) and all meetings for the following day from Google Calendar, excluding tentative events for current scheduling context.

## Usage
```
/list-upcoming-meetings
```

## What it does

### Meeting Extraction
Gathers all confirmed meetings requiring current attention:
- Remaining meetings today after the current time
- All meetings scheduled for tomorrow
- Excludes tentative events (informational only)
- Shows meeting times, titles, and locations

## Command Implementation

When this command is invoked:

1. **Get current time:**
   ```
   mcp__google-calendar__get-current-time()
   ```
   *Returns current time with timezone info*

2. **Get remaining meetings today:**
   ```
   mcp__google-calendar__list-events(
     calendarId: "primary",
     timeMin: "2025-08-28T19:37:59-05:00",  // current time in RFC3339
     timeMax: "2025-08-28T23:59:59-05:00",  // end of today
     timeZone: "America/Chicago"
   )
   ```

3. **Get tomorrow's meetings:**
   ```
   mcp__google-calendar__list-events(
     calendarId: "primary",
     timeMin: "2025-08-29T00:00:00-05:00",  // start of tomorrow
     timeMax: "2025-08-29T23:59:59-05:00",  // end of tomorrow
     timeZone: "America/Chicago"
   )
   ```

4. **Filter and format:**
   - Exclude events marked as "tentative" in your response status
   - Show time, title, location, and attendees
   - Group by day for clarity
   - **CRITICAL**: Make TWO separate API calls - one for today, one for tomorrow

## Example Output Format

```
## Upcoming Meetings

**Today (remaining):**
- No meetings remaining today

**Tomorrow (August 29):**
- 9:00 AM - 10:00 AM: Morowitz / Haley Weekly Check-in
  *Strategic planning discussion*

- 9:30 AM - 10:00 AM: TBSPs Daily Sync (tentative)
  *Team standup*

- 10:00 AM - 10:30 AM: Yashvi / Michael 1-on-1
  *LR03 (1)*

- 1:30 PM - 2:00 PM: Zenhub planning session
  *PM coordination meeting*

- 3:00 PM - 4:00 PM: Michael / John - Career Development Time
  *1:1 career discussion*

**Tentative (can skip):**
- 9:45 AM - 10:00 AM: CX - Growth Sync
- 10:00 AM - 10:15 AM: Stand - CX Expansion  
- 10:45 AM - 11:00 AM: CX - Engagement Sync
```

## Integration with Review Workflow

This command supports daily planning by:
- Providing visibility into upcoming time commitments
- Excluding tentative events that aren't real commitments
- Showing meeting context (location, attendees) for preparation
- Separating today vs tomorrow for better time management
- Supporting scheduling decisions with current availability

## Notes

- Always ignores tentative events per project rules
- Uses primary calendar by default
- Shows times in user's local timezone
- Includes location and attendee count when available
- Groups meetings by day for easier scanning
- Only shows meetings after current time for today