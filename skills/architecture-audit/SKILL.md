---
name: architecture-audit
description: Use when asked to review or audit the codebase's structure, modularity, or maintainability, or when a file has grown large or mixes concerns. A read-only analysis that flags monolithic components, mislocated logic, and coupling, and returns a prioritized refactor plan. Do not modify code during the audit.
---

# Architecture & modularity audit

This is a read-only review. Do not change any code during the audit. Produce a report only, then wait for approval before making edits.

## What to check
- Files that are too large or mix concerns (UI + data fetching + business logic in one file).
- Components that fetch their own data or call Supabase directly instead of going through a data-access layer.
- Duplicated logic that should be a shared utility or hook, and any missing single source of truth for shared state/types.
- Tight coupling where a change in one module would force changes across several others.
- Mislocated code: logic that belongs in a hook, utility, or data layer but sits in a component.

## Output
A prioritized report, most critical first. For each finding:
1. What and where (file/component).
2. Why it's a risk (e.g. "one edit here can break unrelated features").
3. Recommended refactor, as a concrete, ordered step.

End with the top 3 fixes to do first. Do not implement anything until approved.
