---
source_kind: web
url: https://code.claude.com/docs/en/hooks
retrieved: 2026-10-24T13:46:02+09:00
licence_note: "unknown; documentation summarised, nothing quoted"
archive_status: saved
archive_url: http://web.archive.org/web/20261019030048/https://code.claude.com/docs/en/hooks
archive_timestamp: 2026-10-19T03:00:48+00:00
body_sha256: d8800ea0edeea113a34d4d8868a27b6299e92f4668dea17c44bdb4c920736151
read_via: raw
verify_by: hash
---
Claude Code hooks reference. Hooks are commands configured in settings that run on events such as PreToolUse, receiving the event as JSON on stdin. Exit code 2 has a per-event meaning; for PreToolUse it blocks the tool call, and the hook's stderr is shown to Claude as the reason. Other non-zero exit codes are treated as non-blocking errors.
