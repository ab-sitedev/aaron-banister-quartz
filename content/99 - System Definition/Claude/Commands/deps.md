Check that all dependencies for Claude Code slash commands are present and working on this device. Run each check via Bash and report the results.

## Checks to run

### 1. obsidian CLI
The `obsidian` CLI is the primary tool used across nearly every slash command. Run:
```bash
which obsidian && obsidian --version
```
If missing or erroring, flag it — most slash commands will not work without it.

### 2. obsidian CLI subcommands
Several specific subcommands are actively used. Spot-check that they respond without error:
```bash
obsidian tags counts sort=count format=json 2>&1 | head -5
obsidian tasks todo format=json 2>&1 | head -5
obsidian recents 2>&1 | head -5
obsidian orphans 2>&1 | head -5
```
Flag any that return an error or "unknown command".

### 3. .claude/CLAUDE.md symlink
Project instructions are stored in the vault and symlinked into `.claude/`. Run:
```bash
ls -la "/Users/aaron/Obsidian Vaults/Aaron Banister/.claude/CLAUDE.md"
```
Confirm it is a symlink (`->`) pointing to `99 - System Definition/Claude/CLAUDE.md`. If it's a regular file or missing, inform the user to fix it by establishing the symlinks per [[New Device Setup]].

### 4. .claude/commands symlink
Slash commands are stored in the vault and symlinked into `.claude/`. Run:
```bash
ls -la "/Users/aaron/Obsidian Vaults/Aaron Banister/.claude/commands"
```
Confirm it is a symlink (`->`) pointing to `99 - System Definition/Claude/Commands`. If it's a regular file or missing, inform the user to fix it by establishing the symlinks per [[New Device Setup]].

### 5. Bash availability
The `/stale` command uses `find`, `xargs`, `stat`, `sort`, `awk`, and `sed`. These are standard macOS tools but worth confirming on a new device:
```bash
which find xargs stat sort awk sed
```
Flag any that are missing.

---

## Report format

Present results as a table:

| Dependency | Status | Notes |
|---|---|---|
| obsidian CLI | ✅ / ❌ | version or error |
| obsidian subcommands | ✅ / ⚠️ / ❌ | list any failing ones |
| CLAUDE.md symlink | ✅ / ❌ | path or missing |
| commands symlink | ✅ / ❌ | path or missing |
| Bash tools | ✅ / ❌ | list any missing |

If anything is missing, suggest the fix. For symlink issues, inform the user to fix it per [[New Device Setup]].
