### Step‑by‑step instructions

1. **Unzip your Chef export** into a project folder. The Convex docs recommend extracting the zip and renaming the folder to your app name.
2. **Unzip this kit** (the file above) into the same project folder. It adds `AGENTS.md`, `.vscode/mcp.json`, `.github` prompts and instructions without touching your code.
3. **Install and run locally** (recommended):

   * `npm install` to install all dependencies.
   * `npx convex dev --once` to initialise a Convex dev deployment (run once).
   * `npm run dev` to start the app and follow any login prompts.
4. **Open VS Code**, enable Copilot Chat in Agent mode, and run **`/ground-rules`**. This reads `.cursorrules` and Convex instructions, then summarises the rules before you make changes.
5. **Optional – Add a build script**: If `package.json` doesn’t already have `"build": "vite build"`, run **`/add-build-script`**. Some Chef exports omit the build script.
6. **Create a repo**: Run **`/init-github`**. Copilot will use the GitHub MCP tools to create a new repository, initialise git, commit, and push. You’ll be asked for the repository name and owner.
7. **Deploy to Vercel**: Run **`/vercel-setup`**. The prompt automatically picks the correct build command based on whether a build script exists, sets the `CONVEX_DEPLOY_KEY` environment variable, and triggers the first deployment. Have your Convex Production Deploy Key ready to paste.
8. Once the deployment finishes, you’ll receive a live URL. You can later add a Preview deploy key for per‑branch backends if desired.

With these steps, you can go from a Chef export to a running development environment and then to a production deployment, all without editing the app code.
