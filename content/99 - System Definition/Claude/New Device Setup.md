# Claude Code — New Device Setup

Claude Code looks for project instructions and slash commands in `.claude/` inside the working directory. These files live inside the vault (so Obsidian Sync moves them between devices), but `.claude/` itself is not synced. You need to create two symlinks manually on each new device before any slash commands will work.

---

## Mac

Open Terminal. Set your vault path, then create the symlinks:

```bash
VAULT="$HOME/Obsidian/Aaron Banister"

mkdir -p "$VAULT/.claude"

ln -s "$VAULT/99 - System Definition/Claude/CLAUDE.md" "$VAULT/.claude/CLAUDE.md"

ln -s "$VAULT/99 - System Definition/Claude/Commands" "$VAULT/.claude/commands"
```

> Adjust `VAULT` if your vault is in a different location. Run `obsidian vaults verbose` to find the exact path.

Verify:

```bash
ls -la "$VAULT/.claude/"
```

Both entries should show `->` pointing into `99 - System Definition/Claude/`.

---

## Windows

Enable **Developer Mode** first: Settings → System → For Developers → Developer Mode

Then open PowerShell and run:

```powershell
$vault = "C:\Users\YourName\Obsidian\Aaron Banister"

New-Item -ItemType Directory -Force -Path "$vault\.claude"

New-Item -ItemType SymbolicLink -Force `
    -Path "$vault\.claude\CLAUDE.md" `
    -Target "$vault\99 - System Definition\Claude\CLAUDE.md"

New-Item -ItemType SymbolicLink -Force `
    -Path "$vault\.claude\commands" `
    -Target "$vault\99 - System Definition\Claude\Commands"
```

Verify:

```powershell
Get-Item "$vault\.claude\*" | Select-Object Name, LinkType, Target
```

---

## After Setup

Open Claude Code from the vault root. Project instructions and slash commands will load automatically.

Run `/deps` to confirm everything is wired up correctly.
