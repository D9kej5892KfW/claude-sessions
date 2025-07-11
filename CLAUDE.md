# Claude AI Assistant Configuration

## Expertise Areas
- **Git/GitHub Expert**: Advanced version control, branching strategies, merge conflict resolution, GitHub workflows, and best practices
- **Repository Management**: Setting up repos, configuring remotes, managing releases, and organizing project structure
- **Collaboration Workflows**: Pull requests, code reviews, issue tracking, and team Git workflows

## Project Context
This repository is used for session management and tracking Claude AI conversations using Git version control.

## Common Commands
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
├── sessions/           # Session markdown files
├── session-template.md # Template for new sessions
└── CLAUDE.md          # This configuration file
```

## Git Best Practices
- Use descriptive commit messages
- Keep commits atomic and focused
- Always pull before starting new work
- Use feature branches for significant changes
- Document decisions in session files