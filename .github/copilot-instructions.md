# Copilot Instructions

These instructions tell GitHub Copilot’s coding agent how to operate on this repository.

- **Plan first; minimise changes** – Copilot should generate a plan before editing files and keep diffs small. For the hand‑off, no code edits are allowed.
- **Use the provided prompts** – When you need to perform actions beyond local development (e.g. adding a build script, creating a GitHub repo or deploying to Vercel), use the appropriate prompt files under `.github/prompts`.
- **Follow AGENTS.md** – The `AGENTS.md` file at the project root defines how to run and work with this app. Copilot should always consult it before acting.
- **Avoid secrets** – Never commit API keys or secrets. Use environment variables in Convex and Vercel dashboards.

### Later actions (not during hand‑off)

Use these prompts via Copilot Chat when you’re ready:

- `ground-rules.prompt.md` – summarises Convex and Cursor guidelines from `.cursorrules` and `convex.instructions.md`.
- `init-github.prompt.md` – initialises a new GitHub repo and pushes the current code using the GitHub MCP tools.
- `add-build-script.prompt.md` – adds a production build script to `package.json` (`"build": "vite build"`).
- `vercel-setup.prompt.md` – creates a Vercel project, configures the build command (`npx convex deploy --cmd 'vite build'`) and environment variables, and deploys.