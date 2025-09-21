Title: Add production build script to package.json
Goal: Prepare for deployment by adding a single `build` script.
Steps:
1. Open `package.json`. If a `build` script is not present, insert `"build": "vite build"` into the `scripts` section.
2. Do not modify any other scripts.
3. Show a diff of `package.json` and wait for approval before committing.
Output: The proposed change and a confirmation prompt.