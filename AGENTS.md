# AGENTS.md — Operator Notes

## Quick start (handoff)

The downloaded Chef project runs out of the box. To get it running locally you only need to install dependencies and start the development server:

- `npm install` — install all dependencies for the project【379763478983828†L141-L145】.
- `npx convex dev --once` — initialise a local Convex dev deployment; run this once to link the project to your Convex account. Follow any browser prompts to log in.
- `npm run dev` — launch the development server for the frontend and backend together【379763478983828†L147-L153】.

> **Note**: No code changes are required at this stage. You have taken over from Chef for development; going back into Chef may cause conflicts【379763478983828†L155-L159】. Use GitHub Copilot Chat in Agent mode for assistance. MCP servers (GitHub, Convex, Vercel) are configured via the `.vscode/mcp.json` file included with this kit.

## Project layout

- **Frontend**: `src/` (Vite + React components)
- **Backend**: `convex/` (Convex functions, schema and HTTP handlers)
- **Auth**: Convex Auth (additional providers can be added later)

## Guardrails

- **Minimal change policy** – don’t refactor generated code unless something is broken.
- **No secrets in code** – when you eventually deploy, set keys in Convex/Vercel dashboards rather than hard‑coding them.
- **Deployment (later)** – use Vercel with the command `npx convex deploy --cmd 'vite build'` and the `CONVEX_DEPLOY_KEY` environment variable.

## Detailed rules (authoritative, do not duplicate)

Chef exports include detailed guidelines for working with Convex. Keep these files in your repo and refer to them rather than copying their contents:

- `.cursorrules` – Convex and Cursor guidelines (new function syntax, validators, pagination, etc.)
- `.github/instructions/convex.instructions.md` – instructions used by Chef and Convex agents

## Next steps (when ready)

These actions are **not** part of the hand‑off, but you can perform them later using Copilot Chat and the provided prompt files:

- `/ground-rules` – summarise applicable constraints from `.cursorrules` before making edits.
- `/init-github` – create a new GitHub repository and push the current project.
- `/add-build-script` – add a production build script (`"build": "vite build"`) to `package.json`.
- `/vercel-setup` – set up a Vercel project, configure the build command and environment variables, and trigger the first deploy.