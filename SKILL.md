---
name: prompt-optimizer
description: Write or improve a prompt when the user requests a reusable prompt, task instructions, or a prompt for another conversation. Adapt coding, design, research, automation, growth, and handoff requests while preserving intent and creative freedom. A link, screenshot, browser comment, or direct fix request alone does not trigger prompt writing. Execute the underlying task only when the user also requests execution.
---

# Prompt Optimizer

## Purpose

Convert the user's actual intent into a clear, appropriately detailed prompt that another AI can execute reliably. Completeness and useful freedom matter more than minimum length.

Optimize for fidelity, authority, evidence, scope, useful freedom, output, and verification. Do not turn a simple request into a project specification. Do not execute the underlying task unless the user explicitly requests both optimization and execution.

## Operating Model

Judge every request on two independent axes before writing.

### Authority

- `Advise`: analyze, compare, recommend, or plan without changing state.
- `Review`: inspect evidence or files and report findings without modifying them.
- `Modify`: edit files or configuration within the stated scope and verify the result.
- `External action`: deploy, publish, send, submit, write to SaaS, change production data, or perform another side effect. State the authorized action, target, limits, and any remaining approval boundary.

Do not silently promote advice or review into modification. Do not silently promote modification into an external action.

Carry forward valid explicit authorization from the conversation, including its target and limits. Do not add another confirmation for the same approved scope; leave unapproved consequential actions outside it. Approval to write a prompt alone does not authorize executing its underlying task.

### Freedom

- `Exact`: use when correctness, safety, data flow, deployment, tracking, or a precise reference must not drift.
- `Guided`: use for UI, copy, image, motion, 3D, brand, and other taste-sensitive work. Lock the target and non-negotiables while preserving implementation judgment.
- `Exploratory`: use for strategy, workflow design, tool choice, early product thinking, or uncertain direction. Request options, tradeoffs, assumptions, and one recommendation.

Authority and freedom may differ. A design implementation can be `Modify + Guided`; an automation audit can be `Review + Exact`.

## Intent Capsule

Extract these silently. Include only the parts that improve the final prompt.

- Action: what the next AI should do.
- Deliverable: what should exist at the end.
- Evidence: URLs, screenshots, browser comments, files, data, or prior decisions.
- Source of truth: the file, reference, live page, or data that outranks assumptions.
- Authority: advise, review, modify, or external action.
- Hard constraints: safety, privacy, scope, exact references, and user-stated non-negotiables.
- Flexible direction: taste, structure, implementation choice, or ideas the AI may improve.
- Verification: the narrowest useful proof of completion.
- Open decisions: only questions that would materially change the result.

Ask up to three focused questions when missing information would materially change the objective, audience, visual direction, deliverable, or authority and cannot reasonably be inferred. Respect a requested question-led opening and whether the questions belong here or in the prompt for the next AI. Reuse supplied answers; a complete brief proceeds directly. Wait for necessary answers before dependent work; otherwise preserve open choices or state a reasonable assumption.

Translate vague goals into observable success criteria tied to the user's context. For example, visual quality can involve hierarchy, image scale, and readable composition; inquiry improvement can involve CTA clarity and verified form receipt. Use relevant criteria without inventing numerical targets, test results, or a fixed design recipe.

## Workflow

1. Restate the real objective internally in one sentence.
2. Set authority and freedom.
3. Identify the source of truth and available evidence.
4. Separate hard constraints from flexible preferences.
5. Choose prompt detail and language strategy according to task complexity and the user's requested output.
6. Add a specialist skill route only when it materially improves execution.
7. Write the prompt in the user's language and preferred tone.
8. Run the anti-bureaucracy and quality checks before returning it.

## Prompt Budget

- `Micro`: one direct paragraph or roughly 4-10 lines. Use for a simple scoped request, such as an exact copy change or small UI correction. A URL, screenshot, or one-file target alone does not determine complexity.
- `Compact`: a short task statement plus only the context, constraints, output, and verification that matter. Use for most coding, design, research, growth, and automation work.
- `Full`: a structured brief for cross-system work, multiple deliverables, fragile data flows, or major ambiguity. Do not use it merely because many details are available.

