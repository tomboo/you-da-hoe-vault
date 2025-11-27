# Session Start - Writing Session

You are starting a new writing session on the **you-da-hoe** novel vault.

## Tasks

1. **Check git status and show uncommitted changes**
   ```bash
   git status
   ```

2. **Show last 5 commits**
   ```bash
   git log -5 --oneline --decorate
   ```

3. **Count scenes in each directory**
   ```bash
   echo "Library scenes: $(ls Library/scenes/*.md 2>/dev/null | wc -l)"
   echo "Manuscript scenes: $(ls Manuscript/scenes/*.md 2>/dev/null | wc -l)"
   ```

4. **Show recent file modifications (last 24 hours)**
   ```bash
   find . -name "*.md" -type f -mtime -1 -not -path "./.git/*" -not -path "./Library/*" 2>/dev/null | head -10
   ```

5. **Check for any uncommitted work**
   - If there are uncommitted changes, ask if they want to commit them before starting
   - Suggest running auto-commit script if needed

6. **Ask what the author wants to work on today:**
   - Write a new scene?
   - Edit an existing scene?
   - Work on character profiles or research?
   - Review Library scenes for reference?
   - Planning or outlining?

7. **Offer assistance:**
   - Search Library for specific scenes/characters
   - Check continuity with previous work
   - Help brainstorm or work through writing challenges

## Output Format

```
=== Writing Session Started ===

Current Status:
- Library: [N] scenes (depot archive)
- Manuscript: [N] scenes (active work)
- Uncommitted changes: [Yes/No]

Recent Commits:
[Show last 3 commits with dates]

Recent Activity (last 24h):
[List recently modified files]

What would you like to work on today?
```

## Notes

- Be encouraging and supportive
- Keep responses focused on the writing task
- Suggest using templates for new content
- Remind about auto-commit if editing for a while
