Start a new development session by creating a session file in `~/.claude/sessions/` with the format `YYYY-MM-DD-HHMM-$ARGUMENTS.md` (or just `YYYY-MM-DD-HHMM.md` if no name provided).

First, ensure the global sessions directory exists: `mkdir -p ~/.claude/sessions`

Next, check if this is a git repository and offer to initialize if needed:
1. Run `git status 2>/dev/null` to check if git repo exists
2. If not a git repo, ask user if they want to initialize git for better session tracking
3. If user agrees, run:
   - `git init`
   - `git add .`
   - `git commit -m "Initial commit before starting session"`
4. Note the git status in the session file

The session file should begin with:
1. Session name and timestamp as the title
2. Project context section showing:
   - Current working directory
   - Project name (extract from directory name or git repo)
   - Git repository URL if available
3. Session overview section with start time
4. Goals section (ask user for goals if not clear)
5. Empty progress section ready for updates

Include project context template:
```markdown
## Project Context
- **Directory**: [current working directory]
- **Project**: [project name from directory or git]
- **Repository**: [git remote URL if available, or "Newly initialized" if just created]
- **Git Status**: [Repository status - existing, newly initialized, or none]
```

After creating the file, create or update `~/.claude/sessions/.current-session` to track the active session filename.

Confirm the session has started and remind the user they can:
- Update it with `/project:session-update`
- End it with `/project:session-end`