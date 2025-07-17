# Personal Assistant Prompts (for Claude MCP)
This is an experiment to use Claude desktop chat, MCP tools, and natural language prompts to create a functional personal assistant focused on productivity.

## What it does
This assistant manages structured periodic reviews of tasks, calendars, projects, and meeting notes and maintains a journal. The files included are:
1. [Project Rules](project-rules.md) is used as project instructions inside a Claude Project on desktop. It references your local filesystem for other instructions. This provides flexibility in editing and updating prompts without having to delete and reload files into the desktop project.
2. [Review](review.md) is an instruction set for a periodic review that can be conducted daily or ad-hoc. It contains a detailed workflow about reviewing tasks, calendar, projects, notes, and writing and reviewing a journal.
3. [Weekly Review](weekly-review.md) a more comprehensive review, designed to be run once weekly.

## Requirements / Assumptions
### Core requirements
1. Claude desktop
1. Filesystem MCP (Extension) enabled

### Optional/modifiable requirements
These are specific to my task, calendar, and specific document management. You can modify the prompts and connectors as needed.
1. Todoist with a very specific setup (See "Todoist Notes")
1. [Todoist MCP](https://github.com/Doist/todoist-mcp)
1. Google Calendar and enabled extension
1. Google Drive and enabled extension

## Setup Notes
1. Clone this to a directory.
1. Update [project-rules.md](project-rules.md) to reference the folder instead of my example folder as well as a folder to store journal files.
1. Setup a Claude Project and put the content of [project-rules.md](project-rules.md) into the project instructions.
1. Make any modifications to the review processes to suit your needs.
1. Enable the Filesystem and Google extensions in Claude settings and in the "Search and Tools" box in the Claude Chat window
1. Set the Filesystem permissions to have access to the folder where you
1. Install and configure [Todoist MCP](https://github.com/Doist/todoist-mcp)
1. Test the integrations in chat by asking for data from your sources
1. Start a chat inside the Claude project and run a review

## Enhancements to come
1. Slack and gmail integration
1. Backup and git integration for filesystem files
1. Privacy management for MCP logs (?)
