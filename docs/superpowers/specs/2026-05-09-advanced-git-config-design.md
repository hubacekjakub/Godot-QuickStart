# Advanced Git Configuration Design Spec

## Goal
Optimize the Godot 4 project's Git configuration for professional team workflows, efficient large asset handling, and robust merge conflict management.

## Architecture
- **Git LFS (Large File Storage)**: Move all binary and heavy assets to LFS.
- **Locking Mechanism**: Enable `lockable` for LFS assets to support team coordination.
- **Merge Safety**: Explicitly treat Godot's text formats (`.tscn`, `.tres`) as text to ensure they remain mergeable.
- **Line Ending Normalization**: Enforce LF line endings across all platforms to prevent "phantom" diffs.

## Detailed Changes

### 1. `.gitattributes` Overhaul
Update the `.gitattributes` file to include:
- **Global Normalization**: `* text=auto eol=lf`.
- **Godot Text Formats**: Ensure `*.tscn`, `*.tres`, `*.gd`, `*.gdshader`, `*.import`, `*.godot`, `*.uid`, `*.cfg` are treated as `text`.
- **Enhanced LFS Rules**:
    - Add `lockable` attribute to all binary patterns.
    - Add Godot-specific binary resources: `*.scn`, `*.res`, `*.material`, `*.anim`, `*.mesh`, `*.translation`.
    - Add modern formats: `*.webp`, `*.glb`, `*.gltf`, `*.blend`.
- **Clean Up**: Remove redundant non-game patterns (e.g., presentation files) to keep it focused.

### 2. `.gitignore` Polish
Review and update `.gitignore` to ensure:
- `.godot/` is ignored (Godot 4 cache).
- Export-related files (except `export_presets.cfg`) are ignored.
- OS-specific junk (e.g., `.DS_Store`, `Thumbs.db`) is covered.

## Success Criteria
- Binary files (like `icon.svg` if it were a PNG, or new textures) are correctly tracked by LFS.
- `git lfs lock` is possible on binary files.
- Scene and resource files are always diffable as text.
- No "modified" status loops due to line ending differences.
