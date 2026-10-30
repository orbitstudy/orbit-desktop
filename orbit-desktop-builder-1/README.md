# Orbit Desktop — build installers for macOS, Windows and Linux

This project wraps your Orbit HTML page in an Electron desktop window. A ZIP is only an archive; each operating system needs its own packaged build.

## Fastest route (no local build required)

1. Create/sign in to a GitHub account.
2. Create a **new private or public repository** (e.g. `orbit-desktop`).
3. Extract this ZIP on your computer.
4. Upload the *contents* of this folder to the repository root (so `package.json`, `main.cjs`, `app/`, and `.github/` are at the root). Commit the files.
5. In the repository, open **Actions** and enable workflows if prompted.
6. Open **Releases → Draft a new release**, create tag `v1.0.0`, and publish.
7. Open **Actions** to watch the three OS builds. When they finish, download installers from the release assets:
   - macOS: `.dmg` (or `.zip`)
   - Windows: `.exe` installer (and/or `.zip`)
   - Linux: `.AppImage` (and/or `.deb`)

You can also run the workflow manually from Actions → Build Orbit installers → Run workflow.

## Test locally (optional)

Install Node.js 22 or newer. In this folder run:

```sh
npm install
npm start
```

To package only for the current computer:

```sh
npm run dist
```

## Notes

- Build on the matching operating-system runners; the workflow does this for macOS, Windows, and Linux.
- The generated packages are **not code-signed or notarized**. Windows/macOS may show security warnings. Public distribution usually benefits from signing/notarization.
- Installers have not been built or tested in this workspace.
- The HTML and icon assets live in `app/`. Keep relative paths and file names intact.
- This is a desktop wrapper around the page. Browser data and app data may be separate.
