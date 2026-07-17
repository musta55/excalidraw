# Excalidraw — Student Setup Guide

This is a **course fork of [excalidraw/excalidraw](https://github.com/excalidraw/excalidraw)** — the
open-source **virtual whiteboard** for sketching hand-drawn-style diagrams (React + TypeScript,
Vite, Yarn workspaces). The same code powers <https://excalidraw.com>.

📚 **Official documentation:** <https://docs.excalidraw.com>

---

## 1. Prerequisites

| Tool | Version | Notes |
| --- | --- | --- |
| **Node.js** | **18 or newer** (LTS recommended) | Check with `node -v`. |
| **Yarn** | **1.22 (classic)** | Pinned via `packageManager` — just run `corepack enable` once and the right version is used automatically. |
| **Git** | any recent | |

Works the same on Windows, macOS, and Linux — no database or Docker needed.

---

## 2. Install & run

```bash
git clone <your-team-fork-url>
cd excalidraw

corepack enable      # once — activates the pinned Yarn
yarn                 # install dependencies
yarn start           # dev server for the app
```

Open the URL Vite prints (typically **http://localhost:3000**) — you get the full whiteboard,
hot-reloading as you edit the code.

Useful variants:

```bash
yarn build           # production build of the app (excalidraw-app/build)
yarn start:example   # builds the packages and runs a minimal embedding example
```

---

## 3. Run the tests

```bash
yarn test                     # vitest in watch mode (app + packages)
yarn test:app --watch=false   # single full pass, CI-style
yarn test:typecheck           # TypeScript (tsc)
yarn test:code                # ESLint (zero warnings allowed)
yarn test:other               # Prettier formatting check
yarn test:all                 # everything above, in one go

yarn fix                      # auto-fix formatting + lint issues
```

Run `yarn test:all` before you push — it's what the CI expects to pass.

---

## 4. How to use the tool

Excalidraw is a collaborative whiteboard:

- Draw **shapes, arrows, freehand, and text** from the toolbar; select and style elements
  (colors, fills, stroke, opacity).
- Press **`?`** in the app for the full keyboard-shortcut list.
- **Export** to PNG/SVG or save/load `.excalidraw` files; use **libraries** for reusable components.
- The editor itself is the npm package `@excalidraw/excalidraw` (in `packages/`) — the
  developer docs for embedding and its API live at <https://docs.excalidraw.com>.

---

## 5. How to review the code

Code review is part of the work, not an afterthought:

1. Read the linked issue first, then the diff (GitHub → **Files changed**).
2. Check out the branch locally, run the app (`yarn start`), and run the tests
   (`yarn test:app --watch=false`, `yarn test:typecheck`).
3. Leave **line comments** for specific problems and finish with a summary review —
   **Approve** or **Request changes**.
4. Look for: correctness, tests covering the new behavior, naming/clarity, and unintended
   changes (lockfiles, snapshots, formatting noise).

Every PR needs at least **one teammate approval** before merge — no self-merges. Review the code,
not the person; be specific and constructive.

---

## 6. Pull requests (PRs)

1. Branch off `master`: `git checkout -b feature/<short-name>` (or `fix/<issue-number>-<slug>`).
2. Keep commits small with meaningful messages.
3. Make sure `yarn test:all` passes before pushing.
4. Push to the course fork and open the PR against the course fork's `master` — **never upstream**.
5. In the description: what changed, why, how you tested it, and the linked issue (`Closes #12`).
6. Address review comments with follow-up commits (avoid force-pushes during review), then
   re-request review.

---

## 7. Issue resolution process

1. All work is tracked as **GitHub Issues** on the course fork — bug, feature, or task.
2. Before coding: pick or create an issue, get it **assigned** to you, and outline your approach
   in a comment if it's non-trivial.
3. One issue → one branch → one PR, linked with `Closes #<n>` so the issue closes automatically
   on merge.
4. Blocked for more than a day? Say so on the issue (what you tried, where you're stuck) instead
   of going quiet.
5. An issue is **done** when its PR is merged and the behavior is verified.

---

## 8. AI policies

AI assistants (Claude, ChatGPT, Copilot, …) are allowed as a learning and productivity aid,
under these rules:

- **You are the author.** Understand and be able to explain every line you submit — "the AI
  wrote it" is never an explanation.
- **Test before you commit.** Never push AI-generated code you haven't run and tested locally.
- **Disclose it.** Note meaningful AI assistance in the PR description
  (e.g. *"AI-assisted: first draft of the element utils + tests"*).
- **Protect data.** Never paste secrets, tokens, or private data into AI tools.
