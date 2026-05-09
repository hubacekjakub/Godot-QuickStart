# Minimalist Skeleton & Godot 4.6.2 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Transform the project into a minimalist "magic starts here" skeleton upgraded to Godot 4.6.2.

**Architecture:** 
- Cleanup demo logic and assets.
- Upgrade engine version across config and CI.
- Simplified main level with a label.

**Tech Stack:** Godot 4.6.2, GitHub Actions.

---

### Task 1: Engine & CI/CD Version Upgrade

**Files:**
- Modify: `project.godot`
- Modify: `.github/workflows/build.yml`
- Modify: `.github/workflows/release.yml`
- Modify: `.github/workflows/validation.yml`

- [ ] **Step 1: Update Godot version in `project.godot`**
    - Replace `config/features=PackedStringArray("4.6.1", "GL Compatibility")` with `config/features=PackedStringArray("4.6.2", "GL Compatibility")`.
- [ ] **Step 2: Update versions in GitHub Actions**
    - In `build.yml`, `release.yml`, and `validation.yml`, update `GODOT_VERSION` to `4.6.2` and `GODOT_EXPORT_VERSION` to `4.6.2-stable`.
    - Bump `ncipollo/release-action` to `v1.20.0` in `release.yml`.
- [ ] **Step 3: Commit version upgrades**
    - Command: `git add project.godot .github/workflows/*.yml && git commit -m "chore: upgrade to Godot 4.6.2 and update CI/CD versions"`

### Task 2: Content Cleanup (Deletion)

**Files:**
- Delete: `scenes/Ball.tscn`
- Delete: `scripts/Ball.gd`
- Delete: `scripts/Ball.gd.uid`
- Delete: `scripts/Main.gd`
- Delete: `scripts/Main.gd.uid`

- [ ] **Step 1: Delete demo files**
    - Command: `rm scenes/Ball.tscn scripts/Ball.gd scripts/Ball.gd.uid scripts/Main.gd scripts/Main.gd.uid`
- [ ] **Step 2: Ensure folder integrity with .gitkeep**
    - Create `scenes/.gitkeep` and `scripts/.gitkeep` if they don't exist.
    - Command: `touch scenes/.gitkeep scripts/.gitkeep`
- [ ] **Step 3: Commit deletions**
    - Command: `git add . && git commit -m "refactor: remove demo scripts and scenes"`

### Task 3: Simplify Main Scene

**Files:**
- Modify: `levels/Main.tscn`

- [ ] **Step 1: Replace Main.tscn content**
    - Replace the entire file content with a minimalist structure: a `Node2D` root (Main), a `CanvasLayer`, a `CenterContainer` (anchors preset: Full Rect), and a `Label` with text "magic starts here".
- [ ] **Step 2: Verify Main.tscn**
    - Check the file content to ensure no references to the deleted script `Main.gd` or `Ball` node remain.
- [ ] **Step 3: Commit scene change**
    - Command: `git add levels/Main.tscn && git commit -m "feat: simplify main level to 'magic starts here' label"`

### Task 4: Project Configuration Cleanup

**Files:**
- Modify: `project.godot`

- [ ] **Step 1: Remove demo-specific settings**
    - Remove the `[layer_names]` section.
    - Update `config/name` to `"Godot QuickStart"`.
    - Update `config/description` to `"A minimalist Godot 4.6.2 starter template."`.
- [ ] **Step 2: Commit config cleanup**
    - Command: `git add project.godot && git commit -m "chore: cleanup project configuration"`

### Task 5: CI/CD Workflow Optimization

**Files:**
- Modify: `.github/workflows/validation.yml`

- [ ] **Step 1: Adjust validation steps**
    - Remove `style-check` job as there are no more scripts to lint.
    - Keep the `validate` job but ensure it doesn't fail due to missing script directories (it should just pass if no scripts are found).
- [ ] **Step 2: Commit workflow changes**
    - Command: `git add .github/workflows/validation.yml && git commit -m "chore: simplify validation workflow"`

### Task 6: Final Verification

- [ ] **Step 1: Run local validation**
    - If godot is available, run `godot --headless --check-only --quit --path .`.
- [ ] **Step 2: Final status check**
    - Command: `git status`
