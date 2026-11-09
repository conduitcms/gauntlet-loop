---
name: gauntlet-loop
description: "Bounded builder-critic loops against inspectable bars for substantial work. Use when asked to gauntlet, deeply refine, polish, or stress-test; not quick edits."
license: MIT
metadata:
  version: "1.0.0"
---

# Gauntlet Loop

Run a persistent but bounded improvement loop for any inspectable deliverable. Give a lead agent the outcome and a concrete bar, let it choose the route, separate building from judging, inspect the real artifact, fix the largest meaningful gap, and repeat until the work passes or a boundary fires.

This skill is an independent, bounded adaptation of Matt Shumer's Gauntlet Loop for inspectable work across domains. Read `references/source-notes.md` when explaining the method or its provenance.

## When to use

Use when the user explicitly says “Gauntlet Loop,” “run the gauntlet,” “keep improving,” “polish this against these examples,” or asks for rigorous iterative improvement of substantial work such as:

- emails, copy, articles, books, research, and reports;
- code, software, websites, apps, automations, and data work;
- graphics, layouts, presentations, documents, and spreadsheets;
- any artifact whose actual output can be inspected and compared.

Scale the loop to the task. A short email may need one build-review-revise cycle. A product may need separate component loops and an integration wave.

Do not start a heavy loop when one careful pass is clearly cheaper, the output cannot be observed, success cannot be made concrete, or errors would be high-consequence and no reliable verifier or human gate exists. If the user explicitly invokes the skill anyway, run the smallest safe version and state the limitation.

## Non-negotiables

- Inherited system, developer, workspace, safety, privacy, and user instructions outrank this skill.
- The loop never expands authorization. Deploying, publishing, sending, purchasing, deleting, changing accounts or permissions, using secrets, moving money, or making irreversible changes still requires the authority the host normally requires.
- Judge the real artifact: rendered pixels, running software, tests, finished prose, source traces, exported files, or actual tool results. Never accept the builder's summary as proof.
- Obtain a critic verdict separate from the builder's rationale. Prefer a fresh critic; otherwise use the strongest available separation described in `references/platform-adapters.md` and disclose limited independence.
- Use subagents only when the host exposes them and governing instructions permit them. Parallelize only genuinely independent work.
- “Perfect” and “amazing” are directions, not pass conditions. Every run needs observable success criteria and explicit boundaries.
- Preserve existing user work. Avoid unrelated cleanup, broad rewrites, and metric gains that damage the real objective.
- Never fabricate facts, citations, testimonials, credentials, results, metrics, scarcity, or source support to make a score improve.

## Workflow

### 1. Inspect before planning

Read the supplied materials and inspect the current artifact, relevant project instructions, available tools, and existing verification methods. Identify the deliverable, intended audience or user, current state, protected constraints, and actions that require approval.

If the request is well-scoped, proceed without re-asking answered questions. Ask only when a missing choice would materially change the outcome, quality bar, cost, or risk.

### 2. Create the Loop Card

Use `assets/loop-card.md` as the schema. Define:

- **Objective:** the state that must become true, phrased as an outcome rather than an implementation plan.
- **Artifact:** the exact thing the verifier will inspect.
- **Hard gates:** binary requirements that must all pass.
- **Comparative bar:** an approved reference, benchmark, baseline, rubric threshold, or measurable target.
- **Guardrails:** qualities that must not regress while optimizing the main bar.
- **Evidence:** tests, renders, screenshots, citations, exports, logs, diffs, or reader/user checks available to the critic.
- **Scope and permissions:** allowed targets and actions, forbidden actions, and human gates.
- **Boundaries:** time, attempts, compute or money, repeated-failure, risk, and diminishing-return limits.

If the user supplied references, prefer them. If the bar is missing, find or propose an inspectable one that serves the same function. Explain the choice in one sentence. Do not silently choose a benchmark that changes the user's goal or creates material cost.

Use multiple signals when one metric is gameable. A pass requires every hard gate plus the comparative threshold; a strong average cannot hide a failed gate.

For domain-specific bar options, read only the relevant section of `references/domain-bars.md`.

### 3. Capture the baseline

Run the available verifier before changing anything. Save enough evidence to compare later. Record current failures, relevant scores, screenshots, test output, or a concise rubric assessment.

For substantial filesystem work, keep a compact durable ledger using `assets/workbench.md`. Follow the project's scratch-file convention; otherwise use a clearly temporary Gauntlet work area and do not commit it unless asked. In chat-only work, keep the same fields in the conversation.

