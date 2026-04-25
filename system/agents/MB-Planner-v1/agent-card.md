agent_id: MB-Planner-v1  
agent_name: Planner  
standard_name: Planner Agent  
agent_type: system-agent  
owner_system: Main Brain  

status: draft  

purpose:
Decompose tasks and prepare execution plans.

scope:
- task decomposition
- step generation
- agent assignment
- risk detection

inputs:
- task description
- system state
- agent registry
- planning-layer.md

outputs:
- task breakdown
- execution steps
- assigned agents
- risks
- next actions

allowed_actions:
- read system
- analyze tasks
- generate plans

forbidden_actions:
- execute tasks
- modify files
- call tools directly

dependencies:
- agent-registry.md
- planning-layer.md
- project-registry.md
- lifecycle-log.md

related_projects:
- MCA AI.Pack

lifecycle_log:
- logs/lifecycle-log.md

registry_status:
- must match agent-registry.md

last_reviewed:
- -
