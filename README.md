# nxu - Nexus Uploader CLI

> Upload, download, and manage files in Nexus Raw Repositories with a simple, fast CLI.

[![Go](https://img.shields.io/badge/built%20with-Go-blue?logo=go)](https://golang.org)
[![License](https://img.shields.io/github/license/aquicksoft-dev/nxu)](LICENSE)
[![Releases](https://img.shields.io/github/v/release/aquicksoft-dev/nxu)](https://github.com/aquicksoft-dev/nxu/releases)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](CONTRIBUTING.md)

---

`nxu` is a lightweight, developer-friendly CLI for working with Nexus Raw Repositories. Designed for automation and ease of use, `nxu` simplifies uploading and downloading files or folders while storing your Nexus credentials securely.

---

## ✨ Current Features

- ✅ Upload single files to Nexus Raw
- ✅ Upload folders with recursive path handling
- ✅ Download files from Raw repositories
- ✅ Configure credentials and endpoint interactively

---

## 📦 Roadmap Features

### ✅ CORE FUNCTIONALITY

| Feature                        | Description                                            |
| ------------------------------ | ------------------------------------------------------ |
| **Upload File or Folder**      | Upload artifacts to Nexus Raw hosted repo              |
| **Subpath Uploading**          | Place artifacts in any subdirectory                    |
| **Parallel Uploads**           | Multi-threaded uploads using Go routines               |
| **Retry on Failure**           | Auto-retry uploads (configurable attempts)             |
| **Checksum Validation**        | Validate SHA256 after upload (optional)                |
| **Dry Run Mode**               | Preview uploads without executing                      |
| **Zip Before Upload**          | Compress folder and upload `.zip`                      |
| **Token & Basic Auth Support** | Supports both password and bearer/token authentication |
| **Interactive Config**         | `nxu configure` command for setup                      |
| **`.env` and Config Support**  | Load config from `~/.nxu/config.json` or env vars      |

---

### 🔍 INDEXING & SEARCH FEATURES *(fills Raw gaps)*

| Feature                        | Description                                          |
| ------------------------------ | ---------------------------------------------------- |
| **Upload Metadata Logging**    | Track file name, version, uploader, timestamp        |
| **Automatic `.metadata.json`** | Generate sidecar JSON metadata per artifact          |
| **Artifact Search**            | Search locally indexed uploads by name, version, tag |
| **Tagging Support**            | Tag uploads (e.g., `--tag beta`, `--tag release`)    |
| **Rebuild Index**              | Reconstruct local manifest from repo path listing    |
| **Manifest Upload**            | Upload from structured `manifest.json` file          |

---

### ✅ VALIDATION & MAINTENANCE

| Feature                        | Description                                       |
| ------------------------------ | ------------------------------------------------- |
| **Validate Checksums**         | Compare local/remote hash (re-download if needed) |
| **Retention Policy Support**   | Delete old versions using `--keep-latest N`       |
| **Sync Mode**                  | Only upload new or changed files                  |
| **Incremental Upload Support** | Upload based on cache/history diff                |
| **Download Support**           | Download any path from Nexus Raw                  |
| **Delete Remote File**         | Authenticated delete support via REST             |

---

### 📚 HISTORY, LOGGING, AND TRACEABILITY

| Feature                      | Description                                            |
| ---------------------------- | ------------------------------------------------------ |
| **Upload History Log**       | Logs upload info locally (`~/.nxu/history.log`)        |
| **Action Audit Log**         | Stores structured JSON logs (file, action, user, time) |
| **Show History Command**     | View past uploads/downloads easily                     |
| **Webhook Support (future)** | Push upload logs to Slack/Discord/webhooks (optional)  |

---

### 🎛️ CLI POWER TOOLS

| Feature                      | Description                                        |
| ---------------------------- | -------------------------------------------------- |
| **Serve Nexus Locally**      | Mirror a Raw path and serve locally over HTTP      |
| **Progress Bar**             | Live upload display per file                       |
| **JSON Output Mode**         | Machine-readable output for CI/CD                  |
| **Interactive Upload (TUI)** | Select files/tags/folders via terminal UI (future) |

---

### 🔧 CONFIGURATION & EXTENSIBILITY

| Feature                      | Description                               |
| ---------------------------- | ----------------------------------------- |
| **Config via CLI or JSON**   | Supports `--user`, `--url` or config file |
| **Env Var Override**         | `NXU_USER`, `NXU_URL`, etc.               |
| **Custom Metadata Support**  | Add arbitrary fields to `.metadata.json`  |
| **Support for `.nxuignore`** | Skip files or folders (like `.gitignore`) |

---

### 🧪 FUTURE (v2.0+)

| Feature                      | Description                                                        |
| ---------------------------- | ------------------------------------------------------------------ |
| **TUI (Interactive UI)**     | Terminal UI to browse/search/upload                                |
| **Web GUI**                  | Optional frontend to interact with indexed metadata                |
| **Plugin Support**           | Run user-defined scripts/hooks before/after upload                 |
| **Cloud Caching/Index Sync** | Push metadata to S3, DynamoDB, or Firestore for team searchability |

---

### 💡 Example CLI Usage

```bash
nxu configure

nxu upload --file ./release.zip --subpath app/v2.0.0 --tag stable

nxu search --name release.zip --version 2.0.0

nxu validate --folder ./release

nxu delete --path app/old-v1.zip

nxu upload --folder ./dist --incremental

nxu log --show
```

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
