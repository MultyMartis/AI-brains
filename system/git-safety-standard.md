# Git Safety Standard

## Purpose

Git protects MCA AI.Pack from losing working states.

It must be used as a safety layer, not as manual bureaucracy.

## Core rule

Commit after every completed logical step.

A logical step is:
- system rule update
- roadmap update
- new project scaffold
- workflow tracker update
- prompt pack update
- working code block
- completed wiring task
- completed QA pass

## Commit timing

Commit when:
- files are stable
- task report is complete
- no known broken state exists unless commit explicitly marks WIP

## Commit message format

Use:

type(scope): short action

Examples:

docs(ai-brains): add lifecycle log standard
docs(gulp-starter): align workflow tracker
feat(frontend): add hero section skeleton
fix(gulp): correct style entry docs
chore(system): update project registry

## Push rule

Push after:
- important system changes
- end of work session
- before switching to another major project
- before risky refactor
- after stable milestone

## Local Git rule

Every active project should be a Git repository.

Main Brain should also be versioned if practical.

## Forbidden

Do not commit:
- secrets
- passwords
- API keys
- node_modules
- dist unless explicitly required
- temporary exports
- local caches

## Agent responsibility

Before major changes, agent must report:
- current Git status if available
- whether the task should be committed after completion
- recommended commit message

After changes, agent must report:
- changed files
- whether commit is recommended
- suggested commit message
- whether push is recommended
