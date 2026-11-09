# Domain quality bars

Read only the section relevant to the active deliverable. These are starting menus, not automatic requirements. Prefer user-approved references, existing acceptance criteria, and project-native checks.

## Email, sales copy, and marketing

Possible hard gates:

- audience, purpose, offer, facts, links, dates, sender identity, and call to action are correct;
- no invented testimonials, results, proof, guarantees, credentials, scarcity, or personalization;
- required legal, brand, consent, and deliverability constraints are preserved;
- the message is within the requested length and channel format.

Useful comparative bars:

- approved past emails with the desired clarity, warmth, specificity, and pacing;
- a brand voice guide plus a reader-task rubric;
- a user-supplied winning example, judged on principles rather than copied wording.

Inspect the final subject line, preview text, body, links, mobile scanability, and CTA together. A send, schedule, list change, or live campaign launch is a human gate unless explicitly authorized.

## Code and software features

Possible hard gates:

- issue acceptance criteria pass;
- relevant unit, integration, end-to-end, lint, type, build, and security checks pass;
- no unrelated behavior or public interface changes;
- failure paths, data migration, accessibility, and performance meet stated requirements.

Useful comparative bars:

- the current repository's strongest neighboring implementation;
- a reference implementation or protocol specification;
- a latency, reliability, coverage, memory, or bundle-size budget.

Critics inspect code, diffs, running behavior, and test receipts. They do not grade a prose summary. For deployment, production data changes, schema deletion, paid dependencies, secrets, and irreversible operations, follow the user's authorization and any host-required gates.

## Apps and websites

Possible hard gates:

- the target user journey works end to end;
- responsive layouts pass at agreed viewports with no overflow;
- accessibility, keyboard use, contrast, error states, and loading states pass;
- existing analytics, forms, legal copy, and integrations remain functional;
- agreed performance budgets pass.

Useful comparative bars:

- approved category-leading products or design references;
- a supplied design system or reference deck;
- screenshot comparisons plus interaction and accessibility tests.

Inspect real pixels and behavior on representative screen sizes. Judge hierarchy, comprehension, interaction, and system consistency separately, then integrate them.

## Graphics and visual design

Possible hard gates:

- exact dimensions, file format, color mode, transparency, safe area, and export requirements;
- all text is correct and legible at final display size;
- approved brand assets and colors are used correctly;
- no unlicensed or fabricated logos, marks, likenesses, claims, or source assets.

Useful comparative bars:

- approved art direction, mood board, layout references, or brand system;
- objective checks for spacing, alignment, hierarchy, contrast, cropping, and focal clarity;
- side-by-side renders at actual use size.

Critics inspect exported pixels, not the source prompt. Use references for properties and quality, not to reproduce protected work or a living artist's distinctive style.

## Articles, books, scripts, and editorial work

Possible hard gates:

- the approved outline, thesis, audience, scope, length, and factual constraints are fulfilled;
- claims trace to supplied or verified sources;
- required examples, transitions, definitions, and calls to action are present;
- no plagiarism, invented sources, or imitation of a living author's voice.

Useful comparative bars:

- user-approved samples for clarity, information density, structure, warmth, or pacing;
- an editorial rubric covering argument, evidence, organization, repetition, readability, and audience fit;
- continuity and fact-check passes independent from prose editing.

Decompose by argument, opening, section purpose, examples, paragraphs, transitions, and continuity where useful. The final integration critic reads the complete manuscript, not isolated excerpts alone.

## Research, analysis, and strategy

Possible hard gates:

- every material factual claim is traceable to an accessible source;
- source dates, scope, definitions, and uncertainty are represented accurately;
- primary or authoritative sources are used where required;
- facts, inferences, assumptions, and recommendations are labeled separately;
- counterevidence and material limitations are addressed.

Useful comparative bars:

- an approved evidence standard and source hierarchy;
- a decision rubric tied to the user's actual constraints;
- reproducible calculations or query results.

Critics open sources and trace claims. Citation count is not a quality bar by itself. For consequential decisions or actions, follow the applicable requirements for expertise, authorization, and human review.

## Presentations and documents

Possible hard gates:

- required sections, facts, page or slide count, template structure, and audience are satisfied;
- no clipping, overlap, unreadable text, orphaned headings, or broken links;
- charts and citations match the underlying data;
- the exported artifact renders correctly.

Useful comparative bars:

- an approved template or reference deck/document;
- content hierarchy, narrative flow, information density, scanability, and visual consistency rubrics;
- page-by-page or slide-by-slide rendered comparison.

Critics inspect the rendered PDF or images as well as editable source. Finish with a complete-document continuity pass.

## Spreadsheets and data products

Possible hard gates:

- formulas, units, dates, joins, assumptions, and source ranges are correct;
- reconciliation totals and known control totals match;
- errors, blanks, duplicates, outliers, and edge cases are handled as specified;
- formatting, filters, freeze panes, charts, and print/export behavior work.

Useful comparative bars:

- source-of-truth totals and independently computed checks;
- a supplied model, schema, or reporting standard;
- accuracy, usability, auditability, and refresh-performance thresholds.

Critics inspect formulas and outputs, not screenshots alone. Financial posting, filing, money movement, and live-system writes must follow applicable authorization and host-required human gates; prior authorization can satisfy these when the host permits it.

## Automations and operations

Possible hard gates:

- dry run and representative test cases pass;
- idempotency, retries, duplicate prevention, logging, and recovery are proven;
- permissions follow least privilege;
- failure and escalation paths are observable and bounded.

Useful comparative bars:

- an existing manual process with known correct outcomes;
- service-level targets and failure-injection tests;
- a runbook that an independent operator can follow.

Start read-only or reversible. Scheduling, credential changes, live messages, production mutation, and destructive actions require explicit authorization.

## A new domain

When no section fits, derive a bar with four layers:

1. Binary correctness and safety gates.
2. A concrete reference, benchmark, or baseline.
3. Guardrails against gaming or regression.
4. An artifact-level inspection method available to the critic.

Explain why the selected bar predicts the user's real objective. If it does not, replace it before looping.