When the user asks for "prompt only" or a prompt for another conversation, return only the paste-ready prompt. This removes surrounding explanation, not task-critical detail. Treat "fast" as a preference for directness, not permission to omit requirements; honor an explicitly requested length. If essential information is missing, ask only the necessary question. Do not show the selected mode by default.

## Optional Language Strategy

Preserve the user's language by default. `bilingual_layered` is an optional strategy for assigning
different languages to technical instructions, business context, or audience-facing copy.
Enable it when requested or when the supplied multilingual context clearly benefits from it.
Use the user's chosen languages; do not assume a preferred country, dialect, or language pair.

Do not enable it for a Micro prompt, simple translation, single-language creative writing, an
explicit one-language request, or a target system that accepts only one language. Never duplicate
the full prompt as parallel translations.

When enabled or materially useful, read
[references/bilingual-layered.md](references/bilingual-layered.md). Use its defaults unless the
user provides settings. Do not display the strategy or language rationale unless requested.

## Optional Specialist Support

This skill works on its own. If an available specialist skill adds useful domain knowledge, name
it with a clear role. Do not assume other skills, plugins, integrations, or accounts are installed.
Do not execute their workflows merely to write a prompt. Avoid overlapping lead roles and
mandatory chains of intake, design review, implementation, and handoff.

For an actionable brief, write the prompt directly. For a handoff, include the continuity facts
already supplied and identify only the facts that still need gathering. Reference research or a
design digest belongs in the prompt only when it resolves uncertainty or the user requests it.

## Evidence Handling

- For a URL or localhost link, ask the next AI to inspect it using available access. If it cannot reach the resource, report that limitation and request only the missing evidence; do not imply remote access to the user's localhost.
- For a screenshot or browser comment, identify it as visual evidence and preserve the user's selected scope.
- For a local path, tell the next AI which project or file owns the task; do not invent unread files.
- For current or high-stakes facts, require fresh sources and separate facts, assumptions, and recommendations.
- For existing projects, use available project instructions (such as `AGENTS.md`) and relevant documentation for context. Do not require a particular documentation layout or create missing workflow files just to write a prompt. Within system, safety, and permission boundaries, newer explicit user instructions can update older project preferences or an approved design direction. Preserve requirements still applicable to the task; clarify genuine unresolved conflicts rather than reinstating an obsolete preference.

Do not ask the user to repeat evidence already provided.

## Constraint Language

Use hard language only for true boundaries: `must`, `do not`, exact paths, external side effects, safety, privacy, required verification, and fixed deliverables.

Use directional language for judgment: `aim for`, `prefer`, `use as direction`, `preserve room for better local decisions`, and `avoid unless justified`.

For creative work, lock identity, purpose, mood, reference qualities, and avoid-list without prescribing every component. For implementation, data flow, tracking, deployment, or automation, make ownership and verification explicit.

## Mode References

Read [references/regression-cases.md](references/regression-cases.md) only when evaluating or modifying this skill. These are behavioral test cases, not a template or a checklist to load for ordinary prompt requests.

Read [references/prompt-modes.md](references/prompt-modes.md) only when a task needs domain-specific prompt ingredients or the full brief skeleton. Do not load it for an obvious Micro prompt.

Read [references/bilingual-layered-evals.md](references/bilingual-layered-evals.md) only when
validating or changing the bilingual strategy, not during normal prompt optimization.

## Anti-Bureaucracy Pass

Before returning the prompt:

- remove headings with no useful content;
- remove rules already covered by the named skill or project instructions;
- merge repeated negative constraints;
- remove background that does not affect execution;
- avoid invented requirements, technologies, files, metrics, and approval gates;
- keep open decisions open when the next AI can make a better local choice;
- prefer one clear success condition over a ceremonial checklist.

## Output

Default to the optimized prompt only when the user's intent is clear. Add a brief explanation only when a material assumption, route, or risk needs it. Ask necessary questions in the user's language; do not require fixed section labels.

Match the user's language. Preserve their terminology and level of directness instead of rewriting their voice into generic corporate language.

## Quality Check

Confirm that the prompt:

- preserves the user's real objective and supplied evidence;
- carries the requested authority and existing approvals without expanding them;
- distinguishes hard constraints from creative latitude;
- specifies a useful deliverable and proportionate verification;
- includes enough detail to execute the task without unnecessary structure;
- routes specialist work without duplicating another skill;
- contains no invented certainty or unnecessary ceremony.
