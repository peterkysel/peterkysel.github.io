# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Personal portfolio site hosted on GitHub Pages at `peterkysel.github.io`. Built with **Vue 3**, **TypeScript**, and **Tailwind CSS**.

## Commands

```bash
npm run dev        # start dev server
npm run build      # type-check + production build (output: dist/)
npm run type-check # TypeScript check only
npm run lint       # ESLint with auto-fix
npm run format     # Prettier over src/
```

## Architecture

- `src/main.ts` — app entry point, mounts Vue with Pinia + Router
- `src/router/index.ts` — Vue Router (hash history for GitHub Pages)
- `src/views/` — page-level components mapped to routes
- `src/assets/main.css` — Tailwind entry (`@import "tailwindcss"`)
- Single `tsconfig.json` extending `@vue/tsconfig/tsconfig.dom.json` (no project references)

## Tooling

- **Formatting**: Prettier runs automatically via a PostToolUse hook after every Edit/Write. No manual formatting needed.
- **Package manager**: npm
- **Tailwind**: v4 — configured via `@tailwindcss/vite` Vite plugin, no `tailwind.config.js` needed. Entry point is `src/assets/main.css` with `@import "tailwindcss"`.
- **ESLint**: flat config (`eslint.config.ts`), covers `.ts` and `.vue` files.

## TypeScript Setup Notes

- `@vue/tsconfig` does **not** ship `tsconfig.node.json` — only `tsconfig.json`, `tsconfig.dom.json`, `tsconfig.lib.json`.
- Project uses a **single** `tsconfig.json` extending `@vue/tsconfig/tsconfig.dom.json` — no project references. This avoids `vue-tsc -b` emitting a `vite.config.js` that conflicts with Vite's ESM config loading.
- Build script uses `vue-tsc --noEmit` (not `-b`).
- `@types/node` is required for `node:url` in `vite.config.ts`.

## Git & Deployment

- The `main` branch deploys directly to GitHub Pages.
- Force-pushing to `main` is blocked by project policy.
- Commits follow conventional commit style (see recent git log).

## Language

- All code comments and CLAUDE.md content must be written in **English**, even when the user communicates in Slovak.

## Constraints

- `.env` and `*.key` files are never to be read or committed.
