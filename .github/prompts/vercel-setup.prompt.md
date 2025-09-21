Title: Vercel project setup (Convex first-class integration, MCP)

Goal
Wire Vercel for deployment of this Chef export using Convex’s recommended flow.  Choose a build command based on whether a `build` script exists.  Use MCP tools and ask for approval before each external operation.

Preconditions
- The GitHub repository exists (`<OWNER>/<REPO>`).  You should have already run `/init-github`.
- You have your Convex Production Deploy Key ready to paste.

Plan
1. Detect the build script:
   - Inspect `package.json`.  If it contains a `"build"` script under `"scripts"`, then set the **Build Command** to:

     ```bash
     npx convex deploy --cmd 'npm run build'
     ```

   - If no build script is present, set the **Build Command** to:

     ```bash
     npx convex deploy --cmd 'vite build'
     ```

     This uses Vite’s default production build without modifying your code.

2. Create or link a Vercel project:
   - Using the Vercel MCP, create (or connect) a project named after the repo (`<REPO>`) from `<OWNER>/<REPO>`.
   - Leave the install command and output directory to Vercel’s defaults (framework detection handles this).

3. Add environment variables:
   - In Vercel’s settings, add `CONVEX_DEPLOY_KEY` with **Production** scope.  Ask the user for the key at this step.  If a Preview Deploy Key is available, also add `CONVEX_DEPLOY_KEY` with **Preview** scope.
   - Do not set `CONVEX_URL`; the Convex CLI will set it during deploy.

4. Trigger the first deployment:
   - Kick off a production deployment using MCP.  Stream the build logs and summarise the results.  Return the deployment URL.

5. Post‑deploy checklist:
   - Verify the Build Command in Vercel matches the selected variant.
   - Confirm `CONVEX_DEPLOY_KEY` (Production) is set (Preview optional).
   - Provide the live URL and note any warnings.

Output
Display the deployment URL, a summary of the build logs, and a checklist of the settings that were applied.