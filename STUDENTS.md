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

## 4. Project documentation & policies (required reading)

📚 **Official documentation:** <https://docs.excalidraw.com> — the developer docs for the editor
package and the app (press **`?`** inside the app for the shortcut list).

Excalidraw has its own established contribution processes. They are **not restated here** — you
are responsible for finding, reading, and following them from the sources below:

| You must take care of | Where to find it |
| --- | --- |
| How to use the tool | <https://docs.excalidraw.com> |
| Code review process | [Contributing guide](https://docs.excalidraw.com/docs/introduction/contributing) |
| Bug / issue resolution process | [Contributing guide](https://docs.excalidraw.com/docs/introduction/contributing) |
| Pull request conventions & PR policies | [Contributing guide](https://docs.excalidraw.com/docs/introduction/contributing) (see [CONTRIBUTING.md](CONTRIBUTING.md)) |
| AI policies | Check the [contributing guide](https://docs.excalidraw.com/docs/introduction/contributing) for the project's current stance before submitting AI-assisted work |
