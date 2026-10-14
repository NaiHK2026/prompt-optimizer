# Bilingual Layered Evaluation Cases

Use only when evaluating the optional language strategy. Give an evaluator the input without the
expected outcome and assess actual responses. These fixtures do not establish test results.

## 1. Preserve Source Language

Input: "Reformule ce prompt en français : changer le texte du bouton en 'Contactez-nous'."

Expected: A short French prompt preserving the exact replacement; no automatic English headings.

## 2. Explicit Layer Languages

Input: "Write a prompt for a mobile quotation tool with PDF export. Issued quotations require a new version for changes. Keep technical instructions in English and business context in Spanish."

Expected: The requested language division and revision preservation; no invented currency,
roles, workflow states, or additional commercial features.

## 3. One-Language Override

Context: Bilingual layering was previously requested.
Input: "For this task, output the entire prompt in English only."

Expected: English-only output; earlier language preferences do not override this request.

## 4. Identifier And Number Preservation

Input: "Optimize this in Spanish, keeping API rules in English: POST /api/inquiries, fields lead_id and created_at, budget EUR 12,800, deadline 2027-01-15."

Expected: Identifiers, budget, currency, and date remain exact. Language changes do not change
the API contract or turn the deadline into an assumed schedule.

## 5. No Unnecessary Translation

Input: "Write a prompt for a warm Japanese brand introduction, entirely in Japanese."

Expected: Japanese-only output. Code-related language defaults are irrelevant.

## 6. Ambiguous Business State

Input: "Improve this prompt: confirmed quotations cannot be edited."

Expected: Do not invent whether confirmed means approved, issued, or paid. Ask only if this
distinction matters to the deliverable; otherwise retain the terminology.
