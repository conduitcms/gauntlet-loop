# Platform adapters

Use the strongest separation and observation the active host genuinely supports. Host rules and user authorization always win.

## Codex

- Invoke explicitly with `$gauntlet-loop` when available; matching requests may also activate it implicitly.
- Inspect workspace instructions before changing files.
- Use separate agents for builder and critic only when multi-agent tools are available and governing instructions permit delegation.
- Give critics bounded packets: objective, bar, relevant constraints, artifact paths, and verifier receipts. Do not forward builder rationale.
- Use isolated worktrees or disjoint ownership for independent code changes when supported. In a shared filesystem, never allow concurrent edits to the same file or coupled surface.
- Prefer deterministic local verifiers before model judgment. Render visual artifacts and inspect the render.
- If agents are unavailable, use a host review context or sequential role separation and disclose that the review was not fully independent.

## OpenClaw

- Invoke with `$gauntlet-loop` or the skill's `/gauntlet-loop` command when available, or by a clearly matching request. Available commands vary by channel and configuration.
- Use `sessions_spawn` or the host's current subagent mechanism only when available, allowed, and useful. Use separate sessions for fresh critics.
- Treat shared-workspace concurrency as a collision risk. Assign disjoint files or run coupled work sequentially.
- Keep durable state in the project or workspace rather than relying on session history.
- Skill availability depends on snapshots, refresh settings, and source type. File-backed changes can refresh in an existing session; managed library selections can pin revisions. Follow the current OpenClaw refresh instructions if a change is not visible.
- A skill does not grant message, browser, shell, secret, deployment, or spending authority. Keep those gates intact.

## ChatGPT Work

- Invoke a personal or workspace skill with `@gauntlet-loop` when it is installed.
- Use connected tools to inspect the real artifact when available. If only chat output exists, the finished draft itself is the artifact.
- If workspace agents or separate chats are available, use a fresh one as critic with a sanitized packet.
- If no fresh context is available, run role-separated sequential passes, strengthen objective checks, and label independence as limited.
- Do not imply a background or autonomous loop is continuing when the product cannot actually continue working.
- Installation, invocation, and available tools depend on the ChatGPT surface and account; follow the current product instructions.

## Plain chat or a host without tools

- Build a Loop Card in the conversation.
- Draft the artifact, run a clearly labeled critic pass, revise the largest gap, and repeat within a small stated budget.
- Ask the user for the artifact, reference, or verification result when the host cannot observe it.
- Never claim tool execution, independent review, or continued background work that did not occur.

## Choosing a separation level

Use this order:

1. Fresh critic agent with direct artifact access.
2. Fresh session or host-provided review model with direct artifact access.
3. Same model in a new context with only the sanitized critic packet.
4. Same context, role-separated pass plus deterministic checks.
5. Human review handoff.

Record the chosen level in every critic report.
