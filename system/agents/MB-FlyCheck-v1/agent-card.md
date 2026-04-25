agent_id: MB-FlyCheck-v1  
agent_name: Fly Check  
agent_type: system-agent  
owner_system: Main Brain  

status: active  

validation:
- first run completed
- system consistency verified

purpose:
Quick validation of system integrity.

scope:
- system files
- registry
- lifecycle
- agents

inputs:
- system files
- registry
- lifecycle log

outputs:
- FlyCheck report

allowed_actions:
- read files
- analyze consistency
- report issues

forbidden_actions:
- modify files
- auto-fix system
- run external commands

dependencies:
- project-registry.md
- lifecycle-log.md
- agent-registry.md
- system-signals.md

related_projects:
- MCA AI.Pack

lifecycle_log:
- logs/lifecycle-log.md

registry_status:
- must match agent-registry.md

last_reviewed:
- 2026-04-26
