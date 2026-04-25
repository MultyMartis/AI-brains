# Self-Describe System

## Purpose

Give any AI agent (Cursor, ChatGPT, Codex, etc.) a **fast, repeatable way** to rebuild accurate context about **MCA AI.Pack** and **Main Brain v2** without guessing.

The agent follows a **short trigger** (or loads this spec), reads **canonical files**, and returns a **structured report** in a fixed format.

---

## Trigger concept

Humans and agents agree on **code phrases** that mean: *stop improvising; read the system files and summarize*.

Triggers are **not** magic commands inside software. They are **conventions**: when the user sends one, the assistant must enter **Self-Describe mode** — load sources, apply rules, emit the chosen output structure.

### Example triggers

- `SELF DESCRIBE MCA SYSTEM FULL` — full structured report (see **Modes → FULL**).
- `SELF DESCRIBE MCA SYSTEM SHORT` — minimal snapshot (see **Modes → SHORT**).
- `MCA SYSTEM STATUS` — same family as SHORT; emphasize registry + latest lifecycle headings.
- `LOAD MAIN BRAIN CONTEXT` — same family as FULL; emphasize architecture + index + registry.
- `SELF DESCRIBE MCA SYSTEM FULL USING INTERNAL PROMPTS` — FULL mode; assistant loads `self-describe-full.txt` and sources from workspace when supported (see `prompts/system/self-describe-command.txt`).

**Short aliases supported:**

- `WHOAMI FULL`
- `WHOAMI SHORT`
- `WHOAMI DEBUG`

These map to full system commands.

Additional triggers may be defined by the team; this document defines **behavior**, not a closed list of strings.

---

## Hard dependency (operational)

Self-Describe is **not** standalone narrative. **FULL** and **DEBUG** reports **must** ground truth in:

1. `system/project-registry.md` — which systems exist, paths, status, `next_action`.
2. `logs/lifecycle-log.md` — what changed recently, in what order.

All other sources **support** those two. If either file is unreadable, emit **UNKNOWN** / **FILE ACCESS UNKNOWN** per `system/system-signals.md` and do not invent state.

---

## Data sources

When executing Self-Describe, the agent **must** prefer these sources (paths from `AI-brains` repository root unless a registry entry gives an absolute path):

| Source | Role |
|--------|------|
| `system/ai-brains-system-index.md` | Entry map of core system files |
| `system/main-brain-v2-architecture.md` | Main Brain v2 layers and operating cycle |
| `system/metacode-mission.md` | Mission and product vision |
| `system/v2-ai-brains-roadmap.md` | System roadmap, stages, priorities |
| `system/planning-layer.md` | Planning Layer — decomposition, handoff, SAFE UNKNOWN |
| `system/terminology-map.md` | MCA terms mapped to standard industry terminology |
| `system/engineer-protocol.md` | Engineer-class agents — responsibilities and protocol |
| `system/project-registry.md` | Registered projects, paths, status, next_action |
| `logs/lifecycle-log.md` | Chronological system and project events |
| `system/rule-precedence.md` | Rule stack, SAFE UNKNOWN MODE |
| `system/webgpt-memory-module.md` | WebGPT migration / memory **specification** (what the module is supposed to do) |
| `system/project-architecture-principles.md` | Where roadmaps belong (AI-brains vs project repos) |
| `system/system-signals.md` | Standard integrity / risk markers (`⚠ SYSTEM MAY BE OUTDATED`, `UNKNOWN`, etc.) |
| `system/agent-standard.md` | Agent System — naming, cards, and conventions |
| `system/agent-registry.md` | Agent System — registered agents and status |
| `system/agents/` | Agent System — per-agent folders (`agent-card`, workflow, changelog) |

**Per-project** (when registry points to them):

- Project `workflow-tracker.md` (path from registry)
- Project `lifecycle-log` / `project-state.md` if present and referenced

**Optional (DEBUG mode):**

- Git history / commit messages — only if already available in the session; do not assume access.

---

## Output structure

### FULL mode

The assistant output **must** use this top-level shape (markdown headings):

```text
# MCA AI System Full Report

---

## 1. System identity
## 2. Architecture (Main Brain v2)
## 3. Current state (registry + lifecycle)
## 4. Active systems and projects
## 5. Implemented vs planned (honest)
## 6. How to interact with the system
## 7. Risks / inconsistencies / UNKNOWNs
```

Under each section, use short bullets. Every factual claim should be traceable to a file named in the report or marked **UNKNOWN**.

### SHORT mode

**5–10 lines** maximum:

