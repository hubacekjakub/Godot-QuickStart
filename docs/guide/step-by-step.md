# Step-by-Step Setup Guide

This guide will take you from a fresh fork to a fully automated game development pipeline.

---

## 1. Initial Project Setup

### Fork and Clone
1. **Fork** this repository on GitHub to your own account.
2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Godot-QuickStart.git
   cd Godot-QuickStart
   ```

### Git LFS Initialization
This project uses Git LFS for binary assets. Ensure it is installed and initialized:
1. [Install Git LFS](https://git-lfs.github.com/) if you haven't already.
2. Initialize LFS in the repository:
   ```bash
   git lfs install
   git lfs pull
   ```

### Opening in Godot
1. Open the **Godot Engine (4.6.2)**.
2. Click **Import** and select the `project.godot` file in your cloned directory.
3. Once the editor opens, press **F5** to run the project. You should see "magic starts here" centered on the screen.

---

## 2. Automated Deployment (itch.io)

This template is pre-configured to build and deploy your game to itch.io automatically using GitHub Actions.

### Step A: Get your itch.io Credentials
1. **Butler API Key**: Go to your [itch.io settings](https://itch.io/user/settings/api-keys) and generate a new API key.
2. **Project Info**: Note your itch.io **username** and the **game-url-name** (e.g., `my-awesome-game`).

### Step B: Configure GitHub Secrets
In your GitHub repository, go to **Settings > Secrets and variables > Actions** and add the following **Repository secrets**:

| Secret Name | Description |
| :--- | :--- |
| `BUTLER_API_KEY` | Your itch.io API key. |
| `ITCH_USERNAME` | Your itch.io username. |
| `ITCH_GAME_NAME` | The URL slug of your game project on itch.io. |

### Step C: Trigger your first Release
To trigger the automated pipeline, simply push a version tag:
```bash
git tag v1.0.0
git push origin v1.0.0
```
GitHub Actions will now:
1. **Validate** your scripts and project structure.
2. **Build** your game for Windows, Linux, and Web.
3. **Release** the files on GitHub.
4. **Deploy** the Web version to your itch.io page.

---

## 3. Professional Workflow Tips

### File Locking (Teams)
Since binary files (images, sounds) cannot be merged, use Git LFS locking to avoid conflicts:
- **Lock a file**: `git lfs lock assets/textures/character.png`
- **Unlock a file**: `git lfs unlock assets/textures/character.png`

### VS Code Integration
If you prefer VS Code for scripting:
1. Open the project folder in VS Code.
2. Ensure the **Godot Tools** extension is installed.
3. Use **F5** to start a debugging session. Breakpoints and variable inspection will work directly in the editor.

### Clean Slate Philosophy
This template is a **Minimalist Skeleton**. 
- **Levels**: Add your levels to the `levels/` folder.
- **Components**: Create modular scenes in the `scenes/` folder.
- **Global Events**: We recommend creating a `GlobalSignalBus.gd` autoload if your project grows complex.
