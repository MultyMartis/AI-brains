# Self Update Rules (Strict)

## Purpose

Ensure **critical system descriptions** (including Self-Describe and related prompts) stay aligned with reality — **only** after **confirmed** important changes, and **never** as silent automatic edits.

This document defines **when** updates are required, **what** is in scope, and **who** decides — not an auto-pipeline.

---

## Scope (critical modules)

Updates to Self-Describe artifacts and peer canon are **governed by these rules** when any of the following change in a **critical** way:

- Main Brain architecture (`system/main-brain-v2-architecture.md` and equivalents)
- Self-Describe System (`system/self-describe-system.md`, `prompts/system/self-describe-full.txt`, `prompts/system/self-describe-short.txt`, `prompts/system/self-describe-command.txt`)
- Project Registry **structure or contract** (`system/project-registry.md`, `system/project-registry-standard.md`)
- Lifecycle rules (`system/ai-lifecycle-log-standard.md`, log format expectations)
- **Agent System** (future) — any first-class module once it exists in AI-brains
- **MetaBOT** — architecture or global integration **as recorded in AI-brains** (registry, lifecycle, linked docs), not every bot tweak

---

## What is a "Critical Change"

An update to Self-Describe (and related prompts) is **REQUIRED** only if **all** of the following apply:

1. A **new** system or module is **added to canon** (e.g. new `system/*.md` that changes how agents navigate the pack; future **Agent System**; **Fly-Check** or similar once documented in AI-brains; any named global capability in index or architecture).
2. **Architecture** changed: layers, roles, control flow, or operating cycle as documented in Main Brain v2.
3. **Core logic** changed: rule precedence, lifecycle obligations, project control rules, SAFE UNKNOWN behavior, Git safety at standard level.
4. A **new global capability** is documented as part of MCA AI.Pack (e.g. memory bridge, automation layer) — not a single-project experiment.

**Confirmed** means: change is **implemented and reflected** in authoritative files (merged intent in repo), not only discussed in chat.

---

## What is NOT critical

**Do not** treat these as triggers to rewrite Self-Describe or full prompts:

- Minor wording or formatting edits that do not change behavior or structure
- Local project-only changes (implementation detail in a project repo) with **no** change to AI-brains standards or registry contract
- Single-agent or single-session tweaks
- Temporary experiments not promoted to `AI-brains/system` or index
- **Routine** lifecycle log entries that only record work done, with **no** change to architecture, registry structure, or Self-Describe contract

---

## Update trigger logic

1. A change occurs in scope above.
2. The change is **confirmed** (present in canon files / registry / standards — not an idea only).
3. A **lifecycle log** entry is created per `system/ai-lifecycle-log-standard.md` (when that standard applies).
4. **Then** the responsible party **must**:

   - Review whether `self-describe-system.md` still matches reality → update **if needed**.
   - Review whether `self-describe-full.txt` / `self-describe-short.txt` / `self-describe-command.txt` still match → update **if needed**.
   - **Notify** the user (or ticket owner):

     `Self-Describe System update recommended`

   - Wait for **manual** execution in Cursor (or equivalent) — see Safety Rule.

---

## Responsibility

| Role | Responsibility |
|------|----------------|
| **Main Brain** (process / owner) | Detect mismatch between triggers, prompts, and canon after critical changes; flag recommendation. |
| **Factory Engineer** (future) | If introduced: enforce that critical merges include Self-Describe review checklist item. Until then: **N/A — manual discipline**. |
| **User** | Final approval on whether and when to edit Self-Describe files. |

---

## Safety rule

**Self-update is NEVER automatic.**

Allowed sequence only:

1. **Recommendation** (explicit message: `Self-Describe System update recommended`).
2. **Manual** edit of the listed files via Cursor (or human), with normal review and lifecycle logging if policy requires.

No script, agent, or hook should overwrite Self-Describe prompts **without** human-triggered execution.

---

## Key principle

**Strict self-update** means **strict gates**: critical change → log → recommend → human edits — not continuous churn.