### 4. Decompose by judgeability

Let the lead choose the smallest important parts that can be improved and judged independently. Map coupling before delegation:

- Give independent components separate owners when useful.
- Keep tightly coupled components under one coherent owner or process them sequentially.
- Do not let builders edit overlapping files or artifact regions concurrently.
- Rank workstreams by expected impact on unmet criteria, not by ease or novelty.

The lead owns the Loop Card, priorities, shared constraints, integration, and final evidence. Builders own scoped improvements. Critics own verdicts only.

### 5. Select the separation pattern

Read `references/platform-adapters.md` and use the strongest available pattern:

1. Separate builder and fresh-context critic agents.
2. Separate sessions or a host-provided review context.
3. Role-separated sequential passes with a sanitized critic packet.
4. Human critic handoff when independent review is required but the environment cannot provide it.

Never call a same-context self-review “independent.” State the limitation and compensate with stronger objective checks.

### 6. Run the component loop

For each active component:

1. Give the builder the objective, scoped target, relevant constraints, current artifact, and latest correction target. Do not prescribe architecture unless the user or project already did.
2. Make one coherent improvement aimed at the highest-impact unmet criterion.
3. Produce or refresh the real artifact.
4. Run deterministic checks first: tests, lint, type checks, validators, source checks, renders, exports, or measurements.
5. Give a critic the original objective, relevant bar, constraints, real artifact, and verifier receipts. In a fresh context, exclude the builder's rationale and conversational history. In a same-context fallback, use the packet to guide the review but disclose that prior context remains visible.
6. When feasible, randomize labels and use a blind A/B comparison against the reference or baseline. The critic must disclose when comparison was not blind.
7. Require the critic report format in `assets/critic-report.md`.
8. If the result fails, return the single largest meaningful gap and a concrete correction target to the builder.
9. Re-run all relevant gates after the change to catch regressions.
10. Record the round, evidence, strategy, verdict, next action, and remaining boundary.

Do not repeat the same failed approach unchanged. After two materially similar failures, diagnose the pattern and choose a different strategy. If no credible new strategy remains, stop under the repeated-failure boundary.

### 7. Run integration waves

After a meaningful group of component changes, and before any final PASS, review the complete artifact. Use a fresh integration critic when available; otherwise use the strongest feasible separation and disclose its limits. The reviewer checks:

- consistency and coherence across improved parts;
- end-to-end behavior and the original objective;
- regressions in hard gates and guardrails;
- seams, duplication, conflicts, and local improvements that hurt the whole.

The integration reviewer may identify conflicts and bounded defects. A builder or lead applies any corrections, then reruns relevant gates and has a critic review the revised whole artifact before the final verdict. This process must not silently redesign the project or reopen settled requirements.

### 8. Stop deliberately

Stop immediately when any condition applies:

- **Success:** every hard gate passes, the comparative threshold is met, and the integration critic finds no blocking gap.
- **Diminishing returns:** two consecutive valid rounds produce no material gain against the bar.
- **Repeated failure:** the same blocker survives multiple genuinely different strategies and no credible next strategy remains.
- **Boundary reached:** time, attempts, tokens, money, tool quota, or other declared budget is exhausted.
- **Human gate:** the next step requires a user decision, permission, credential, or other access that is not already available or authorized, or a confirmation required by the host.
- **Safety or observability failure:** continuing would be unsafe, unauthorized, or impossible to verify.

Do not lower the bar after seeing the result. If the user changes the target, version the Loop Card and record the change.

## Default boundaries

When the user gives no budget, choose a proportional, low-risk local budget and state it before the first change:

- Small artifact: up to 2 critic rounds plus final review.
- Medium artifact: up to 3 rounds per active component and 1 integration wave.
- Large artifact: propose a staged budget and complete the highest-value stage first; do not begin an open-ended high-compute run silently.

Stop earlier on success or diminishing returns. The user may explicitly raise or lower these limits.

## Final response contract

Lead with exactly one status:

- **PASS** — the declared success condition passed with evidence.
- **FAIL** — work was attempted but the declared bar was not met before a non-human stop condition.
- **BLOCKED** — progress requires user input, authority, unavailable access, or an external state change.

Then report only what helps the user verify or continue:

- objective and quality bar;
- artifact or changed files;
- strongest before/after evidence and commands or checks used;
- critic and integration verdicts;
- rounds completed and stop reason;
- remaining material gaps;
- the exact human decision or next action if blocked.

Do not claim “production-ready,” “better,” or “passed” without receipts tied to the Loop Card.
