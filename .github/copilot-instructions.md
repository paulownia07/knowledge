# Repository instructions

## Purpose

This repository is a technical knowledge base and documentation collection for learning, reference, and practical note-taking. The main content is Markdown-based documentation organized by technology area.

When generating or editing content, prioritize clarity, accuracy, and reusability over verbosity.

## General principles

- Keep content factual, practical, and easy to scan.
- Prefer concise explanations with concrete examples.
- Write in Japanese unless the target document is explicitly written in English.
- Preserve the repository's knowledge-base style: short notes, practical commands, and relevant references.
- Do not invent undocumented features, commands, or product behavior.
- If a document is marked as WIP, treat it as a draft and do not claim it is finalized.

## Documentation style

- Use Markdown headings in a consistent structure: `#`, `##`, `###`.
- Use clear section names such as `Install`, `Basics`, `Command`, `Config`, `Examples`, and `Reference`.
- Prefer short paragraphs, bullet lists, and fenced code blocks.
- Add code examples only when they are directly useful for the topic.
- Keep examples realistic and minimal.
- Include command examples with relevant context when necessary.

## File and folder conventions

- Keep documents under the appropriate category folder such as `docs/python/`, `docs/docker/`, `docs/aws/`, etc.
- Maintain the naming pattern used by the repository: topic names in lowercase, with descriptive filenames.
- Preserve the existing index structure and category organization.
- When adding a new document, add or update the corresponding index page if applicable.

## Links and navigation

- Use relative links between Markdown documents.
- Prefer linking to the nearest relevant index or category page.
- Keep navigation logic consistent with the repository's current site structure.
- Do not add broken links or references to non-existent files.

## Content expectations

- Focus on learning materials, operational tips, command references, configuration examples, and practical notes.
- Prefer information that helps a developer understand a concept quickly and apply it safely.
- For technical commands, include prerequisites, usage context, and important cautions when relevant.
- If the topic is a complex system, explain the minimum necessary background before the examples.

## Editing behavior

- Do not make unrelated changes.
- Do not rewrite existing documents more than necessary.
- Preserve the original intent and structure of the document unless an update is clearly needed.
- Keep changes consistent with neighboring documents in the same category.

## Quality bar

Before finalizing a change, check that:

- the content matches the repository's purpose,
- the wording is clear and consistent,
- formatting is valid Markdown,
- links are valid relative paths,
- the document remains aligned with the surrounding category.

## Commit conventions

- Use Conventional Commits for every git commit message.
- Follow the format: `type(scope): subject`
- Recommended types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
- Keep the subject in the imperative mood, concise, and under 72 characters.
- Use lowercase for the type and subject unless a proper noun is required.
- Add a body and footer only when the change needs explanation beyond the subject.
- When writing commit messages for this repository, prefer English unless the existing document set or team convention clearly uses Japanese.
- Do not create vague messages such as `update`, `fix bug`, or `misc changes`; use a specific conventional commit type and a clear subject.

Examples:

- `docs: add docker basics overview`
- `feat: add python uv install guide`
- `fix: correct broken links in git documentation`

## Special notes for this repository

- This repository contains both completed documents and WIP materials.
- Maintain the distinction between mature docs and draft docs.
- Prefer incremental improvements over major restructuring unless there is a clear need.
- Keep a practical, study-oriented tone rather than a formal product-document tone.
