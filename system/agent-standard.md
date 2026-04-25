# Agent Standard

## Purpose

Define what an agent is inside MCA AI.Pack / Main Brain v2.

## Agent Definition

An agent is a controlled AI module with:

- clear purpose
- owner system
- input/output contract
- allowed actions
- forbidden actions
- dependencies
- status
- lifecycle log connection

## Agent Types

Define these initial types:

### 1. system-agent

For Main Brain / infrastructure tasks.

Examples:

- Fly-Check
- Self-Describe maintenance
- Registry validation

### 2. runtime-agent

For working with external workflows and automation runtime.

Examples:

- n8n workflow helper
- MetaBOT workflow agent

### 3. data-agent

For collecting, parsing, scraping, scanning, and structuring information.

Examples:

- scraper
- source scanner
- YouTube scanner

### 4. ops-agent

For work chat observation, task extraction, reminders, and project operations.

### 5. personal-agent

For personal assistant logic.

Examples:

- Personal Secretary
- Idea Designer
- Obsidian Agent

## Required Agent Files

Each agent MUST have:

- README.md
- agent-card.md
- workflow.md
- changelog.md

Optional:

- prompts/
- schemas/
- examples/
- tests/
- runtime/

## Agent Card Required Fields

Define required fields:

- agent_id
- agent_name
- standard_name
- agent_type
- owner_system
- status
- purpose
- scope
- inputs
- outputs
- allowed_actions
- forbidden_actions
- dependencies
- related_projects
- lifecycle_log
- registry_status
- last_reviewed

**standard_name**

- maps agent to industry-equivalent role
- required for all system agents

## Agent Statuses

Define:

- planned
- draft
- active
- stable
- paused
- deprecated

## Agent Lifecycle

Define lifecycle:

1. idea
2. design
3. draft
4. validation
5. active
6. stable
7. paused / deprecated

## Safety Rules

Strict rules:

- Agents must not self-create or self-modify without user-approved Cursor task.
- Agents must not bypass Main Brain.
- Agents must be registered before considered active.
- Agents must use UNKNOWN for missing facts.
- Runtime agents must not touch live systems without explicit user instruction.
- System agents may recommend updates but must not auto-update files.

## Registry Requirement

Every agent must be listed in:

system/agent-registry.md

Agents not listed in agent-registry.md are considered NON-EXISTENT in the system.

Agent status must match:

- agent-registry.md
- lifecycle-log.md
- actual agent files/folders

## Relationship to Existing Systems

Explain:

- Main Brain controls standards and registry.
- Factory Engineer will design and evolve agents.
- Cursor executes file changes.
- User approves critical changes.
- MetaBOT bots may become runtime-agents if registered.

## Active Agents

- MB-FlyCheck-v1

## Draft Agents

- MB-FactoryEngineer-v1
- MB-Planner-v1

## Initial Planned Agents

Note:

MB-FlyCheck-v1 has already been created, validated, and activated in system/agent-registry.md.
MB-FactoryEngineer-v1 has already been created as a draft agent and registered in system/agent-registry.md.
MB-Planner-v1 has already been created as a draft agent and registered in system/agent-registry.md.
The remaining agents in this section are planned until their folders and agent cards are created.

List planned agents:

- MB-SelfDescribeMaintainer-v1
- MB-AgentRegistryValidator-v1
- MB-AgentBuilder-v1
- MB-SystemAuditor-v1
- MB-Scraper-v1
- MB-SourceScanner-v1
- MB-WorkChatObserver-v1
- MB-IdeaDesigner-v1
- MB-PersonalSecretary-v1
- MB-ObsidianAgent-v1
