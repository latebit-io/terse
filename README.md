# terse

Agent rule to reduce tokens and cut the bull sh$t.

`terse.md` is a portable output style. Drop it in (or symlink it) wherever your agent reads rules.

## Usage

### Claude Code
Recommended — install as an output style (toggleable, scoped to formatting):
```
mkdir -p ~/.claude/output-styles
cp terse.md ~/.claude/output-styles/terse.md
# activate
/output-style terse
```
Per-project variant:
```
mkdir -p .claude/output-styles
cp terse.md .claude/output-styles/terse.md
```
Fallback — append its body to `CLAUDE.md` to apply as a project rule (always-on, but adds to every turn's system prompt).

### Cursor
```
mkdir -p .cursor/rules
cp terse.md .cursor/rules/terse.mdc
```
Set `alwaysApply: true` in the frontmatter, or scope with `globs:`.

### Windsurf
```
mkdir -p .windsurf/rules
cp terse.md .windsurf/rules/terse.md
```
Or append to `.windsurfrules` for repo-wide application.

### Codex / AGENTS.md agents
Append `terse.md` body to `AGENTS.md` at repo root. Works for OpenAI Codex, Jules, Aider (`--read AGENTS.md`), and other agents that follow the AGENTS.md convention.

### Aider
```
aider --read terse.md
```
Or add to `.aider.conf.yml`:
```yaml
read:
  - terse.md
```

### Cline / Roo Code
Paste body into Settings → Custom Instructions, or add to `.clinerules` at repo root.

### Continue.dev
Add to `~/.continue/config.json` under `systemMessage`, or reference as a rule file in `.continue/rules/`.

### Zed
Append body to `.rules` at repo root.

### Generic / system prompt
Prepend `terse.md` body to your system prompt for any agent or chat UI that accepts custom instructions.
