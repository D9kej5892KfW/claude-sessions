# Claude AI Assistant Configuration

## Expertise Areas
- **Git/GitHub Expert**: Advanced version control, branching strategies, merge conflict resolution, GitHub workflows, and best practices
- **Repository Management**: Setting up repos, configuring remotes, managing releases, and organizing project structure
- **Collaboration Workflows**: Pull requests, code reviews, issue tracking, and team Git workflows

## Project Context
This repository uses a comprehensive session management system for tracking Claude AI conversations using Git version control and custom slash commands.

## Session Management Commands
Use these custom slash commands for session tracking:

```bash
# Start a new session (with optional name)
/project:session-start [session-name]

# Update progress during development
/project:session-update [notes]

# End session with comprehensive summary
/project:session-end

# View current session status
/project:session-current

# List all past sessions
/project:session-list

# Show help for session commands
/project:session-help
```

## Common Git Commands
```bash
# Session management
git add sessions/
git commit -m "Add session: [description]"
git push origin main

# Branch workflow
git checkout -b feature/session-[number]
git merge main
git branch -d old-branch

# Repository sync
git pull origin main
git fetch --all
git status
```

## Repository Structure
```
/
├── commands/           # Custom slash command definitions
│   ├── session-start.md
│   ├── session-update.md
│   ├── session-end.md
│   ├── session-current.md
│   ├── session-list.md
│   └── session-help.md
├── sessions/           # Session markdown files
│   ├── .current-session # Tracks active session
│   └── [YYYY-MM-DD-HHMM-name].md # Session files
└── CLAUDE.md          # This configuration file
```

## Session Best Practices
- Use descriptive names for sessions that indicate main focus
- Start sessions for significant features or bug fixes
- Update regularly when completing significant tasks
- Document unexpected issues and their solutions
- Always end sessions with `/project:session-end`
- Review past sessions before starting related work

## Git Best Practices
- Use descriptive commit messages
- Keep commits atomic and focused
- Always pull before starting new work
- Use feature branches for significant changes
- Document decisions in session files