# nxu - Nexus Uploader CLI

> Upload, download, and manage files in Nexus Raw Repositories with a simple, fast CLI.

[![Go](https://img.shields.io/badge/built%20with-Go-blue?logo=go)](https://golang.org)
[![License](https://img.shields.io/github/license/yourname/nxu)](LICENSE)
[![Releases](https://img.shields.io/github/v/release/yourname/nxu)](https://github.com/yourname/nxu/releases)
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

## 🚀 Quick Start

```bash
nxu configure                          # Set up credentials and base repo URL
nxu upload --file ./build.zip         # Upload a single file
nxu upload --folder ./dist            # Upload an entire folder
nxu download --remote-path path/to/file.zip --output ./file.zip
```

---

## 🗺️ Roadmap (Upcoming Features)

- Parallel uploads with retries
- Automatic SHA256 checksum validation
- Tagging and version metadata
- Generate `.metadata.json` sidecar files
- Upload via manifest file
- Upload history and audit logs
- Search indexed uploads
- CLI validation of files against remote
- Delete remote files
- Rebuildable upload index
- Serve a remote repo path locally over HTTP
- TUI for interactive uploads (future)
- GitHub Pages documentation + manpage support

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
