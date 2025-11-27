# Manual Commit

Manually commit current changes with a custom message.

## Tasks

1. **Show git status with detailed changes**
   ```bash
   git status
   git diff --stat
   ```

2. **List all modified/new files**
   - Categorize: new files, modified files, deleted files
   - Show brief preview of changes

3. **Suggest commit message based on changes**
   - Analyze file changes
   - Generate descriptive message
   - Format: "[Type]: [Brief description]"
   - Examples:
     - "Add: New scene - James confronts Rachel"
     - "Edit: Revise opening chapter for pacing"
     - "Research: Add character profile for Lorenzo"

4. **Ask user to confirm or customize message**

5. **Stage all changes**
   ```bash
   git add -A
   ```

6. **Commit with message**
   ```bash
   git commit -m "[Message]"
   ```

7. **Show commit confirmation**
   ```bash
   git log -1 --stat
   ```

## Output Format

```
Changes to commit:

New files:
- [file1.md]
- [file2.md]

Modified files:
- [file3.md] (+50 lines, -10 lines)
- [file4.md] (+5 lines, -2 lines)

Suggested commit message:
"[Auto-generated message based on changes]"

Would you like to use this message, or provide a custom one?

[After commit]
✓ Changes committed successfully
Commit: [hash] - [message]
[Show files changed and line counts]
```

## Notes

- Keep suggestions concise but descriptive
- Include file counts and change statistics
- Confirm before committing
- Show clear feedback after commit completes
