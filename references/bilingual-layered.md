# Bilingual Layered Optimization

Use only when requested or when supplied multilingual context benefits from assigning languages
different jobs. Produce one coherent prompt, not parallel translations of every section.

## Language Choices

Keep the user's source language by default. Use the requested languages for technical instructions,
business context, and audience-facing copy. Unspecified layers stay in the source language.
An explicit one-language request takes precedence over this optional strategy.

Ask about a language choice only if it materially affects the output. Do not assume a country,
dialect, currency, audience, or technical language from the language the user happens to write in.
Preserve a regional register when explicitly supplied and useful to the task.

## When It Helps

- Technical collaborators and end users work in different languages.
- A brief contains local terminology that would lose meaning in translation.
- The user requests instructions in one language and customer-facing examples in another.

Keep one language for short edits, simple translation, single-language creative writing, or when
layering would make the result harder to use. English code identifiers alone do not trigger it.

## Possible Layers

Use only layers carrying useful information:

- Objective and business context: the user's chosen working language.
- Technical rules and acceptance tests: the requested technical language, otherwise the source language.
- User-facing copy and tone: the intended audience's language and register.
- Open questions: the language the user can answer most easily.

These are roles, not mandatory headings. Preserve appropriate prompt length and structure.

## Preservation

Keep exact identifiers, quoted text, amounts, dates, deadlines, stack choices, permissions, and
output requirements. Do not invent features, workflow states, localization requirements, or
architecture while changing language. Explain language choices only when requested or needed
to resolve a material ambiguity.

## Example

Source:

```text
Create a prompt for a mobile quotation tool with PDF export. Issued quotations cannot be edited;
changes require a new version. Keep technical instructions in English and business context in Spanish.
```

Optimized:

```text
Objetivo: crear un sistema de presupuestos utilizable desde el móvil, con exportación a PDF.

Technical requirements:
- Issued quotations must not be edited in place.
- A change to an issued quotation must create a new version and preserve the original.
- Verify PDF export, mobile usability, and revision behavior.

Keep the implementation approach open and follow any supplied project requirements.
```

The example uses two languages because the user requested them. It does not infer extra states,
currencies, approval roles, or commercial features.
