---
name: author-rls-migration
description: Use when making any database schema change in a Supabase-connected project — creating or altering tables, columns, indexes, or policies. Produces a committed SQL migration with RLS enabled. Not for reading data or for writing application/UI code.
---

# Author an RLS migration

When a task requires a database schema change, do not change the schema through the Supabase dashboard and do not run ad-hoc SQL. Produce a migration file so the change is version-controlled and reviewable.

## Steps
1. Create a migration file under `supabase/migrations/`, timestamp-prefixed with a short snake_case description (e.g. `20260101120000_add_clients_table.sql`). With the CLI: `supabase migration new <name>`.
2. Write the change as plain SQL in that file.
3. For every new table, enable Row Level Security in the same migration:
   `alter table public.<table> enable row level security;`
4. Author explicit RLS policies for the access the feature actually needs. A table with RLS on and no policy is locked down by default — that is the safe starting point; grant access deliberately.
5. Keep each migration focused on one logical change. Do not bundle unrelated schema edits.

## Rules
- RLS is enabled on every table, in the migration that creates it. No table ships without RLS.
- Row access is governed by policies, never by exposing a secret key to the client.
- Never target the production database. Migrations apply to dev; production changes happen only through promotion.
- Prefer additive, reversible changes; provide a matching rollback migration when dropping or destructively altering.

## Output
- The SQL migration file contents, plus a one-line summary of what it changes and which policies it adds.
- If multiple tables are affected, list the RLS posture for each.
