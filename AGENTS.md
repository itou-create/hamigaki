# Repository Guidelines

## Project Structure & Module Organization
- Current repo is minimal; place gameplay code in `src/` (logic, state, rendering), static entry point in `public/index.html`, shared UI or images in `assets/`, automated checks in `tests/`, docs/notes in `docs/`, helper scripts in `scripts/`.
- Keep modules small: `src/game/` for core loop, `src/ui/` for canvas/DOM glue, `src/audio/` if sound is added.

## Build, Test, and Development Commands
- Static prototype: open `public/index.html` directly in a browser or serve locally with `npx serve public` (recommended to avoid CORS issues).
- If npm is initialized: `npm run dev` (start dev server), `npm run build` (bundle for release), `npm test` (run unit tests), `npm run lint && npm run format` (style checks). Add scripts to `package.json` as tooling lands.

## Coding Style & Naming Conventions
- JavaScript/TypeScript, 2-space indent, trailing commas where legal, prefer const/let over var, use arrow functions for callbacks.
- Names: files kebab-case (`tooth-state.ts`), components/classes PascalCase, instances camelCase.
- Keep functions pure where possible; isolate DOM and canvas effects.
- Use ESLint with recommended+typescript rules and Prettier for formatting; commit after a clean `npm run lint`.

## Testing Guidelines
- Framework: Jest for logic, Playwright (or similar) for canvas/DOM interactions.
- Place unit tests in `tests/` mirroring `src/` paths; name them `*.test.ts`.
- Aim for coverage on scoring/cleanliness calculations and timer logic; add smoke UI test per major feature.
- Run `npm test` before opening a PR; document flaky tests in the PR body.

## Commit & Pull Request Guidelines
- Commits: small, present-tense, scope prefixes encouraged (`feat: add brushing feedback`, `fix: clamp cleanliness`).
- PRs: include summary, before/after notes for gameplay changes, screenshots or short clips for UI shifts, and linked issue/Task. Note any follow-up work or known gaps.
