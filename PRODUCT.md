# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary: the AI/agent-engineering community and researchers — people who run
coding agents (Codex, Claude Code, Antigravity) and want to compare how the
agents behave and what their session-trace formats actually capture. They arrive
with a local `.jsonl` trace file (or curiosity satisfied by the bundled
samples), usually from a shared link or a GitHub/community mention.

Secondary: engineers debugging a specific agent session of their own.

## Product Purpose

A client-side viewer for coding-agent session traces. Import a local trace from
Codex, Claude Code, or Antigravity and inspect the full trajectory — system
instructions, messages, reasoning records, tool calls and results, context, and
captured state — through four views: Timeline, Insights (behavior dashboard,
tool flow graph, density strip, interesting moments), Privacy scan, and Raw
schema.

Success for a visit: the visitor understands something concrete about an
agent's behavior or its trace format. Success for the product: it gets shared
and starred in agent-dev communities, and a fraction of visitors discover
ZenML and Kitaru through it.

## Positioning

The only trace viewer that reads all three major coding-agent formats and runs
entirely in the browser — the page makes zero network requests, so traces
(which routinely contain secrets and private code) never leave the machine.
Neighboring tools are either single-vendor or server-backed. The comparative
angle is the identity: same task, three formats, side-by-side understanding of
what each vendor's trace does and doesn't capture.

## Operating Context

- Traces come from real local paths: `~/.codex/sessions/*.jsonl`,
  `~/.claude/projects/<project>/*.jsonl`, and Antigravity's
  `brain/<conversation>/.system_generated/logs/transcript_full.jsonl`.
- Trace files routinely contain secrets, API keys, private code, and personal
  paths; users may screenshot or copy from the viewer, so the product carries
  explicit warnings and a built-in privacy scanner.
- Open source at github.com/zenml-io/agent-trace-viewer; deployed as a static
  site on Cloudflare Pages (direct `wrangler pages deploy`, not git-connected).
- Parsers are grounded in observed files from specific client versions, not
  format contracts; vendors change formats without notice.

## Capabilities and Constraints

- **Binding: zero-network privacy.** The page must make no network requests;
  imported traces are read with the File API and never uploaded, stored, or
  persisted. Enforced today by CSP `default-src 'none'`. Future work must
  preserve this guarantee.
- Single-file delivery is NOT binding — a build step or multiple files are
  acceptable if the tool grows, as long as the privacy guarantee holds.
- Bundled sample traces are synthetic (fictional but format-faithful) and must
  stay clearly labeled as such; real traces must never be bundled.
- The privacy scanner is heuristic and must always present itself as a
  checklist, not a guarantee.
- Terminology: "trace" (a session file), "event" (a normalized record),
  "source"/"agent" (Codex, Claude Code, Antigravity), event kinds
  (message, instruction, reasoning, tool_call, tool_result, context, state,
  metadata).

## Brand Commitments

- Branding stays light: a neutral tool identity with a footer credit to the
  ZenML team. Not visually branded as a ZenML product (no logo/palette
  takeover).
- ZenML (zenml.io) and its sister project Kitaru (kitaru.ai) are the projects
  the tool should quietly route curious visitors toward.
- Name in use: "Agent Trace Viewer" / repo `agent-trace-viewer`.

## Evidence on Hand

- Three synthetic sample traces embedded in the page (same fictional bug-fix
  task in each format) — safe to publish, labeled synthetic in the UI.
- No testimonials, benchmarks, or usage numbers exist; do not fabricate any.

## Product Principles

1. **Nothing leaves the browser.** Every feature must work offline-capable and
   request-free; features that need a server don't belong here.
2. **Evidence over contract.** Present what a file actually contains; label
   parser assumptions and vendor-version grounding honestly.
3. **Comparison is the point.** Views and features should make the three
   formats comparable, not just individually readable.
4. **Treat every trace as radioactive.** Warn, scan, and mask by default;
   never encourage careless sharing.
5. **Useful before branded.** The tool earns attention through utility; ZenML
   and Kitaru discovery rides on credibility, never on interruption.
