---
name: operational-agent-judgment
description: Use this skill whenever the user asks whether Analog should create a new agent, skill, repo, hosted API, automation, product AI surface, memory layer, or operating function. Also use it when planning any new operational capability, deciding what existing agent or skill should own work, or preventing duplicate AI infrastructure.
---

# Operational Agent Judgment

Use this skill to route new Analog operating work to the lightest durable home.

The goal is to avoid overbuilding while still letting the company scale into acute use cases.

## First Question

Start by answering:

```text
What are we trying to accomplish?
```

Then classify the work:

- knowledge
- repeatable workflow
- repo-specific code work
- product runtime feature
- API or integration
- recurring automation
- new operating function

## Required Checks

Before recommending a new skill, agent, repo, service, or automation, check:

1. Does existing Analog Brain context already answer this?
2. Does an existing skill already cover this workflow?
3. Does an existing durable agent own this domain?
4. Does an existing repo already own the implementation?
5. Does the work need private memory, product data, external APIs, secrets, scheduled execution, or human approval?
6. Who owns the result after the first pass?
7. What artifact should exist when the work is done?

## Default Recommendation Order

Prefer the lightest useful option:

1. Use existing docs or context.
2. Use an existing skill.
3. Create or improve a shared skill.
4. Add a page or manifest to `analog-brain`.
5. Add `AGENTS.md` to an existing repo.
6. Create a hosted service or API.
7. Create a new GitHub repo only when ownership, secrets, deployment, data boundaries, or recurring execution justify it.

## Recommendation Labels

Use exactly one of these labels:

- `Use Existing`
- `Create Skill`
- `Extend Agent`
- `Create Runtime Service`
- `Create Repo`

## Output Format

Return a concise routing memo:

```text
Recommendation: [Use Existing | Create Skill | Extend Agent | Create Runtime Service | Create Repo]

Outcome:
[What Analog is trying to accomplish.]

Why:
[One to three concrete reasons.]

Use:
[Existing doc, skill, agent, repo, service, or proposed new asset.]

Memory and data:
[What context is allowed, what stays canonical, and what is sensitive.]

Human approval:
[What needs approval before external action, spend, publishing, repo creation, product mutation, or data sharing.]

Next steps:
[Three or fewer actions.]
```

## New Repo Test

Recommend a new repo only when at least two are true:

- separate deployment
- separate secrets
- separate production permissions
- separate owner or team
- separate release cadence
- separate data boundary
- recurring autonomous execution
- external API surface
- dependency stack that does not belong in an existing repo

One strong reason is enough when it involves security, permissions, or production isolation.

## New Skill Test

Recommend a new skill when:

- the workflow is repeatable
- a current skill does not cover it cleanly
- the output can be standardized
- it does not require private runtime data, secrets, or scheduled execution
- one or more durable agents would reuse it

Improve an existing skill when the new workflow is a variant of an existing one.

## Agent Extension Test

Extend an existing agent when:

- the domain owner is already clear
- the work needs memory or repeated judgment
- a skill alone is too procedural
- the agent can keep using existing docs, repos, and tools

Create a new agent manifest only when an existing agent would become unclear, unsafe, or overloaded.

