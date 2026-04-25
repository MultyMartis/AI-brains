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
