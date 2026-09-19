---
name: technical-en-zh-translation-skill
description: Translate English technical or specialist documents into accurate, natural Simplified Chinese, preserving code and identifiers and applying context-aware, extensible domain glossaries. Use for English-to-Chinese documentation translation or terminology review; not for unrelated writing or other language pairs.
---

# English → Simplified Chinese translation

Translate the user's source faithfully. Optimize for technical meaning, established terminology, and readable Chinese, in that order. Do not add technical claims, silently repair the source, or turn a translation request into a rewrite.

## Working rules

1. Identify the document's subject, intended readers, format, and any terminology or formatting instructions supplied by the user. Keep the original structure where practical.
2. Protect literal material before translating: fenced and inline code, commands, options, paths, filenames, URLs, domains, IP addresses, API and function names, JSON/YAML keys, headers, environment variables, registry paths, CVE IDs, hashes, protocol abbreviations, placeholders, and product or project names. Preserve their spelling, case, punctuation, and syntax. Translate code comments or string values only when expressly requested and safe to do so.
3. Read [the style guide](references/style-guide.md) for document-level choices and [the general glossary](references/general-glossary.md) for common terms. Load only the relevant bundled domain file(s): [AI/LLM](references/domains/ai-llm.md), [cybersecurity](references/domains/cybersecurity.md), [cloud native](references/domains/cloud-native.md), or another relevant `references/domains/*.md` file. Also use a glossary the user supplies or a relevant file under the active project's `.technical-en-zh/domains/`, if present. Do not load every domain file by default.
4. Apply a glossary entry only when its **sense and context** match the sentence. For a matching sense, precedence is: explicit terminology in the current request → user-supplied glossary → project `.technical-en-zh/domains/` → bundled domain glossary → general glossary → established usage. A higher-priority entry cannot override the actual meaning of the source or the protected-literal rule. For collisions at the same level, prefer the more specific context; if still tied, follow the user's stated domain priority; otherwise retain the English term and briefly flag the ambiguity.
5. Render natural Simplified Chinese. Preserve modality, negation, conditions, scope, units, comparisons, and security-relevant distinctions. Introduce an English term in parentheses on first mention only when it helps disambiguate a significant concept; do not repeat it mechanically.
6. Check the translation against the source for omissions, changed meaning, altered identifiers, inconsistent terms, and malformed Markdown or tables. By default return the translated document alone. Add a brief translator's note only for material ambiguity, an apparent source error that affects meaning, or a terminology conflict that cannot be resolved from context. Do not guess.

## Extending the vocabulary

Users can provide a Markdown glossary with the request, point to a glossary file, add a project-specific file at `.technical-en-zh/domains/<domain>.md`, or contribute a reusable file under `references/domains/`. Follow [the domain template](references/domain-template.md) and its sense-specific table format. Custom domains can be legal, biology, finance, or any other field. Do not assume that a listed English word has one Chinese translation in every context.

See [the worked example](examples/README.md) for input and output.
