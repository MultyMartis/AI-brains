# Project Registry Standard

## Purpose

The Project Registry is the central list of all MCA AI.Pack projects.

It prevents project loss, duplication, and context confusion.

## Registry location

D:\AI\AI-brains\system\project-registry.md

## Required project record

Each project must be registered as:

## Project name

- path:
- type:
- status:
- owner:
- git_repo:
- current_phase:
- workflow_tracker:
- lifecycle_log:
- last_checked:
- next_action:

## Project types

Allowed types:
- main-brain
- frontend-starter
- frontend-project
- wordpress-project
- opencart-project
- metabot
- automation
- experiment
- archive

## Status values

Allowed statuses:
- active
- paused
- planned
- archived
- experimental

## Rules

- Every project under D:\AI\Projects must be registered.
- Every active project must have a workflow tracker.
- Every active project should have a lifecycle log.
- If project state is UNKNOWN, mark it as UNKNOWN.
- Do not guess missing Git repo URLs.
