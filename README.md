# Dock CLI

Official Dock CLI downloads for macOS, Linux and Windows. Requires **Node.js 24.14.1+ with npm**. Bun is not required for users.

Download a version from [Releases](https://github.com/dock-hq/cli-releases/releases) when available. This repository hosts the compiled CLI package, public docs, skills and installers. The Dock backend and internal plans are maintained separately.

## Install

Choose a release and download its `install.sh` (macOS/Linux) or `install.ps1` (Windows). Replace `VERSION` below with that release's version, without the leading `v`.

```sh
sh install.sh --version VERSION --release-url https://github.com/dock-hq/cli-releases/releases/download/vVERSION
```

```powershell
./install.ps1 -Version VERSION -ReleaseUrl https://github.com/dock-hq/cli-releases/releases/download/vVERSION
```

The installer verifies the package's SHA-256 checksum, installs through npm into a user-local directory, and prints its executable path. Agents can use that path directly. Keep Node.js on PATH. Re-run with another version to update. These packages are distributed through GitHub Releases; no npm registry publication is required.

## Connect and explore

Use the printed executable path, or `dock` if its directory is on PATH:

```sh
dock auth login
dock auth status
dock api describe GET /workspaces
dock api request GET /workspaces --query page=1 --query limit=10
dock docs
dock skill
```

Browser login requires a compatible Dock server, an administrator account and API access. Credentials stay in the OS credential store; Linux needs an unlocked Secret Service. `DOCK_API_KEY` is also supported for automation. Never paste credentials into chat. Run `dock auth logout` to disconnect.

If migrating from the unreleased Go prototype, log out with that executable before switching, then sign in again with the Node CLI.

Preview releases are unsigned and may require API changes that are not deployed yet. Full workspace-editor coverage is in development. Agents need local shell access; hosts without it need a separate connector.
