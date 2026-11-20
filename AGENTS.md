# Project Rules

## What this is

The Leave Request module for Budiman Company's HR Management System.
Four roles and one flow: an Employee submits a leave request to a
supervisor in their own division, the Supervisor signs it or rejects it
with a remark, the Employee sends the signed request to the HR queue,
and any HR officer approves or rejects it with a remark. The Admin sees
every request but changes nothing. Statuses: Pending supervisor, Signed,
Pending HR, Approved, Rejected by supervisor, Rejected by HR.

## What it is built with

Next.js with TypeScript, SQLite with Prisma, Tailwind CSS with daisyUI,
login with a signed session cookie and bcryptjs password hashing, and
server actions for buttons and forms. No separate API.

## How to run it

Node 20.9 or newer. `npm install`, then `npm run dev`, open
http://localhost:3000. Demo logins (password `password123`) are listed in
the HRMS document, section 7.2.

## Where things live

- `docs/Agentic AI - HRMS Doc.pdf` — what to build, for whom, and why. Read it before writing specs or code.
- `docs/templates/` — blank spec files to copy from.
- `docs/specs/` — the agreed specs: 01-requirements, 02-design, 03-tasks.
- `src/app/` — the app screens and server actions.
- `prisma/` — database schema and demo data seed.

## How to work on it

- Specs first. Nothing gets built that is not in an approved spec. If behaviour changes, update the spec first, then the code.
- Build High priority requirements first; login comes first.
- Every commit uses a conventional commit message, such as `feat: add login page`, `fix: stop empty leave requests`, `docs: update design spec`.
- Ask before running commands, and explain what a change does before making it.

<!-- BEGIN:nextjs-agent-rules -->

## This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

## UI components: daisyUI by default

- For any UI work in this project, use daisyUI 5 components as the default whenever one exists for the need (buttons, inputs, forms, cards, modals, tables, nav, alerts, badges, breadcrumbs, etc.). Follow the installed `daisyui` skill.
- Use plain Tailwind utilities only for layout and spacing, or when no daisyUI component fits.
- daisyUI is not installed yet. Before the first UI task, add it: install `daisyui` (Tailwind CSS 4 is already set up), import it in `src/app/globals.css` with `@plugin "daisyui";`, and pick a distinctive theme rather than the default look.
- Keep the anti-slop design guidance active: distinctive typography and color, consistent spacing, real states (loading, empty, error), and accessible contrast.
