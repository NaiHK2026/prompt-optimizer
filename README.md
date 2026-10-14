# Prompt Optimizer

A standalone Codex skill that turns rough requests into clear, executable prompts while preserving
intent, scope, existing authorization, and useful creative freedom.

Use it for coding, design, research, automation, marketing, or a handoff to another AI conversation.
It produces a prompt; it runs the underlying task only when execution is also requested.

## What It Adapts

- **Authority:** advice, read-only review, local changes, or explicitly authorized external actions.
- **Freedom:** exact requirements, guided creative work, or exploratory decisions.
- **Detail:** a brief edit prompt or a fuller cross-system brief, based on complexity.
- **Questions:** ask when missing information matters; use a complete brief directly.
- **Language:** preserve the user's language, with optional multilingual layers when useful.

"Prompt only" removes surrounding commentary; it does not discard requirements. The skill does
not require a fixed project structure, design style, cloud provider, companion skill, or API key.

## Install In Codex

Ask Codex's skill installer to install `https://github.com/NaiHK2026/prompt-optimizer` with the
repository root as the skill directory and `prompt-optimizer` as its name.

For a standard Codex installation, the manual equivalent is:

```sh
git clone https://github.com/NaiHK2026/prompt-optimizer.git ~/.codex/skills/prompt-optimizer
```

If that directory already exists, compare or back it up before replacing anything. Use your
configured skills directory if it differs from the standard location. Start a new Codex session
if the newly installed skill is not yet listed.

Other skill-compatible assistants may use `SKILL.md` and its relative references. The
`agents/openai.yaml` file supplies Codex-specific UI metadata; no cross-client testing is claimed.

## Examples

```text
Use $prompt-optimizer. Write a prompt to review this automation's triggers and duplicate-run
risk. Read-only: do not change or run it.
```

```text
Use $prompt-optimizer. Prompt only: redesign this homepage using the attached reference.
Keep the existing copy and inquiry flow, but you may replace the old layout. Verify desktop
and mobile in the browser. Do not deploy.
```

```text
Use $prompt-optimizer. I want to build a small tool but have not settled on its audience or
scope. Ask me a few useful questions before writing the project prompt.
```

Links, screenshots, and direct fix requests do not by themselves trigger prompt writing. Include
relevant evidence, the desired outcome, and any actual limits; the skill handles the structure.

## Contents

- [SKILL.md](SKILL.md): core decisions and output behavior.
- [Prompt modes](references/prompt-modes.md): optional domain-specific ingredients.
- [Multilingual layering](references/bilingual-layered.md): optional language guidance.
- [Regression cases](references/regression-cases.md): behavioral fixtures for maintainers.
- [Language cases](references/bilingual-layered-evals.md): language-strategy fixtures.

The reference files load only when relevant. Test fixtures are examples, not proof that every
model or environment will behave identically. Test with isolated inputs and inspect actual
responses; prompt writing is not authorization to run the actions described in those inputs.
