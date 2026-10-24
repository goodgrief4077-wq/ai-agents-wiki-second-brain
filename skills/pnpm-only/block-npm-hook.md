# block-npm hook (Claude Code, PreToolUse on Bash)

Save the script as `~/.claude/hooks/block-npm.sh` and `chmod +x` it. It reads the tool call as JSON on stdin and exits 2 to block when `npm` or `npx` is used as a command. Exit 2 on PreToolUse blocks the call and shows the message to the agent.

It ignores heredoc bodies and quoted strings (commit messages, grep patterns), but still checks the payload of `bash -c` and `sh -c`.

```bash
#!/usr/bin/env bash
# PreToolUse(Bash): refuse npm/npx; pnpm only.
python3 -I -c '
import json, re, sys
cmd = json.load(sys.stdin).get("tool_input", {}).get("command", "")
# Heredoc bodies are data, not commands.
cmd = re.sub(r"<<-?\s*([\x27\"]?)(\w+)\1[^\n]*\n.*?^\s*\2\s*$", "", cmd, flags=re.S | re.M)
# Quoted strings are arguments, except bash -c / sh -c payloads.
cmd = re.sub(r"\b(?:ba)?sh\s+-c\s+([\x27\"])(.*?)\1", r"; \2", cmd, flags=re.S)
cmd = re.sub(r"\x27[^\x27]*\x27|\"(?:\\.|[^\"\\])*\"", "\x27\x27", cmd)
pat = r"(?:^|[;&|(`]|\$\(|\b(?:sudo|exec|env|command)\b|\s--)\s*(?:npm|npx)(?=\s|$)"
if re.search(pat, cmd, re.M):
    print("Blocked: npm/npx are not allowed. Use pnpm (pnpm add, pnpm dlx, pnpm run).", file=sys.stderr)
    sys.exit(2)
'
```

Settings entry (add to the existing `hooks.PreToolUse` list in `~/.claude/settings.json`, do not replace other hooks):

```json
{"matcher": "Bash", "hooks": [{"type": "command", "command": "bash ~/.claude/hooks/block-npm.sh"}]}
```

## Test cases
Feed each as `{"tool_input":{"command":"<case>"}}` on stdin and check the exit code.

| Expect | Command |
|---|---|
| block (2) | `npm install x` |
| block | `npx foo` |
| block | `cd a && npm run b` |
| block | `x \| npx y` |
| block | `sudo npm i -g z` |
| block | `mise exec -- npm -v` |
| block | `echo $(npm bin)` |
| block | `bash -c 'npm i'` |
| block | a heredoc, then `npm i` on the line after its terminator |
| allow (0) | `pnpm dlx some-tool` |
| allow | `echo "npm/npx links trashed"` |
| allow | `git commit -m "remove the npm copy"` |
| allow | a heredoc whose body mentions npm |
| allow | `grep -nE 'Installation\|npm install -g' file` |
