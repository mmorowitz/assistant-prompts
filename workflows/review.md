# Review Workflow (Two-Stage Process)

## Stage 1: Context Gathering
**Purpose**: Systematically load all relevant data into context without user interruption.

### Data Collection (Automated)
Execute the following slash commands in sequence to gather comprehensive context:

1. **Project Context**
   - `/list-project-descriptions` - Load all project purposes and descriptions

2. **Task Context** 
   - `/list-active-tasks` - Get inbox, due today, and overdue tasks
   - `/list-now-tasks` - Get current week @NOW tasks
   - `/list-tomorrow-tasks` - Get tomorrow's scheduled tasks
   - `/list-stalled-projects` - Identify projects without clear next actions

3. **Calendar Context**
   - `/list-upcoming-meetings` - Get remaining meetings today and tomorrow

4. **Historical Context**
   - `/list-recent-journal [7]` - Review last 7 days of journal entries
   - `/list-gdocs [20]` - Get recent Google Drive documents

5. **Timestamp Context**
   - Note current date/time and time since last review

## Stage 2: Analysis and Recommendations
**Purpose**: Process gathered data and provide actionable insights with user interaction.

### Pre-Analysis Check
- [ ] **STOP AND WAIT** - Confirm user has processed all inboxes (personal email, work email, Slack, GitHub) to zero items. Wait for confirmation before proceeding.

### Context Analysis Report
Present findings from Stage 1 data in this format:

#### **Current Status Summary**
- Active task load: [X tasks in inbox, Y due today, Z overdue]
- @NOW task commitment: [X tasks across Y projects] 
- Tomorrow's workload: [X tasks + Y meetings]
- Stalled projects: [List projects needing attention]

#### **Key Insights**
- Pattern analysis from recent journal entries
- Meeting preparation needs from calendar review  
- Document review priorities from recent GDrive activity
- Project momentum assessment

#### **Priority Recommendations**
1. **Immediate Actions** (today): [High-priority items requiring attention]
2. **This Week Focus** (@NOW tasks): [Weekly planning recommendations]
3. **Project Maintenance** (stalled projects): [Projects needing next actions]
4. **Tomorrow Preparation** (planning): [Prep work and scheduling needs]

### Analysis and Recommendations Report

Present a comprehensive review report with actionable recommendations:

#### **Executive Summary**
- Current system health and status
- Key patterns and insights from data analysis
- Priority focus areas requiring immediate attention

#### **Action Recommendations**

**Immediate (Today):**
- List specific tasks/actions needed today
- Flag any urgent conflicts or deadline issues
- Identify preparation needs for tomorrow

**This Week (@NOW Tasks):**
- Analyze @NOW task load and priority distribution
- Recommend adjustments for realistic weekly commitment
- Suggest focus areas and task sequencing

**Project Maintenance:**
- Identify stalled projects needing attention
- Recommend next actions or cancellation decisions
- Flag projects with unclear momentum

**Schedule Optimization:**
- Highlight calendar conflicts or optimization opportunities
- Suggest meeting decisions (attend/decline/reschedule)
- Recommend time blocking for focused work

#### **Follow-up Items**
- Specific tasks to track for next review
- Patterns to monitor over time
- System improvements or workflow adjustments

#### **Journal Entry Creation**
- [ ] **CONFIRM ONLY** - Ask user for any additional thoughts or important events to include
- Create comprehensive journal entry with review findings
- [ ] **CONFIRM ONLY** - Share draft journal entry for approval before saving

## Important Notes
- **Stage 1** runs without user interruption - gather all data first
- **Stage 2** presents analysis as a comprehensive report with actionable recommendations
- Only two confirmation points: inbox clearance + journal entry approval
- Focus on patterns, conflicts, and optimization opportunities rather than raw data
- Present specific, actionable recommendations organized by time horizon
- Always end with clear next actions and follow-up commitments