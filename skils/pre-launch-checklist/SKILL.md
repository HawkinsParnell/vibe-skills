---
name: pre-launch-checklist
description: Use when I say I'm about to launch, ship, or release a project, or ask whether it is ready to go live. Runs a go/no-go checklist before approving. Not for mid-development feature work.
---

# Pre-launch checklist

Walk through every item and report pass, fail, or "needs manual check". Do not skip ahead, and do not say "ready to launch" unless every item passes or is explicitly waived.

## Accounts & access
- Sign-up, sign-in, sign-out, and password reset work end to end.
- Signed-out users cannot reach pages that require an account; signed-in users land on the right page.

## Data & permissions
- Every table holding user data has Row Level Security enabled.
- A user in one account cannot read or write another account's data — flag as "needs manual check" and ask for a second test account before launch.
- Destructive actions (delete, cancel, refund) require confirmation.

## Core surfaces
- Primary routes render without console errors.
- Every list/table/feed has a real empty state.
- Long actions show a loading state and surface errors with a retry path.
- At 375px width there is no horizontal scroll and primary actions are reachable.

## Environment & secrets
- No test API keys, dev URLs, or localhost references in production code.
- No secret key in client code or any VITE_-prefixed variable.
- Required production environment variables/secrets are set.

## Content & trust
- App name, favicon, social preview, and meta description are set.
- Footer links to working privacy and terms pages.
- No placeholder copy ("Lorem ipsum", "TODO") left in the UI.

## Final
- Summarize failures and manual checks in priority order.
