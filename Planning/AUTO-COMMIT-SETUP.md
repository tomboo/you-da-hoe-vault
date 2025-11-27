# Auto-Commit Setup Instructions

The auto-commit script is ready at `.git/hooks/auto-commit.sh`.

## Manual Execution

You can run it manually anytime:

```bash
cd ~/Projects/you-da-hoe-vault
.git/hooks/auto-commit.sh
```

## Automatic Execution Options

### Option 1: Cron Job (Runs Every 15 Minutes)

```bash
# Edit your crontab
crontab -e

# Add this line (runs every 15 minutes):
*/15 * * * * cd ~/Projects/you-da-hoe-vault && .git/hooks/auto-commit.sh >> .git/logs/auto-commit.log 2>&1
```

### Option 2: Launchd (macOS Native, Recommended)

Create `~/Library/LaunchAgents/com.vault.autocommit.plist`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.vault.autocommit</string>
    <key>ProgramArguments</key>
    <array>
        <string>/Users/tom/Projects/you-da-hoe-vault/.git/hooks/auto-commit.sh</string>
    </array>
    <key>StartInterval</key>
    <integer>900</integer>
    <key>StandardOutPath</key>
    <string>/Users/tom/Projects/you-da-hoe-vault/.git/logs/auto-commit.log</string>
    <key>StandardErrorPath</key>
    <string>/Users/tom/Projects/you-da-hoe-vault/.git/logs/auto-commit-error.log</string>
</dict>
</plist>
```

Then load it:
```bash
launchctl load ~/Library/LaunchAgents/com.vault.autocommit.plist
```

### Option 3: Manual (No Automation)

Just run the script when you start/end writing sessions:

```bash
# Before closing Obsidian
cd ~/Projects/you-da-hoe-vault && .git/hooks/auto-commit.sh
```

## Testing

Test the script now:

```bash
cd ~/Projects/you-da-hoe-vault
echo "Test file" > test.md
.git/hooks/auto-commit.sh
git log -1
rm test.md
```

## Remote Push

The script does **not** push to GitHub by default (to avoid network delays).

To enable auto-push, edit `.git/hooks/auto-commit.sh` and uncomment this line:
```bash
# git push origin main 2>&1 | tee -a "$LOG_DIR/auto-commit.log"
```

## Logs

Auto-commit logs are saved to:
- `.git/logs/auto-commit.log` (output)
- `.git/logs/auto-commit-error.log` (errors, if using launchd)

View recent activity:
```bash
tail -20 ~/Projects/you-da-hoe-vault/.git/logs/auto-commit.log
```
