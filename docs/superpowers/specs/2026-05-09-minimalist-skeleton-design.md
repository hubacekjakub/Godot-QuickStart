# Minimalist "Magic Starts Here" Skeleton Design

## Goal
Transform the Godot-QuickStart template from a "ball demo" into a clean, minimalist skeleton upgraded to Godot 4.6.2.

## Architecture
- **Minimalist UI**: The main scene will contain only a `CenterContainer` and a `Label`.
- **Clean Configuration**: Remove all demo-specific input maps, physics layers, and metadata.
- **Project Structure**: Maintain a clean folder hierarchy using `.gitkeep` files for empty directories.

## Tech Stack
- **Engine**: Godot 4.6.2 (Stable)
- **CI/CD**: GitHub Actions (Checkout v6, Upload-Artifact v7, Download-Artifact v8, Cache v5)

## Detailed Changes

### 1. Godot 4.6.2 Upgrade
- Update `project.godot` `config/features` to `4.6.2`.
- Update `GODOT_VERSION` and `GODOT_EXPORT_VERSION` in all `.github/workflows/*.yml` files.
- Bump `ncipollo/release-action` to `v1.20.0`.

### 2. Cleanup & Minimalism
- **Delete Files**:
    - `scenes/Ball.tscn`
    - `scripts/Ball.gd`
    - `scripts/Main.gd`
    - Any associated `.uid` or `.import` files for deleted scripts/scenes.
- **Modify `levels/Main.tscn`**:
    - Remove the `Ball` node and the script attachment.
    - Add a `CenterContainer` covering the full screen.
    - Add a `Label` inside with the text "magic starts here".
- **Clean `project.godot`**:
    - Remove `[layer_names]` section.
    - Remove any custom `[input]` actions.
    - Update `config/name` to "Godot QuickStart".
    - Update `config/description` to "A minimalist Godot 4.6.2 starter template."

### 3. Directory Integrity
- Ensure `.gitkeep` exists in:
    - `assets/fonts/`
    - `assets/sounds/`
    - `assets/textures/`
    - `scripts/` (after `Main.gd` and `Ball.gd` are removed)
    - `scenes/` (after `Ball.tscn` is removed)

### 4. CI/CD Validation
- Update `validation.yml` to remove specific linting paths that no longer exist, ensuring it still validates the project structure and the main level.
