# Command Execution Rules

## Command Execution Policy
- Run all read-only commands without asking for permission
- NEVER run `sudo` or any commands that require password authentication without explicit user permission
- Examples of commands to run freely: `ls`, `cat`, `grep`, `find`, `git status`, `git log`, `python --version`, etc.
- Examples of commands to ask permission for: `sudo`, `rm`, `mv` (when moving to different directories), `git commit`, `git push`, etc.