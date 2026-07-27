---
name: document-feature
description: Use when a user-facing feature has been added or changed and its end-user documentation needs to be created or updated. Writes a structured doc entry in a fixed schema under docs/ so the corpus can later be transformed into in-app help and a help center. Not for internal code comments or architecture notes.
---

# Document a feature

When a user-facing feature is added or changed, create or update its doc entry under `docs/` using the exact schema below. Consistency matters more than length: every entry uses the same headings in the same order, because these entries are later transformed mechanically into end-user help (tooltips, help center, in-app guidance). Freeform prose does not transform cleanly; a fixed schema does.

## Rules
- One file per feature: `docs/<feature-slug>.md` (lowercase, hyphenated).
- Use the schema headings verbatim and in order. If a section is truly not applicable, write "N/A" rather than deleting the heading.
- Document only what was actually built. Do not invent behavior, screens, or permissions.
- Write "How to use it" in plain end-user language — no code, no internal jargon.
- Update the entry in the same PR as the feature change, and update "Last updated".

## Schema (use exactly)
```
# <Feature name>

**Purpose:** One sentence — what it does and why it exists, in user terms.

**Who can use it:** Roles or permission levels that can access it.

**How to use it:**
1. Plain-language step
2. ...

**Where:** Routes / screens involved (e.g. /matters, Matter detail).

**Data touched:** Entities / tables read or written.

**Permissions / RLS:** Access rules governing who can see or change what.

**Limitations / notes:** Known constraints, edge cases, or gotchas.

**Last updated:** YYYY-MM-DD — PR/commit ref.
```

## Output
- The created or updated `docs/<feature-slug>.md` content.
- A one-line note of which feature it documents and whether it was new or an update.