- What MCA AI.Pack / Main Brain is (one sentence).
- Where the index and architecture live (paths).
- Current priority / phase **only if** stated in `v2-ai-brains-roadmap.md` or registry.
- Active vs paused projects **only from** `project-registry.md`.
- One line: how to continue (e.g. read index → rule precedence → project tracker).

### DEBUG mode

Same sections as FULL, plus:

- Explicit list of **files read** (or **FILE ACCESS UNKNOWN** if not read).
- **Contradictions** between registry, roadmap, and lifecycle (if any), quoted neutrally.
- **Gaps**: items in roadmap not evidenced by implementation files (describe gap without inventing code).

---

## Modes

| Mode | Trigger hint | Output |
|------|----------------|--------|
| **SHORT** | `… SHORT`, `MCA SYSTEM STATUS` | 5–10 lines, no subsections or minimal |
| **FULL** | `… FULL`, `LOAD MAIN BRAIN CONTEXT` | Full report structure above |
| **DEBUG** | `… DEBUG`, `SELF DESCRIBE MCA SYSTEM DEBUG` | FULL + file list + contradictions |

If the user does not specify mode, default to **FULL** when the message contains `FULL`, `MAIN BRAIN`, or `USING INTERNAL PROMPTS`; default to **SHORT** when the message contains `SHORT` or `STATUS`.

---

## System integrity check

When generating a **FULL** or **DEBUG** report, the assistant **must**:

1. **Read** (when possible): recent `logs/lifecycle-log.md` entries, full `system/project-registry.md`, and `system/self-describe-system.md` + `prompts/system/self-describe-full.txt` (contract text).
2. **Compare:**
   - Latest lifecycle events (scopes, `files_changed`, `next_action`) vs what the report would say about “current” systems.
   - Registry rows vs lifecycle claims (e.g. status, phase, paths).
   - Whether Self-Describe **artifacts** (this file + full prompt) **obviously omit** a capability or project **already recorded** in lifecycle/registry (e.g. new section in registry, log says “module added”, but report template still silent).

3. **If a mismatch or stale Self-Describe risk is detected** (lifecycle/registry ahead of what fixed prompts describe, or internal contradiction):

   - Output the standard line from `system/system-signals.md` — **SIGNAL: SYSTEM MAY BE OUTDATED** (exact marker: `⚠ SYSTEM MAY BE OUTDATED`).
   - Then bullet **what changed** (from lifecycle/registry only).
   - Then bullet **what is not reflected** in Self-Describe prompts or this spec (be specific: file/section, or “prompts not yet edited”).
   - **Recommend:** `Run Self-Describe update via Cursor` (manual edit of `self-describe-*.md` / `self-describe-*.txt` per `system/self-update-rules.md`).

4. **If comparison cannot run** (no file access): emit **UNKNOWN** per `system/system-signals.md`; do not guess “up to date.”

**SHORT** mode: one-line integrity hint if obvious contradiction between registry and one-line summary; otherwise skip detail.

---

## Rules

- **Do not hallucinate.** If a subsystem is not described in AI-brains files, say **NOT DOCUMENTED in AI-brains** or **UNKNOWN**, not a plausible story.
- **Use UNKNOWN** for registry fields explicitly marked unknown or missing file access.
- **Rely on files, not assumptions.** Prefer quoting paths and titles over paraphrasing deep implementation detail not in docs.
- **Agent Registry / Agent System** — if `system/agent-registry.md` exists, **Self-Describe FULL** and **DEBUG** must include Agent System status (registered agents, draft vs active, alignment with `agent-standard.md` when applicable).
- **Planning Layer and Engineer Protocol** — if `system/planning-layer.md` and `system/engineer-protocol.md` exist, **Self-Describe FULL** and **DEBUG** must include Planning Layer status (purpose, rules, future planner agent if documented) and Engineer Protocol status (how engineer-class agents operate, named engineer agents vs registry when applicable).
- **WebGPT Memory Module** — documented in `system/webgpt-memory-module.md` as specification and process. Do not claim automated tooling exists unless the agent has verified such files in the workspace.
- **Execution layer** items (e.g. agent coordination) in architecture are **descriptions of intent**; separate **roadmap / implementation** must be confirmed from roadmap and repo, not invented.
- If the user names a product (e.g. a check or pipeline) **not** present in AI-brains search results, respond **NOT DOCUMENTED in AI-brains** rather than inventing it.
- Use standard phrases from `system/system-signals.md` in reports, integrity checks, and audits when triggers match.

---

## Key principle

**Triggers request discipline.** The value is not the phrase — it is the **forced pass** through the same canonical sources and output shape every time.
