### What’s included

* **AGENTS.md** – a minimal operator guide with commands to run the project locally and guardrails for future work. It links to `.cursorrules` and the Convex instructions for deeper rules.
* **.vscode/mcp.json** – configures the Convex (stdio), GitHub (HTTP) and Vercel (HTTP) MCP servers so Copilot Chat can access them without extra setup.
* **.github/copilot-instructions.md** – repo‑level guidance for Copilot (minimal edits, follow prompts, no secrets, respect AGENTS.md).
* **Prompt files** under `.github/prompts` – ready‑made Copilot slash‑commands for summarising constraints (`ground-rules`), creating a GitHub repo (`init-github`), adding a build script later (`add-build-script`) and wiring up Vercel (`vercel-setup`).

### How to use it

1. **Download and unzip the Chef project** into a directory and rename it as desired (e.g. `MyApp`). The Chef docs advise unzipping and renaming for convenience.
2. **Copy the contents of this kit** (extract the ZIP above) into the root of your unzipped project so it adds `AGENTS.md`, `.vscode`, and `.github` directories. These files don’t modify your app code.
3. In your terminal, run:

   * `npm install` to install dependencies.
   * `npx convex dev --once` to initialise a Convex dev deployment (first time only).
   * `npm run dev` to start the local development server and follow any login prompts.
4. Read `AGENTS.md` in the project root. It outlines the quick‑start commands, guardrails and points to the detailed Convex rules. **No code changes are needed at this stage**; Chef recommends taking over development outside of Chef and warns that returning to Chef will cause conflicts.
5. When you’re ready for the next phases (adding a build script, creating a GitHub repo, or deploying to Vercel), use Copilot Chat (Agent mode) in VS Code. Attach the appropriate prompt file (`ground‑rules`, `init‑github`, `add‑build‑script`, `vercel‑setup`) to guide Copilot through the process.

This setup ensures a smooth transition from Chef to your own development environment while keeping the exported code untouched.
