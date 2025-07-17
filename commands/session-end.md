End the current development session by:

1. Check `~/.claude/sessions/.current-session` for the active session
2. If no active session, inform user there's nothing to end
3. If session exists, handle git repository management:
   a) Offer to commit any remaining changes:
      - Check `git status --porcelain` for uncommitted changes
      - If there are changes, ask user if they want to commit them
      - If yes, run: `git add .` and `git commit -m "Session end: [session-name] - [brief summary]"`
   
   b) Check for unpushed commits and offer to push:
      - Run `git status` to check if branch is ahead of origin
      - If there are unpushed commits, ask user if they want to push to remote
      - If yes, run: `git push origin [current-branch]`
   
   c) Handle repository-specific tasks:
      - If current directory contains 'claude-sessions' or similar session management repos:
        * Check if command files were modified
        * Offer to update README.md with current examples and documentation
        * If documentation updated, commit and push those changes too
   
4. Then append a comprehensive summary including:
   - Session duration
   - Git summary:
     * Total files changed (added/modified/deleted)
     * List all changed files with change type
     * Number of commits made during session
     * Final git status
     * Repository URL if available
   - Todo summary:
     * Total tasks completed/remaining
     * List all completed tasks
     * List any incomplete tasks with status
   - Key accomplishments
   - All features implemented
   - Problems encountered and solutions
   - Breaking changes or important findings
   - Dependencies added/removed
   - Configuration changes
   - Deployment steps taken
   - Lessons learned
   - What wasn't completed
   - Tips for future developers

5. Empty the `~/.claude/sessions/.current-session` file (don't remove it, just clear its contents)
6. Inform user the session has been documented and provide summary of git actions taken:
   - Whether changes were committed
   - Whether commits were pushed to remote
   - Whether documentation was updated
   - Repository status after session end

The summary should be thorough enough that another developer (or AI) can understand everything that happened without reading the entire session.