# Search Library

Search the Library/scenes directory for specific content, characters, or themes.

## Tasks

1. **Ask what to search for:**
   - Character name
   - Location/setting
   - Theme or keyword
   - Plot element

2. **Perform search using grep**
   ```bash
   # Search for keyword in all scenes
   grep -ri "keyword" Library/scenes/ --include="*.md"

   # Show filenames only
   grep -ril "keyword" Library/scenes/ --include="*.md"

   # Show context (lines before/after)
   grep -ri "keyword" Library/scenes/ --include="*.md" -B 2 -A 2
   ```

3. **Parse and present results:**
   - Count: How many scenes mention this
   - List: Scene filenames that contain matches
   - Excerpts: Brief quotes showing context
   - Suggest: Related scenes to review

4. **Offer follow-up:**
   - Search for related terms
   - Open specific scenes for full content
   - Create summary of character/theme across scenes

## Output Format

```
Searching Library for: "[search term]"

Found in [N] scenes:

1. [Scene title/filename]
   "...excerpt with search term highlighted..."

2. [Scene title/filename]
   "...excerpt with search term highlighted..."

3. [Scene title/filename]
   "...excerpt with search term highlighted..."

[Show up to 10 results]

Would you like to:
- See more results
- Search for related terms
- Open a specific scene
- Create a character/theme summary
```

## Advanced Search Examples

**Find scenes with specific character:**
```bash
grep -ril "James" Library/scenes/*.md
```

**Find scenes in specific location:**
```bash
grep -ri "Healing House" Library/scenes/*.md
```

**Find scenes by date pattern in filename:**
```bash
ls Library/scenes/ | grep "^01.*2025"
```

**Find scenes with character interactions:**
```bash
grep -ri "James.*Rachel\|Rachel.*James" Library/scenes/*.md
```

## Notes

- Case-insensitive search by default
- Show enough context to understand usage
- Preserve formatting and quotes
- Suggest refinements if too many/few results
- Help identify patterns and continuity
