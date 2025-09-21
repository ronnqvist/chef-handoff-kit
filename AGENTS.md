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

After confirming the app runs locally, use Copilot Chat to automate the rest of your workflow.  The following **slash prompts** live in `.github/prompts/` and can be executed directly in Copilot Chat (Agent mode):

- **`/ground-rules`** – read `.cursorrules` and Convex instructions and summarise the applicable guidelines before you make changes. Run this once per session to refresh your understanding.
- **`/init-github`** – create a new repository under your GitHub account (using the GitHub MCP tools), initialise git locally if needed, commit all files, add a remote, and push. The prompt will ask for your owner and repo name.
- **`/add-build-script`** – *(optional)* add a `build` script to `package.json` (`"build": "vite build"`) if one doesn’t already exist. Chef projects often ship without a build script【379763478983828†L163-L169】; run this prompt only if it’s missing.
- **`/vercel-setup`** – configure Vercel for deployment using Convex’s first‑class integration. The prompt will detect whether a build script exists and choose the appropriate build command (`npx convex deploy --cmd 'npm run build'` or `npx convex deploy --cmd 'vite build'`), set the `CONVEX_DEPLOY_KEY` environment variable (you’ll paste it), and trigger the first deploy.

These prompts guide Copilot through multi‑step tasks safely by using the MCP connectors; you’ll be asked to approve each external action.