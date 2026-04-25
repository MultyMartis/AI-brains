# System Signals

## Purpose

Standard, copy-paste phrases for **state** and **risk** in Self-Describe reports, audits, and system checks. Use exact markers so humans and tools can scan output.

---

## SIGNAL: SYSTEM MAY BE OUTDATED

**Trigger:**

- `logs/lifecycle-log.md` documents changes **after** or **not aligned with** what Self-Describe prompts / `self-describe-system.md` still describe; **or**
- `project-registry.md` lists systems/phases that the fixed prompt text does not acknowledge; **or**
- registry vs lifecycle contradict each other.

**Output (exact first line):**

```text
⚠ SYSTEM MAY BE OUTDATED
```

**Then list:**

- What changed (from lifecycle/registry only).
- What is not reflected in Self-Describe (name files or gaps).

**Action:**

- Run update of Self-Describe System (manual in Cursor, per `system/self-update-rules.md`).

---

## SIGNAL: UNKNOWN STATE

**Trigger:**

- Required data missing, unreadable paths, or broken links between registry and log files.

**Output (exact marker when appropriate):**

```text
UNKNOWN
```

**Action:**

- Restore file access or fix paths; re-run Self-Describe; do not invent values.

---

## SIGNAL: INCONSISTENCY DETECTED

**Trigger:**

- `project-registry.md` vs `lifecycle-log.md` (or vs on-disk project paths) **conflict** on status, phase, or existence of a project.

**Output (exact first line):**

```text
⚠ INCONSISTENCY DETECTED
```

**Then list:**

- Field A vs Field B (cite which file each comes from).

**Action:**

- Resolve in registry or lifecycle per `system/ai-lifecycle-log-standard.md` / registry standard; then update Self-Describe if critical.

---

## Rule

These signals **must** appear in output when their triggers are met:

- Self-Describe reports (FULL / DEBUG; SHORT when obvious)
- Audits and system checks that compare registry, logs, and canon

Do not emit a signal **without** a trigger; do not soften wording (keeps grep/search consistent).
