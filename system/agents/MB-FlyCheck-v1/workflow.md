# FlyCheck Workflow

## Steps

1. Load:

- project-registry
- lifecycle-log
- agent-registry

2. Check:

### A. File existence

- critical system files present

### B. Registry consistency

- agents in registry vs actual agents

### C. Lifecycle consistency

- lifecycle vs registry mismatch

### D. System signals

- detect outdated state

### E. Agent consistency

- every agent in `agent-registry` must have a corresponding folder under `system/agents/` when registry status is not `planned`

### F. Registry vs lifecycle sync

- each agent’s `last_update` (or equivalent) in `agent-registry` must exist as a corresponding note or entry in `lifecycle-log` (no registry updates without lifecycle trail)

### G. Project registry sync

- `last_checked` in `project-registry` must not lag behind the latest meaningful change reflected in `lifecycle-log` (staleness = WARNING or BROKEN per severity rules)

3. Output:

FLYCHECK REPORT

Status:

- OK
- WARNING
- BROKEN

Sections:

- Missing files
- Inconsistencies
- Risks
- Recommended actions
