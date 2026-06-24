
# Godot 4.7 QuickStart Template

[![itch.io](https://img.shields.io/badge/itch.io-Live%20Demo-3eff6a?logo=itch.io)](https://hubacekjakub.itch.io/godot-quick-start)
[![CI Status](https://github.com/hubacekjakub/Godot-QuickStart/actions/workflows/main.yml/badge.svg)](https://github.com/hubacekjakub/Godot-QuickStart/actions/workflows/main.yml)
[![Latest Release](https://img.shields.io/badge/GitHub-Release-blue?logo=github)](https://github.com/hubacekjakub/Godot-QuickStart/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/hubacekjakub/Godot-QuickStart/blob/main/LICENSE)
[![Godot 4.7](https://img.shields.io/badge/Godot-4.7-blue)](https://godotengine.org/)

> Looking for a different Godot version? Use the **branch switcher** (the dropdown at the top-left of this page on GitHub) to see all supported versions.

**A minimalist Godot 4.7 template with automated CI/CD, advanced Git configuration, and itch.io deployment.** Speed up development and deployment of any Godot project.

🎮 **[Try Live Demo](https://hubacekjakub.itch.io/godot-quick-start)**

## ✨ What Makes This Special

This template eliminates the tedious setup work for modern Godot development:
- **Zero-config CI/CD** - Works out of the box with GitHub Actions
- **Professional Git Standards** - Pre-configured Git LFS with lockable binaries and merge-safe scene formats.
- **Production-ready workflow** - Used for real game releases
- **Developer-friendly** - VS Code integration with proper debugging
- **One-tag deployment** - Push `v1.0.0` and your game is live on itch.io

Perfect for game jams, prototypes, or serious indie projects where you want a clean slate!

## 🚀 Quick Start

1. Click **Use this template** → Create a new repository.
2. Follow the **[SETUP](SETUP.md)** guide to get everything running in minutes.
3. **Press F5** in Godot to run • **Start building** your magic.

**Status:** The message "magic starts here" will appear centered on screen.

## ⚡ Features

- **Minimalist Skeleton** - No bloat, just a clean centered label to start your project.
- **Complete CI/CD Pipeline** - Push a tag, get automatic builds + itch.io deployment
- **Advanced Git Configuration** - Optimized `.gitattributes` for LFS, team locking, and merge safety.
- **Multi-Platform Builds** - Windows, Linux, Web exports on every release
- **VS Code Integration** - Debugging, tasks, and launch configurations included
- **Professional Structure** - Organized folders, export presets, proper gitignore

## 🤖 Automated Deployment

### One-Command Release
```bash
git tag v1.0.0 && git push origin v1.0.0
# → Automatic build + GitHub release + itch.io deployment!
```

### Deployment Setup
Add these GitHub secrets for itch.io deployment:
- **`BUTLER_API_KEY`** - Get from https://itch.io/user/settings/api-keys
- **`ITCH_USERNAME`** - Your itch.io username
- **`ITCH_GAME_NAME`** - Your game project name (e.g., `godot-quick-start`)

**Example:** This demo was deployed automatically: https://hubacekjakub.itch.io/godot-quick-start

### What Happens Automatically
1. **Validation** - GDScript syntax check and project verification
2. **Build** - Creates Windows .exe, Linux executable, and Web build
3. **Release** - GitHub release with downloadable files
4. **Deploy** - Web version automatically published to itch.io
5. **Notify** - Build status and links in GitHub Actions

## 📁 Project Structure

```
├── scenes/          # Game scenes (.tscn)
├── levels/          # Main game levels
├── scripts/         # GDScript files (.gd)
├── assets/          # Fonts, sounds, textures
├── .vscode/         # VS Code integration
└── .github/         # CI/CD workflows
```

## 🔧 VS Code Features

- **Tasks:** Run Godot Project, Run Game, Debug modes
- **Debugging:** Breakpoints, step-through, remote debug
- **Launch configs:** F5 to start debugging sessions

## 📝 License

This project is licensed under the [MIT License](LICENSE).
You are free to use, modify, and distribute this template in your own projects.

---

**💡 Tip:** Star this repo if it helps your workflow! Questions? Open an issue or check the [live demo](https://hubacekjakub.itch.io/godot-quick-start) to see everything working.
