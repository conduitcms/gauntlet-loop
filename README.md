# Gauntlet Loop

**An open-source agent skill for turning a first draft into a better, verifiable result.**

Give an agent a goal and a concrete quality bar. It builds the deliverable, tests it, has a critic inspect the actual result, fixes the biggest gap, and repeats within agreed limits.

The skill works across writing, research, software, websites, presentations, and other work that can be inspected. It combines the builder–critic pattern with explicit stopping conditions, evidence, and safeguards against regressions.

## The loop

1. **Set the bar.** Define the objective, the artifact, required checks, and a concrete reference or measurable target.
2. **Inspect the starting point.** Capture a baseline so the result can be compared with it.
3. **Build and verify.** Improve the most important gap and run the available checks.
4. **Critique the real work.** A fresh critic, when the host supports one, inspects the artifact and evidence against the bar.
5. **Revise and repeat.** Address the largest remaining gap, check for regressions, and review the complete result.
6. **Stop deliberately.** Finish when the bar is met, progress stalls, a limit is reached, or a decision or permission is needed.

If separate agents are unavailable, the skill uses the strongest review separation the host supports and says when the review is not independent. A loop can improve work, but it cannot guarantee perfect results or replace qualified human review where needed.

## Install

The repository is an [Agent Skills](https://agentskills.io/specification) folder: `SKILL.md` is at the root, with its supporting references and templates alongside it. You need the whole folder, not only `SKILL.md`.

### Codex

On this repository's GitHub page, select **Code**, select **HTTPS**, and copy the URL. To install for your user account, run this in a macOS or Linux shell and paste the URL when prompted:

```bash
mkdir -p ~/.agents/skills
printf 'Paste the repository HTTPS URL: '
IFS= read -r REPOSITORY_URL
git clone "$REPOSITORY_URL" ~/.agents/skills/gauntlet-loop
```

On Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills" | Out-Null
$RepoUrl = Read-Host "Paste the repository HTTPS URL"
git clone "$RepoUrl" "$HOME\.agents\skills\gauntlet-loop"
```

Alternatively, put the folder in a project's `.agents/skills/gauntlet-loop` directory. See the [Codex skill locations](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills).

### Other hosts

- **ChatGPT:** On eligible accounts, open **Plugins → Skills → Create → Upload from your computer** and follow [OpenAI's skill upload guidance](https://help.openai.com/en/articles/20001066-skills-in-chatgpt). Include the complete skill and its supporting files; availability and accepted upload formats vary.
- **Claude Code:** Place the complete folder at `~/.claude/skills/gauntlet-loop` for personal use, or `.claude/skills/gauntlet-loop` inside a project. See the [Claude Code skills guide](https://code.claude.com/docs/en/skills).
- **OpenClaw:** Place the complete folder at `<workspace>/skills/gauntlet-loop`, or use another [documented skill location](https://docs.openclaw.ai/tools/skills).
- **Other Agent Skills hosts:** Follow the host's installation instructions and keep the folder's internal structure intact. Skill availability, subagents, tools, and invocation syntax vary by host.

These installation paths follow the hosts' documentation; the package has not been tested in every host or configuration.

## Use it

Ask for the skill by name, or use your host's skill picker. In Codex you can explicitly invoke `$gauntlet-loop`; in Claude Code, use `/gauntlet-loop`. For example:

```text
Use the Gauntlet Loop to improve this landing page for course creators.

The bar: the examples I supplied for clarity and visual quality. It must work
on mobile, explain the offer accurately, and have an obvious next step.

Inspect the actual page, use a separate critic if available, and run up to
three review rounds. Show the evidence, remaining gaps, and why you stopped.
```

You can name a reference, a test suite, a measurable threshold, or an explicit rubric as the bar. For a short email, a single review cycle may be enough; for a larger product, the agent can review components separately and then check the whole experience.

## What's included

| Path | Purpose |
| --- | --- |
| [`SKILL.md`](SKILL.md) | Core workflow, boundaries, and reporting rules |
| [`assets/`](assets/) | Loop Card, critic report, and workbench templates |
| [`references/`](references/) | Quality bars, host adapters, and source notes |

The skill is a set of instructions and templates; it does not install software, provide credentials, grant permissions, or run in the background by itself. Actions remain subject to your instructions and the host's controls.

## Credits

This is an independent, cross-domain adaptation of the Gauntlet Loop method. It is not authored or endorsed by the sources below.

- **Matt Shumer** coined and explained the Gauntlet Loop and its lead, builder, and separate critic pattern in [How to Run a Gauntlet Loop](https://somethingbig.ai/gauntlet-loop). See also his [original Claude of Duty prompt](https://github.com/mshumer/Claude-of-Duty/blob/main/prompt.md).
- **Stephen at The Prompt Index** discusses objective, metric, and boundary framing and loop safeguards in [AI Loop Engineering in 2026: How to Build a Gauntlet Loop](https://www.thepromptindex.com/ai-loop-engineering-gauntlet-loop-guide.html).

## License

[MIT](LICENSE) for this repository's adaptation. Linked third-party works remain under their respective terms.
