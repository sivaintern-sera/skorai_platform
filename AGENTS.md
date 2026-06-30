# AGENTS.md

## Project Context

SKORAi is a premium full-stack SaaS platform for higher education student success, career readiness, workforce readiness, and institutional analytics.

The product should feel credible for institutional buyers, advisors, students, and employer partners. Build it like a senior product engineer and senior designer collaborated on it: polished, practical, accessible, secure, and grounded in real workflows.

## Required Stack

Use the following stack unless the repository owner explicitly changes direction:

- Next.js App Router
- TypeScript
- Tailwind CSS
- Prisma
- PostgreSQL
- Zod
- A secure authentication system

## Product And UI Standards

- Build production-quality UI that looks intentionally designed, not generated.
- Use clean reusable components for layout, forms, tables, navigation, cards, dialogs, and empty states.
- Keep interfaces focused, scannable, and appropriate for a higher-education SaaS product.
- Avoid generic AI-looking gradients, emoji-heavy sections, fake dashboards, dead buttons, placeholder flows, and hardcoded analytics.
- Do not ship decorative dashboards or metrics unless they are backed by real persisted data.
- Every visible feature must work end-to-end with real backend/database persistence.
- Avoid TODOs for core features. If a feature is visible, it should be implemented.

## Data And Backend Rules

- Use Prisma with PostgreSQL for persistent data.
- Model realistic institutional workflows and relationships instead of toy examples.
- Use realistic seed data for development and demos.
- Validate all form input on both the client and server.
- Use Zod schemas for request validation, form validation, and server-side safety.
- Never trust client-provided role, user, institution, or ownership data without server-side checks.
- Avoid hardcoded analytics. Compute analytics from stored records or clearly scoped database queries.

## Auth And Access Control

- Protect authenticated routes.
- Implement role-based access control for:
  - `ADMIN`
  - `ADVISOR`
  - `STUDENT`
  - `EMPLOYER`
- Enforce authorization on the server, not only in the UI.
- Hide or disable UI actions that the current user cannot perform, but still validate permissions server-side.
- Keep auth secrets, database URLs, and provider credentials out of source control.

## Engineering Standards

- Prefer simple, composable, well-named modules over large one-off files.
- Keep components reusable, typed, and easy to test.
- Keep server actions, route handlers, and database access explicit and validated.
- Handle loading, empty, error, and success states for user-facing flows.
- Use accessible semantics for forms, buttons, navigation, tables, and dialogs.
- Do not leave dead buttons, fake links, or nonfunctional controls in committed UI.
- Do not commit generated build output, local environment files, or secrets.

## Verification

Before saying work is complete, run:

```bash
npm run lint
npm run test
npm run build
```

If a command cannot be run, clearly explain why and what remains unverified.
