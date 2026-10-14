# Prompt Mode Reference

Use only the section matching the current task. Combine sections only when the request genuinely crosses domains.

## Contents

- Fast Evidence
- Website And Design
- Code And Debug
- Research And Sources
- SEO, Growth, And Tracking
- Creative, Image, Motion, And 3D
- Workflow And Automation
- Handoff
- Full Brief Skeleton

## Fast Evidence

Use for a simple scoped issue supported by a URL, localhost page, screenshot, or browser comment. Evidence format alone does not make a complex request a Micro task.

Include:

- the supplied evidence;
- the exact area or concern;
- permission to inspect directly;
- the requested authority;
- one compact completion condition.

Reuse supplied context and preserve the selected scope. Ask only about missing information that materially changes the task; otherwise make a reasonable assumption or leave the choice open.

## Website And Design

Use for layout, landing pages, visual polish, unwanted design defaults, responsive behavior, or motion direction.

Include only what applies:

- target reference or locked visual direction;
- what should remain and what should change;
- desktop and mobile expectations;
- content, CTA, tracking hook, and section-ID preservation when relevant;
- visual verification after implementation.

Use guided language for taste. Turn qualities such as "premium" into relevant observable criteria such as hierarchy, image scale, spacing, and CTA clarity, while leaving composition and implementation judgment open. Do not dictate exact components unless the user has fixed them. For a major redesign, state that structural changes are allowed; for a small correction, allow necessary coherent changes without adding an unrelated redesign. A newly approved direction can replace an older design preference within the authorized scope. Cards, dashboards, and other familiar patterns remain valid when they fit the audience and purpose.

When the user wants a question-led opening, use their existing brief and ask only about unresolved goals, materials, or direction. An actionable brief proceeds directly. Include reference research or a design digest only when it resolves a material uncertainty or was requested; neither requires a specific companion skill.

## Code And Debug

Use for implementation, bugs, refactors, build errors, and tests.

Include:

- project path and direct symptom;
- applicable project instructions and relevant documentation when present;
- source-first inspection and the requested edit scope;
- preservation of unrelated changes and use of the project's conventions for generated output;
- the narrowest relevant verification command or behavior;
- changed-files and verification reporting.

Do not add broad exploration or architecture work to a small fix.

## Research And Sources

Use when accuracy depends on external or changing information.

Include:

- research question and decision it supports;
- market, location, date range, or comparison set when known;
- fresh web research and direct source links;
- separation of facts, assumptions, inference, and recommendation;
- confidence or data limitations when useful.

Prefer primary sources for technical, legal, financial, medical, or product facts.

## SEO, Growth, And Tracking

Use for SEO, GEO, Google Ads, analytics, conversions, reporting, and market research.

Include only relevant items:

- site, offer, market, location, audience, and conversion goal;
- data sources and time period;
- metrics or events to inspect;
- prioritized findings and actions;
- assumptions and confidence;
- monitoring cadence or next checkpoint.

Distinguish measurement reliability from campaign optimization and describe only the work requested. For vague outcomes such as "more inquiries", distinguish verifiable behavior (CTA access, form receipt, conversion events) from business impact requiring real performance data; do not invent uplift targets or guarantee results.

## Creative, Image, Motion, And 3D

Use for image generation, editing, moodboards, motion, 3D scenes, and art direction.

Anchor:

- subject and must-preserve identity;
- use case and aspect ratio;
- composition or camera relationship;
- lighting, color, material, and atmosphere;
- reference qualities rather than copied assets;
- a short avoid-list.

Preserve composition and art-direction judgment unless the user provides exact framing. For image editing, identify what must remain unchanged.

## Workflow And Automation

Use for skills, SOPs, automation platforms, agent workflows, and reusable operations.

Include:

- trigger and input;
- system or role ownership;
- step order and data handoff;
- authorized actions, their targets and limits, and any remaining approval boundary;
- failure behavior, duplicate protection, and status fields when relevant;
- completion criteria and a safe test path.

For review-only requests, explicitly prohibit workflow edits or live submissions. For implementation, distinguish dummy tests from production writes.

Carry already approved actions into the prompt without asking for the same permission again. Keep new targets or unapproved external effects outside that authorization.

## Handoff

Use for another AI conversation or later continuation.

Include:

- objective and project path;
- current state and relevant changed files;
- files to read first;
- completed work and do-not-revisit items;
- next useful action and existing authorization with its target and limits;
- verification already completed and next narrow check.

Use supplied continuity facts first; identify missing facts only when they affect the next task. No companion handoff skill is required. Distinguish reported verification from independently verified evidence. Keep a small conversational continuation prompt compact.

## Full Brief Skeleton

Use only when a compact prompt would create material ambiguity.

```text
Task:
[One clear action and deliverable]

Context and inputs:
[Only context and evidence that affect execution]

Scope and authority:
[Authority, source of truth, hard constraints, external actions]

Direction and judgment:
[Target qualities and choices the AI may improve]

Deliverable:
[Expected artifact or response]

Verification and success criteria:
[Smallest meaningful proof]
```

Adapt labels to the user's language and omit empty sections. Add questions only when the answer would change the route, authority, or deliverable.
