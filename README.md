# Agent Trace Viewer

A single-file, client-side viewer for coding-agent session traces. Import a local
trace from **Codex**, **Claude Code**, or **Antigravity (agy)** and inspect the
full trajectory: instructions, user/assistant messages, reasoning records, tool
calls and results, context, and captured state.

## Samples

Each format card has a **Try a sample trace** button — a small synthetic (fictional
but format-faithful) session showing a bug-fix task, embedded inline so the page
still makes zero network requests.

## Privacy

Everything runs in your browser. The selected file is read locally with the File
API — nothing is uploaded, stored, or sent anywhere. Reloading the page discards
the trace. The page ships with a strict CSP (`default-src 'none'`) and makes no
network requests.

Traces can contain secrets and private data (the viewer deliberately shows full
instruction bodies and tool output), so review before sharing screenshots or
copied content.

## Where to find traces

| Agent | Location |
| --- | --- |
| Codex | JSONL files in `~/.codex/sessions` or `~/.codex/archived_sessions` |
| Claude Code | JSONL files in `~/.claude/projects/<project>/` |
| Antigravity | `brain/<conversation>/.system_generated/logs/transcript_full.jsonl` |

## Views

Use the arrow switcher (or ←/→ keys) to cycle between three views per trace:

1. **Timeline** — the normalized event stream, filterable by event type
2. **Insights** — session at a glance: wall clock, tool leaderboard, event mix, reasoning visibility, heaviest events
3. **Raw schema** — record shapes observed plus the normalized event JSON

## Development

It is one dependency-free HTML file. Open `index.html` in a browser, or serve it
with anything static:

```bash
python3 -m http.server
```

## Deployment

Deployed to Cloudflare Pages via direct upload:

```bash
wrangler pages deploy . --project-name agent-trace-viewer
```
