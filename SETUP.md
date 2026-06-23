# Project Setup Guide

This template is designed for **Automated First** development. Follow the first section to get your professional pipeline running in minutes.

---

## 🚀 Basic Setup (The CI/CD Magic)

**This is the only section required to make the template functional.** The core feature of this template is its automated pipeline. Follow these steps to see your game live on itch.io immediately.

### 1. Configure GitHub Secrets
In your GitHub repository, go to **Settings > Secrets and variables > Actions** and add these **Repository secrets**:

| Secret Name | How to get it |
| :--- | :--- |
| `BUTLER_API_KEY` | Generate at [itch.io settings](https://itch.io/user/settings/api-keys) |
| `ITCH_USERNAME` | Your itch.io username |
| `ITCH_GAME_NAME` | The "URL slug" of your game (e.g., `my-game-title`) |

### 2. Trigger Your First Deployment
Push a version tag to trigger the full build and deploy pipeline:
```bash
git tag v1.0.0
git push origin v1.0.0
```
**What happens now?**
1. GitHub Actions validates the project.
2. It builds Windows, Linux, and Web versions.
3. It creates a GitHub Release and **automatically publishes** the Web build to your itch.io page.

---

## 💻 Local Development Setup

If you are a first-time user or having trouble running the project locally, follow these steps to set up your environment.

### 1. Clone & Initialize Git LFS
This project uses Git LFS for binary files. Ensure it is initialized before opening Godot:
1. Click **Use this template** at the top of the GitHub page to create your own repository.
2. **Clone** your new repository.
3. **Install** [Git LFS](https://git-lfs.github.com/).
4. **Run**:
   ```bash
   git lfs install
   git lfs pull
   ```

### 2. Open in Godot
1. Open **Godot 4.6.2**.
2. **Import** the project using the `project.godot` file.
3. Press **F5** to run. You should see "magic starts here" centered on screen.

---

## 🌟 Profi Tips

Advanced workflows for professional game development and team collaboration.

### 🛡️ LFS Locking (Team Coordination)
Since binary files (images, sounds) cannot be merged, use Git LFS locking to prevent team members from editing the same file simultaneously:
- **Lock a file**: `git lfs lock assets/textures/character.png`
- **Unlock a file**: `git lfs unlock assets/textures/character.png`
- **Check locks**: `git lfs locks`

### 🔍 VS Code Integration
Use the included `.vscode` configurations for professional debugging:
- **Tasks**: Run the project or specific builds directly from the command palette (`Ctrl+Shift+P` -> `Tasks: Run Task`).
- **Debugging**: Use **F5** to start a debugging session with breakpoints and variable inspection.

### 🧩 Merge-Safe Scenes
Our Git configuration ensures that `.tscn` and `.tres` files are treated as text. This allows you to diff and merge your scenes and resources just like code, avoiding "binary black box" issues common in other engines.

---

## 🖥️ Platform Notes

- **Windows, Linux, Web** — Fully tested and deployed automatically via CI/CD.
- **macOS** — Export preset is not included. macOS builds require code signing and a Mac runner, which adds complexity beyond this template's scope.

---

## ❓ Troubleshooting

- **"Butler not found"**: Ensure your GitHub Action has the `BUTLER_API_KEY` secret set correctly.
- **LFS Errors**: If textures appear as small text files, run `git lfs pull` to download the actual binaries.
- **Godot Version**: This template is optimized for **Godot 4.6.2**. Using older versions may cause compatibility issues with the export presets.
