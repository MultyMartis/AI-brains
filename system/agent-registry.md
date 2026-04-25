# Agent Registry

## Purpose

Central source of truth for all agents in MCA AI.Pack.

## Rules

- Every agent MUST be listed here
- Agents not listed here are considered NON-EXISTENT
- Registry defines real system state
- Must match actual folders and files
- Must be updated on any agent lifecycle change

## Agent Table

| agent_id | name | type | status | owner_system | location | last_update |
|----------|------|------|--------|--------------|----------|-------------|
| MB-FlyCheck-v1 | Fly Check | system-agent | active | Main Brain | system/agents/MB-FlyCheck-v1 | 2026-04-26 |
| MB-SelfDescribeMaintainer-v1 | Self Describe Maintainer | system-agent | planned | Main Brain | UNKNOWN | - |
| MB-AgentRegistryValidator-v1 | Agent Registry Validator | system-agent | planned | Main Brain | UNKNOWN | - |
| MB-FactoryEngineer-v1 | Factory Engineer | system-agent | draft | Main Brain | system/agents/MB-FactoryEngineer-v1 | 2026-04-26 |
| MB-Planner-v1 | Planner | system-agent | draft | Main Brain | system/agents/MB-Planner-v1 | 2026-04-26 |
| MB-AgentBuilder-v1 | Agent Builder | system-agent | draft | Main Brain | system/agents/MB-AgentBuilder-v1 | 2026-04-26 |
| MB-SystemAuditor-v1 | System Auditor | system-agent | planned | Main Brain | UNKNOWN | - |
| MB-Scraper-v1 | Scraper | data-agent | planned | Main Brain | UNKNOWN | - |
| MB-SourceScanner-v1 | Source Scanner | data-agent | planned | Main Brain | UNKNOWN | - |
| MB-WorkChatObserver-v1 | Work Chat Observer | ops-agent | planned | Main Brain | UNKNOWN | - |
| MB-IdeaDesigner-v1 | Idea Designer | personal-agent | planned | Main Brain | UNKNOWN | - |
| MB-PersonalSecretary-v1 | Personal Secretary | personal-agent | planned | Main Brain | UNKNOWN | - |
| MB-ObsidianAgent-v1 | Obsidian Agent | personal-agent | planned | Main Brain | UNKNOWN | - |

---

## Initial Agents

Initial entries are recorded in **Agent Table** above.

---

## Status Rules

planned = exists only in registry  
draft = files created, not tested  
active = usable  
stable = validated  
paused = temporarily stopped  
deprecated = no longer used  

---

## Sync Rule

Agent Registry MUST be consistent with:

- agent-standard.md
- lifecycle-log.md
- actual agent folders
