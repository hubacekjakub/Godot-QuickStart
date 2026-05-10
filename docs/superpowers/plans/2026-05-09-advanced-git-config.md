# Advanced Git Configuration Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Implement professional-grade Git configuration for Godot 4.

**Architecture:** 
- LFS for binaries with locking.
- Text-enforcement for Godot resource formats.
- Clean ignore rules for Godot 4.

**Tech Stack:** Git, Git LFS.

---

### Task 1: `.gitattributes` Overhaul

**Files:**
- Modify: `.gitattributes`

- [ ] **Step 1: Replace `.gitattributes` content**

```gitattributes
# 1. Line Ending Normalization
* text=auto eol=lf

# 2. Godot Text Formats (Mergeable)
*.tscn text
*.tres text
*.gd text
*.gdshader text
*.import text
*.godot text
*.uid text
*.cfg text

# 3. Git LFS - Common Binary Assets (Lockable)
*.png filter=lfs diff=lfs merge=lfs -text lockable
*.jpg filter=lfs diff=lfs merge=lfs -text lockable
*.jpeg filter=lfs diff=lfs merge=lfs -text lockable
*.webp filter=lfs diff=lfs merge=lfs -text lockable
*.ico filter=lfs diff=lfs merge=lfs -text lockable
*.wav filter=lfs diff=lfs merge=lfs -text lockable
*.mp3 filter=lfs diff=lfs merge=lfs -text lockable
*.ogg filter=lfs diff=lfs merge=lfs -text lockable
*.opus filter=lfs diff=lfs merge=lfs -text lockable
*.ttf filter=lfs diff=lfs merge=lfs -text lockable
*.otf filter=lfs diff=lfs merge=lfs -text lockable

# 4. Git LFS - 3D & Heavy Assets (Lockable)
*.fbx filter=lfs diff=lfs merge=lfs -text lockable
*.glb filter=lfs diff=lfs merge=lfs -text lockable
*.gltf filter=lfs diff=lfs merge=lfs -text lockable
*.blend filter=lfs diff=lfs merge=lfs -text lockable
*.obj filter=lfs diff=lfs merge=lfs -text lockable
*.psd filter=lfs diff=lfs merge=lfs -text lockable
*.exr filter=lfs diff=lfs merge=lfs -text lockable
*.hdr filter=lfs diff=lfs merge=lfs -text lockable

# 5. Godot Binary Resources (Lockable)
*.scn filter=lfs diff=lfs merge=lfs -text lockable
*.res filter=lfs diff=lfs merge=lfs -text lockable
*.material filter=lfs diff=lfs merge=lfs -text lockable
*.anim filter=lfs diff=lfs merge=lfs -text lockable
*.mesh filter=lfs diff=lfs merge=lfs -text lockable
*.translation filter=lfs diff=lfs merge=lfs -text lockable
```

- [ ] **Step 2: Commit `.gitattributes`**

```bash
git add .gitattributes
git commit -m "chore: overhaul .gitattributes for LFS and merge safety"
```

### Task 2: `.gitignore` Polish

**Files:**
- Modify: `.gitignore`

- [ ] **Step 1: Replace `.gitignore` content**

```gitignore
# Godot 4+ specific
.godot/

# Godot-specific ignores
*.import
export.cfg
export_presets.cfg.bak

# Imported translations
*.translation

# Mono/C# specific (if added later)
.mono/
bin/
obj/

# Logs
logs/
*.log

# External editor files
.vscode/
.idea/

# OS-specific
.DS_Store
Thumbs.db
```

- [ ] **Step 2: Commit `.gitignore`**

```bash
git add .gitignore
git commit -m "chore: polish .gitignore for Godot 4"
```

### Task 3: Final Verification

- [ ] **Step 1: Verify attributes**
    - Run: `git check-attr -a icon.svg`
    - Expected: `filter: lfs`, `lockable: set` (if it were PNG, but since SVG is text, let's try a dummy png if needed or just verify the file patterns).
- [ ] **Step 2: Final status check**
    - Run: `git status`
