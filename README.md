# Dock CLI

Official Dock CLI downloads for macOS, Linux and Windows (ARM64 and AMD64). The executable needs no Go, Node or Bun runtime.

Download a version from [Releases](https://github.com/dock-hq/cli-releases/releases) when available. This repository contains distribution files and instructions; Dock source code is maintained separately.

## Install

Choose a release and download its `install.sh` (macOS/Linux) or `install.ps1` (Windows). Replace `VERSION` below with that release's version, without the leading `v`.

```sh
sh install.sh --version VERSION --release-url https://github.com/dock-hq/cli-releases/releases/download/vVERSION
```

```powershell
./install.ps1 -Version VERSION -ReleaseUrl https://github.com/dock-hq/cli-releases/releases/download/vVERSION
```

The installer verifies the binary's SHA-256 checksum and prints its installed path. Agents can use that path directly without changing PATH. Re-run with another version to update.

## Connect and explore

```sh
dock auth login
dock auth status
dock api describe GET /workspaces
dock api request GET /workspaces --query page=1 --query limit=10
dock skill
```

Browser login requires a compatible Dock server, an administrator account and API access. Credentials stay in the OS credential store; Linux needs an unlocked Secret Service. `DOCK_API_KEY` is also supported for automation. Never paste credentials into chat. Run `dock auth logout` to disconnect.

Preview releases are unsigned and may require API changes that are not deployed yet. Full workspace-editor coverage is in development. This CLI does not install a remote connector; agents need local shell access.
