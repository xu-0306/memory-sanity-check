---
name: memory-sanity-check
description: Use when prior context could over-anchor reasoning: saved memories, notes, retrieved documents, RAG/context snippets, issue or PR history, chat transcripts, experiment logs, design docs, handoff docs, plans, runbooks, incident reports, meeting notes, or previous conclusions. Apply before choosing a consequential direction, architecture, debugging strategy, validation plan, product decision, research path, implementation approach, or recommendation. Prevent stale-context anchoring, path dependence, over-trusting old "best" claims, and missing simpler or non-obvious alternatives.
---

# Memory Sanity Check

Use this skill to make prior context useful without letting it become a cage. Treat any retrieved or remembered context as an evidence bundle, not as a route to follow.

## Core Rule

Before committing to a direction from prior context, separate:

- `Observed facts`: raw measurements, commands, logs, outputs, user reports, files, data, decisions actually made, timestamps.
- `Interpretations`: what someone believed the facts meant.
- `Recommendations`: what someone suggested doing next.
- `Constraints`: requirements that were true then, and may or may not still be true.

Reuse observed facts cautiously. Recheck interpretations, recommendations, and constraints against the current task.

## Anti-Anchoring Checklist

Run this checklist after loading prior context and before recommending or implementing a consequential path:

1. State the current objective.
   Define what "good" means now: correctness, user-visible quality, official metric, local test score, latency, cost, safety, reliability, maintainability, delivery speed, or another target.

2. Scope old claims.
   Rewrite claims like "X is best" as "X was best for objective A, under data B, constraints C, validation D, at time E."

3. Check current source of truth.
   Inspect the current artifact that actually matters: code, data, tests, logs, docs, live behavior, user-reported result, benchmark, deployment state, policy, or spec. Do not let prior context override current evidence.

4. Compare validation to reality.
   Ask whether the old measurement matched the real target environment. Watch for proxy metrics, synthetic tests, stale datasets, partial user flows, local-only assumptions, or changed constraints.

5. List simple baselines.
   Identify the simplest viable approaches before adding complexity. Examples: existing implementation, manual workflow, rule-based method, naive heuristic, direct formulation of the task, small model, minimal patch, or no-code/process fix.

6. Look for excluded strong signals.
   Ask whether prior work excluded useful information because it was messy, inelegant, politically uncomfortable, leakage-prone, out of scope, too simple, or inconsistent with the favored approach.

7. Generate independent alternatives.
   List at least two plausible paths not suggested by the loaded context. If there are none, explain why.

8. Label confidence.
   Mark conclusions as `verified now`, `from prior context`, or `inference`. Prefer next actions that cheaply reduce uncertainty.

## Required Output Pattern

When this skill changes the answer, include a compact sanity-check summary before the recommendation or plan:

```text
Context sanity check:
- Current objective: ...
- Prior-context claims reused: ...
- Current evidence checked: ...
- Simple baselines/alternatives: ...
- Main anchoring risk: ...
```

For small tasks, compress this to one paragraph. For implementation work, do the check internally and mention only decisive implications.

## Red Flags

Pause and re-evaluate when:

- Prior context contains many attempts but no comparison to the simplest viable approach.
- A claim says "best", "correct", "decided", or "blocked" without objective, scope, date, and validation method.
- A clean or elegant protocol performs worse on the user's real objective.
- Work keeps adding architecture, abstraction, process, or tooling without measuring a direct baseline.
- Prior context disagrees with current files, data, tests, user reports, docs, or live behavior.
- Validation optimizes what is easy to measure rather than what matters.
- The loaded context all points in one direction and no one has articulated credible alternatives.

## Context Hygiene

Do not load every historical source by default. Prefer:

- Read current/high-priority summaries first.
- Read old or archived sources only when needed for a specific question.
- Treat archives and old discussions as provenance, not active guidance.
- If stale context is causing repeated mistakes, suggest superseding, archiving, or annotating it.
