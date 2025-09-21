Title: Vercel project setup (MCP)
Goal: Wire up Vercel for deployment after the repo exists.
Steps (with approval at each step):
1. Create or link a Vercel project using the GitHub repository `<OWNER>/<REPO>` via the Vercel MCP tools.
2. Set the build command to `npx convex deploy --cmd 'vite build'` in the project’s build settings. This command deploys Convex and builds the frontend in one step.
3. Add the environment variable `CONVEX_DEPLOY_KEY` with production scope (ask the user to provide the deploy key). Optionally add a preview key.
4. Trigger the initial deployment and fetch build logs. Summarise the outcome and provide the deployment URL.
Output: Deployment URL, log summary and any next steps.