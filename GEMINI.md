# Godot QuickStart Template

## Project Overview

This is a minimalist starter template for Godot 4.6.2. It is designed to eliminate boilerplate setup and provide a clean, production-ready foundation with automated CI/CD pipelines. The project currently features a "magic starts here" skeleton in its main scene, avoiding any preset game logic or mechanics so developers can start from a truly blank slate.

**Key Technologies:**
- **Engine:** Godot 4.6.2
- **Language:** GDScript
- **CI/CD:** GitHub Actions
- **Platform Deployment:** Automated Web deployment to itch.io, plus Windows and Linux builds.
- **Git Config:** Optimized with Git LFS for binary assets and text-based locking/merging for `.tscn` and `.tres` files.

## Directory Overview

- `levels/`: Contains main game levels (currently houses `Main.tscn` which serves as the entry point).
- `scenes/`: Intended for modular game objects and prefabs.
- `scripts/`: Intended for GDScript logic.
- `assets/`: Contains subdirectories for fonts, sounds, and textures.
- `docs/superpowers/`: Contains design specifications and implementation plans for the project's architecture.
- `.github/workflows/`: Contains the CI/CD configuration files (`main.yml`, `build.yml`, `release.yml`, `validation.yml`).
- `.vscode/`: Contains VS Code integration files for debugging and tasks.

## Building and Running

### Local Development
1. Open the project in the Godot 4.6.2 editor.
2. Press **F5** to run the main scene (`res://levels/Main.tscn`).

### VS Code Integration
The project includes `.vscode` settings. You can use VS Code's integrated debugger and run tasks directly if you have the Godot tools extension installed.

### Automated CI/CD (GitHub Actions)
The project is configured to automatically validate, build, and deploy when a version tag is pushed:

```bash
git tag v1.0.0
git push origin v1.0.0
```

To enable itch.io deployment, the following GitHub Secrets must be configured in your repository:
- `BUTLER_API_KEY`
- `ITCH_USERNAME`
- `ITCH_GAME_NAME`

## Development Conventions

- **Minimalism:** The template enforces a clean slate. New logic and UI components should be built modularly without relying on bulky, monolithic boilerplates.
- **Version Control:** 
  - Git LFS is active for all heavy binary files (e.g., `.png`, `.wav`, `.glb`) and Godot binary resources (`.res`, `.scn`).
  - LFS files are `lockable` to support team workflows (`git lfs lock`).
  - Godot text formats (`.tscn`, `.tres`, `.gd`) are strictly maintained as text files to ensure safe and trackable merge conflict resolution.
- **Continuous Integration:** The `validation.yml` action automatically verifies project integrity using Godot's headless mode on every push/PR.
