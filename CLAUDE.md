# CLAUDE.md

This is an Obsidian vault for the novel "you-da-hoe".

---

## Vault Structure

- **Library/scenes/** - Read-only archive from depot (225 scenes from firebase-depot)
- **Manuscript/scenes/** - Active work, editing and new scenes
- **Research/** - World-building, character notes, reference material
- **Planning/** - Outlines, templates, session notes

---

## Important Context

**Novel:** you-da-hoe
**Genre:** [To be documented]
**Status:** Prototype phase - setting up vault workflow
**depot Project:** `you-da-hoe` (225 converted scenes)

**Key Characters:**
- [To be documented after reviewing Library content]

**Setting:**
- [To be documented after reviewing Library content]

**Plot Summary:**
- [To be documented after reviewing Library content]

---

## Working with Claude Code

When helping with this vault project, Claude should:

1. **Understand the vault structure** - Library is read-only reference, Manuscript is active work
2. **Respect the author's voice** - Suggest improvements, don't override writing style
3. **Focus on specific requests** - Don't proactively rewrite content unless asked
4. **Use git for history** - Check `git log` to see recent changes
5. **Reference existing scenes** - Search Library/ for relevant content before suggesting new material
6. **Maintain continuity** - Check character profiles and timelines before making suggestions

---

## Useful Commands

### Session Management

Use these slash commands (to be created in `.claude/commands/`) to manage writing sessions:

- `/session-start` - Start new writing session, show recent changes
- `/session-end` - End session, commit work, create session note
- `/manual-commit` - Commit current changes with custom message

### Scene Operations

- **Create new scene:** Use Templater in Obsidian (Cmd+P → "Templater: Create new note from template")
- **Find related scenes:** Search Library/ for character or location mentions
- **Check continuity:** Review Planning/timelines/ and Research/characters/

---

## Git Workflow

**Manual commit (current approach):**
```bash
git add -A
git commit -m "Describe changes"
git push
```

**View history:**
```bash
git log --oneline -10                    # Last 10 commits
git diff HEAD~1                          # Changes since last commit
git show <commit-hash>:<file>            # View old version
```

**Restore old version:**
```bash
git checkout HEAD~N -- <file>            # Restore from N commits ago
```

**Future:** Auto-commit script will be added after testing workflow.

---

## Open Questions / TODOs

- [ ] Review Library content to document genre, characters, setting, plot
- [ ] Where should completed chapters go? (Manuscript/chapters/?)
- [ ] How to organize research notes?
- [ ] Should we create character profile templates?
- [ ] Timeline tracking - manual notes or structured system?
- [ ] Set up auto-commit script (cron or manual)?

---

## Development Philosophy

This vault follows the firebase-depot project philosophy:

**Simple > Clever**
- Hand-built prototype first
- Learn from real usage
- Automate only proven patterns

**Pragmatic > Perfect**
- Start with minimal structure
- Add features as needs emerge
- Avoid over-engineering

---

## Related Documentation

**In firebase-depot repo:**
- `docs/obsidian/PROTOTYPE-PLAN.md` - Complete prototype implementation plan
- `docs/obsidian/README.md` - Obsidian integration architecture overview
- `docs/obsidian/VAULT-ARCHITECTURE.md` - Library/Manuscript pattern details

**This vault:**
- `README.md` - Public-facing vault overview
- `CLAUDE.md` - This file (AI assistant guidance)
- `.claude/commands/` - Session management commands (to be created)

---

## Notes

This vault was created as a hand-built prototype to test the Obsidian + depot workflow.

**Key Goals:**
1. Can author easily find and reference Library scenes?
2. Is Manuscript organization clear and helpful?
3. Does git version control add value without friction?
4. Can Claude Code assist effectively with scene research and continuity?
5. Does the overall workflow feel natural?

**Philosophy:** Build the thing, use the thing, learn from the thing, then automate the thing.

**Initial setup:** 2025-11-26
**Created by:** tomboo (for you-da-hoe project prototype)
