# W.Edit — GitHub Starter

Starter project for **W.Edit**, a Windows/macOS desktop editing app plus a GitHub Pages download website.

## What is included
- `desktop/`: Electron desktop app starter with sign-up/sign-in UI.
- `site/`: responsive download page for Windows and macOS.
- `.github/workflows/`: GitHub Actions workflow to build Windows and macOS release installers.
- `package.json`: project scripts and dependencies.

## Important authentication note
The included sign-up/sign-in is a **local prototype only**. It stores a salted password hash in the current computer's local app data, not the raw password. It does not create a cloud account, sync accounts across computers, or provide production-grade account recovery. Do not use a valuable/reused password with this prototype.

For real accounts shared across Windows and Mac, connect a trusted authentication provider (for example Supabase Auth) before publicly launching sign-up. A short PIN alone is not secure for a cloud account; use a proper password or passkey.

## Run locally
1. Install Node.js LTS from https://nodejs.org/ and Git from https://git-scm.com/.
2. Extract this folder.
3. Open a terminal in this folder and run:
   ```bash
   npm install
   npm start
   ```
4. The app opens as a desktop window.

## Publish on GitHub
1. Create a new GitHub repository called `w-edit`.
2. Upload the contents of this folder to the repository.
3. In `site/index.html`, replace `YOUR-GITHUB-USERNAME/w-edit` with your actual GitHub username and repository.
4. Enable GitHub Pages in **Settings → Pages** and choose the `main` branch, `/site` folder.
5. Push a version tag such as `v0.1.0` to trigger the release build workflow:
   ```bash
   git tag v0.1.0
   git push origin v0.1.0
   ```
6. GitHub Actions will build installers for Windows and macOS and attach them to a GitHub Release. Review the workflow run and release before sharing the links.

## Current status
This is a starter, not a finished video editor. The timeline, real media engine, rendering/export, and cloud authentication still need to be implemented. Never advertise installers until a GitHub Release has successfully published them.
