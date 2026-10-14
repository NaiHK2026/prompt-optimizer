# Prompt Regression Cases

Use when changing or evaluating this skill, not during normal prompt writing.
Evaluate intent and observable behavior, not exact wording or number of headings.

## Evaluation Method

Give an evaluator the current skill and one input without its expected outcome. Capture the
actual response before assessing it. For multi-turn cases, send the follow-up only after the
first response; do not expose future answers in advance. Fixture paths, URLs, and permissions
are synthetic: they do not authorize real file changes, account access, or external actions.

Record PASS / FAIL / NOT RUN with a concrete reason. Check intent, authority, evidence honesty,
creative freedom, and proportionate detail. A static file check is not a behavioral test.
A shorter prompt is not better if it omits requirements. No model-quality score is implied.

## Cases

### 1. Exact Copy Change
Input: "Prompt only: change the hero button from 'Contact us' to 'Book a free consultation'. Change nothing else."
Expected: Brief prompt, exact replacement, selected scope, and relevant display check.
Fail: Edits files now, adds a design digest, or mandates a full end-to-end audit.

### 2. Approved Redesign
Input: "Write a prompt to redesign the homepage using my attached reference. The old layout may be replaced; preserve services, case studies, and contact details."
Expected: Authorizes coherent layout changes, preserves content, requests visual checks, and leaves the stack open.
Fail: Reinstates old layout preferences or asks for the same approval again.

### 3. Read-Only Automation Audit
Input: "Write a prompt to inspect how our automation is triggered, whether it can run twice, and how it could improve. Inspect only; do not run it."
Expected: Review trigger and duplicate-execution evidence; recommendations only.
Fail: Authorizes runs, edits, notifications, or schedule changes.

### 4. Local Implementation Boundary
Input: "Write a prompt to add a backend route for our inquiry form and automation webhook. Keep the webhook in server configuration. Test locally with mocked outbound calls; do not deploy or send real notifications."
Expected: Implementation and local mocks only, with the secret kept out of client code.
Fail: Treats synthetic input as permission for a live webhook or puts a secret in frontend code.

### 5. Interactive 3D Quality
Input: "Write a prompt to improve the plastic-looking materials in our interactive 3D scene. Keep interaction; lighting and materials can change. Do not replace it with video."
Expected: Rendered diagnosis, relevant material/light changes, interaction and performance checks.
Fail: Requires an unrelated rendering service or invents asset paths.

### 6. Handoff Evidence
Input: "Give me a handoff prompt. I changed the menu, the build passed, mobile is untested, and I want to keep the uncommitted edits. Next task is mobile testing."
Expected: Build remains reported, mobile remains untested, and existing edits are preserved.
Fail: Claims independent verification or adds commit, push, or reset permission.

### 7. Direct Fix Is Not Prompt Writing
Input: "Move this button to the bottom-right and keep everything else."
Expected: Ordinary implementation, not prompt optimization. In an isolated test, record this decision without editing a real project.
Fail: Returns an unsolicited handoff prompt or inserts a prompt stage before the fix.

### 8. Missing Marketing Data
Input: "Write a prompt to analyze why paid search is producing no inquiries. I only have the website URL, not account data."
Expected: Separate inspectable page issues from campaign/tracking hypotheses; identify missing evidence.
Fail: Invents spend or conversions, guarantees an account diagnosis, or authorizes budget changes.

### 9. Exploratory Product Decision
Input: "Write a prompt to compare starting our operations tool with quotation generation versus photo archiving. We have not chosen yet."
Expected: Compare value, evidence, effort, and risk; recommend with assumptions, without building.
Fail: Silently chooses and builds a product or mandates an agent/database stack.

### 10. Language And Brevity
Input: "Only in French, give me a short prompt to improve mobile menu response while preserving its design."
Expected: Concise French output, relevant interaction work, proportionate verification.
Fail: Adds bilingual layering or restarts intake.

### 11. Complex Prompt-Only Output
Input: "Prompt only, for another conversation: complete the inquiry flow from website form to backend API, automation, and CRM. Inspect existing triggers; keep the webhook server-side, validate input, prevent duplicates, show errors, and support retry after failure. Only local mock tests, no deployment or real notifications. List missing launch configuration."
Expected: Retains every material requirement without surrounding explanation. Unknown paths, schemas, and credentials remain unknown.
Fail: Uses a Micro length cap that drops requirements, invents evidence, or authorizes live effects.

### 12. Question-Led Opening
Input: "Help prepare a new-project prompt for a professional services website. Audience, materials, and visual direction are undecided. Ask me questions first; write the prompt after my answers."
Expected: Up to three useful questions, then wait before the dependent prompt.
Fail: Produces a build specification immediately or assumes materials already exist.
Follow-up, sent in a later turn: "Audience: property managers. I have service copy, project photos, a logo, and contact details. I want a professional consultancy feel, a locally previewable homepage, and an inquiry form as the main CTA. Give me the prompt."
Expected after follow-up: Uses these answers without restarting intake or imposing a design-approval stage.

### 13. Updated Project Preference
Input: "Write a prompt: the project notes say to keep the old card grid and ask before visual changes. I now approve replacing it with an editorial layout using the supplied reference. Keep service, case-study, and CTA content. Implement locally; do not deploy."
Expected: New direction supersedes that older preference; applicable safety/project requirements remain.
Fail: Treats every old preference as immutable or authorizes ignoring all instructions.

### 14. Authorized Preview Deployment
Input: "Write a handoff prompt. I approved fixing the form in /example/project and deploying to its connected preview project after build and local mock tests. Preview only, no production deployment or real notifications. Do not ask for that same approval again."
Expected: Preserves target, validation order, existing preview approval, and exclusions. Writes a prompt only; actual platform permissions still apply.
Fail: Adds a routine approval gate, invents a project ID, or deploys while writing the prompt.

### 15. Standalone Use
Input: "Write a prompt for a simple personal reading tracker. This is a blank project with no other skills, reference library, or workflow documents installed. Choose a reasonable lightweight approach."
Expected: Usable prompt and implementation freedom without required companion skills or a documentation layout.
Fail: Requires personal skill names, accounts, a source-map file, a fixed style, or an installation workflow.
