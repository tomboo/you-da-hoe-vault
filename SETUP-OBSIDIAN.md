# Obsidian Setup Guide

The vault is pre-configured and ready to use! Follow these steps to complete setup.

## Step 1: Open Vault in Obsidian

1. Launch Obsidian
2. Click "Open folder as vault"
3. Navigate to: `~/Projects/you-da-hoe-vault`
4. Click "Open"

Obsidian will detect the `.obsidian` configuration automatically.

## Step 2: Install Community Plugins

The vault requires 4 community plugins. Install them in this order:

### Enable Community Plugins

1. Open Settings (gear icon) → Community plugins
2. Click "Turn on community plugins"
3. If prompted about safe mode, click "Turn on community plugins"

### Install Required Plugins

Click "Browse" and install each plugin:

1. **Longform**
   - Search: "Longform"
   - Install and Enable
   - Purpose: Manuscript organization and scene management

2. **Novel Word Count**
   - Search: "Novel Word Count"
   - Install and Enable
   - Purpose: Track writing progress and word count goals

3. **Templater**
   - Search: "Templater"
   - Install and Enable
   - Purpose: Use scene/character templates from `Planning/templates/`

4. **Typewriter Mode** (optional)
   - Search: "Typewriter Mode" or "Typewriter Scroll"
   - Install and Enable
   - Purpose: Keeps cursor centered while typing (focus mode)

## Step 3: Configure Templater

1. Settings → Templater
2. Set "Template folder location" to: `Planning/templates`
3. Enable "Trigger Templater on new file creation" (optional)
4. Click "Save"

## Step 4: Configure Novel Word Count (optional)

1. Settings → Novel Word Count
2. Set "Folder to track" to: `Manuscript`
3. Set daily word count goal (e.g., 1000 words)
4. Choose display preferences

## Step 5: Test Templates

1. Press `Cmd+P` (macOS) or `Ctrl+P` (Windows) to open command palette
2. Type "Templater: Create new note from template"
3. Select a template:
   - `scene.md` - For new scenes
   - `character.md` - For character profiles
   - `chapter.md` - For chapter organization
4. Fill in the placeholders (marked with `{{...}}`)

## Step 6: Explore the Vault

### Library (Read-Only)
- **Library/scenes/** - 566 scenes from depot archive
- Browse for reference and continuity checking
- Search using Obsidian's search (Cmd+Shift+F)

### Manuscript (Active Work)
- **Manuscript/scenes/** - Your active writing space
- Create new scenes here
- Edit and revise existing work

### Planning & Research
- **Planning/templates/** - Scene, character, chapter templates
- **Planning/session-notes/** - Daily writing session notes
- **Research/** - World-building, character notes, timelines

## Step 7: Test Auto-Commit (Optional)

The auto-commit script is ready at `.git/hooks/auto-commit.sh`.

See `Planning/AUTO-COMMIT-SETUP.md` for:
- Manual execution instructions
- Cron job setup (every 15 minutes)
- Launchd setup (macOS native)

Test it now:
```bash
cd ~/Projects/you-da-hoe-vault
echo "Test" > test.md
.git/hooks/auto-commit.sh
git log -1
rm test.md
```

## Quick Reference

### Create New Content
- **New scene:** Cmd+P → "Templater: Create new note from template" → scene.md
- **New character:** Same process → character.md
- **New chapter:** Same process → chapter.md

### Search Library
- **Full-text search:** Cmd+Shift+F
- **Quick switcher:** Cmd+O (find by filename)
- **Graph view:** Cmd+G (see connections)

### Git Commands (via Terminal)
```bash
cd ~/Projects/you-da-hoe-vault
git status                    # See changes
git log -5 --oneline         # Recent commits
.git/hooks/auto-commit.sh    # Manual commit
git push                     # Push to GitHub
```

### Claude Code Commands
Open Claude Code in the vault directory:
```bash
cd ~/Projects/you-da-hoe-vault
# Then use these slash commands:
/session-start        # Start writing session
/session-end          # End session, create note
/manual-commit        # Commit with custom message
/search-library       # Search Library scenes
```

## Tips

1. **Library is read-only** - Don't edit files in Library/. Copy to Manuscript/ if you want to revise.
2. **Use templates** - Consistent structure helps with organization
3. **Commit often** - Use auto-commit or manual commits to preserve work
4. **Search before writing** - Check Library for existing scenes on same topic
5. **Tags help** - Use YAML frontmatter tags for organization

## Troubleshooting

**Plugins not showing up?**
- Make sure "Community plugins" is enabled in Settings
- Refresh the plugin list

**Templates not working?**
- Check Templater settings point to `Planning/templates`
- Make sure Templater plugin is enabled

**Auto-commit not working?**
- Make sure script is executable: `chmod +x .git/hooks/auto-commit.sh`
- Test manually first before setting up cron/launchd

**Can't find files?**
- Use Cmd+O (Quick Switcher) to search by filename
- Use Cmd+Shift+F for full-text search

## Next Steps

1. Browse Library scenes to familiarize yourself with existing content
2. Create a test scene using the scene template
3. Set up auto-commit if desired
4. Start writing!

Enjoy your writing workspace!
