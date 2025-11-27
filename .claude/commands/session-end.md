# Session End - Writing Session

End the current writing session and save all work.

## Tasks

1. **Show current git status**
   ```bash
   git status
   ```

2. **Show diff of changes**
   ```bash
   git diff --stat
   ```

3. **Count words added/modified (if possible)**
   - Compare current state to last commit
   - Estimate word count delta for modified scenes

4. **Create session summary:**
   - List all modified files
   - Note new files created
   - Calculate approximate word count progress

5. **Commit all changes with descriptive message**
   ```bash
   git add -A
   git commit -m "Session [DATE]: [SUMMARY]

   - [List of changes]
   - Word count: +[N] words (approximate)
   - Files modified: [N]
   - Files created: [N]"
   ```

6. **Create session note in `Planning/session-notes/`**
   - Filename: `YYYY-MM-DD-session.md`
   - Include summary of work completed
   - Note any continuity issues or questions
   - List goals for next session

7. **Optional: Push to GitHub**
   - Ask if they want to push changes to remote
   - `git push origin main`

8. **Show session summary**

## Session Note Template

```markdown
# Session YYYY-MM-DD

## Summary
[1-2 sentence overview of what was accomplished]

## Work Completed

### New Content
- [List new scenes/chapters created]

### Edits
- [List scenes edited]

### Research/Planning
- [Any research or planning work]

## Statistics
- Session duration: ~[N] hours
- Words added: +[N] (approximate)
- Files modified: [N]
- Files created: [N]

## Next Session Goals
- [ ] [Task 1]
- [ ] [Task 2]
- [ ] [Task 3]

## Notes
- [Any continuity issues noticed]
- [Questions to resolve]
- [Ideas for future scenes]

## Continuity Reminders
- [Characters mentioned]
- [Plot points advanced]
- [Timeline notes]
```

## Output Format

```
=== Session Ended ===

Work Summary:
- New scenes: [N]
- Edited scenes: [N]
- Words added: ~[N]
- Duration: ~[N] hours

Changes committed: [commit hash]
Session note created: Planning/session-notes/[filename]

[Optional: Pushed to GitHub]

Great work today!
```

## Notes

- Be encouraging about progress made
- Even small progress is worth celebrating
- Remind about backing up important work
- Suggest next steps if appropriate
