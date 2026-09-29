---
title: "simpleharness: Operating Harness for AI Coding Agents"
order: 6
context: "Personal project · Claude Code plugin"
period: "Apr 2026"
summary: "Designed a working method for AI coding agents and packaged it as a Claude Code plugin: one agent builds, a separate agent reviews, and nothing counts as done without test evidence."
description: "Designed a working method for AI coding agents and packaged it as a Claude Code plugin: one agent builds, a separate agent reviews, and nothing counts as done without test evidence."
role:
  - "Built the spec around my own workflow, delegating implementation but owning design and approvals"
  - "Added an XY-problem check that confirms the goal before acting on the stated fix"
  - "Scaled process to risk, self-checking small fixes and sending risky work to independent review"
  - "Countered unproven “done” claims with evidence gates and fading rules with three session hooks"
  - 'Tested it with 46 behavioral cases, then ran the whole <a href="/projects/billing-app/">billing app</a> build on it'
links:
  - label: "GitHub"
    url: "https://github.com/kennethghkim/simpleharness"
---

## How a Task Flows

```mermaid
flowchart LR
    user["<b>User</b><br/>goal · pipeline<br/>I/O specs"]
    orch["<b>Main orchestrator</b><br/>checks the intent<br/>plans · dispatches"]
    author["<b>Author agent</b><br/>one scoped task<br/>tests first"]
    reviewer["<b>Reviewer agent</b><br/>independent, read-only<br/>APPROVE / REVISE"]
    user --> orch --> author --> reviewer
    reviewer -- "REVISE" --> author
    reviewer -- "result + evidence" --> user
    user -- "more changes" --> orch
```

## Intent Before Action

Inspired by the XY problem: people often ask AI for the fix they have in mind (Y) instead of the goal behind it (X).

- **Classify first:** Every turn opens with one line of detected intent (research, answer only, implement, or reconcile); an answer-only request never turns into code changes.
- **Context, then questions:** When the user points at files or past projects, the agent reads them first, then asks only the questions that pin down the goal.
- **Decisions as options:** Design questions come as short prose with A/B/C options and a recommendation, so one line answers them.

## Quality Gates

- **Evidence before “done”:** Run the command that proves the result, then report; the reviewer checks the actual changes.
- **Behavior preservation:** Save a baseline before a refactor and explain every difference after it.
- **Circuit breaker:** After three failed fixes, stop and rethink the approach.

## What Is Inside

| Part | What it does |
|---|---|
| Operating protocol | Always-on rules: delegate production code, verify before claiming done, and record the user's approval before any commit or push |
| 4 agents | **author** implements one scoped change; **reviewer** gives an independent, read-only verdict; **explorer** maps a codebase without editing; **researcher** gathers external evidence pinned to specific commits |
| 12 skills | On-demand procedures, such as brainstorming → plan document → step-by-step execution, author/reviewer review rounds, systematic debugging, and session handoff |
| 3 hooks | At session start, inject the protocol. On every prompt, add a short reminder and point to the right skill (English and Korean keywords). At stop, block once if a written plan has stalled |

Credits: some skills adapt ideas from [superpowers](https://github.com/obra/superpowers) (MIT) and [oh-my-openagent](https://github.com/code-yeongyu/oh-my-openagent); `ast-grep` and `insane-search` are vendored from [code-yeongyu/ast-grep-skill](https://github.com/code-yeongyu/ast-grep-skill) and [fivetaku/insane-search](https://github.com/fivetaku/insane-search) (MIT, licenses included).
{: .project-note}
