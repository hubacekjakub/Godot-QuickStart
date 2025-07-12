
# Godot QuickStart Template




[![CI Status](https://github.com/hubacekjakub/Godot-QuickStart/actions/workflows/quick-validation.yml/badge.svg)](https://github.com/hubacekjakub/Godot-QuickStart/actions/workflows/quick-validation.yml)
[![GitHub release](https://img.shields.io/github/v/release/hubacekjakub/Godot-QuickStart)](https://github.com/hubacekjakub/Godot-QuickStart/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/hubacekjakub/Godot-QuickStart/blob/main/LICENSE)
[![Godot 4.4+](https://img.shields.io/badge/Godot-4.4%2B-blue)](https://godotengine.org/)
[![Itch.io](https://img.shields.io/badge/itch.io-template-red)](https://itch.io/)

My personal Godot 4 project template for rapid game development. Perfect for game jams and prototypes!

## 🚀 Quick Start

1. **Clone this repository**
2. **Open Godot** and import `project.godot`
3. **Press F5** to run the template
4. **Replace the ball** with your game objects

## 🎮 Controls

- **WASD** or **Arrow Keys** - Move the white ball
- **Escape** - Quit the game

## 🔧 VS Code Tasks & Launch Options

### Available Tasks
Run these from VS Code Command Palette (`Ctrl+Shift+P` → "Tasks: Run Task"):

- **Run Godot Project** - Opens Godot editor
- **Run Game** - Launches the game directly
- **🐛 Debug Godot Project** - Opens editor with debug flags
- **🔍 Run Game with Remote Debug** - Runs game with remote debugging

### Launch Configurations
Available in VS Code Debug panel (`F5`):

- **🐛 Debug GDScript** - Main debugging configuration
- **🎮 Debug Main Scene** - Debug starting from main scene
- **🔗 Attach to Running Godot** - Connect to running Godot instance

### How to Debug
1. Set breakpoints in `.gd` files
2. Press `F5` in VS Code (starts debugger)
3. Launch game with "Run Game with Remote Debug" task
4. Use `F10` (step over), `F11` (step into), `Shift+F11` (step out)

## 🤖 GitHub Actions

Two automated workflows included:

### Quick Validation (`quick-validation.yml`)
- **Triggers**: Every push and pull request
- **Purpose**: Fast syntax and project validation
- **Runtime**: ~2 minutes

### Build & Deploy (`build-and-deploy.yml`)
- **Triggers**: Tags starting with `v` (e.g., `v1.0.0`)
- **Builds**: Windows (.exe), Linux (.x86_64), Web (HTML5)
- **Outputs**:
  - GitHub Release with downloadable builds
  - Web version deployed to GitHub Pages
- **Runtime**: ~10 minutes

### Usage
```bash
# Create a release
git tag v1.0.0
git push origin v1.0.0
# → Triggers automatic build and deployment
```

## 📁 Project Structure

```
├── scenes/          # Game scenes
├── scripts/         # GDScript files
├── assets/          # Fonts, sounds, textures
├── .vscode/         # VS Code configuration
├── .github/         # GitHub Actions workflows
└── builds/          # Export output (auto-generated)
```


## 🎯 What's Included

- **Clean Godot 4.4+ project** with basic ball movement
- **VS Code integration** with debugging and tasks
- **Export presets** for Windows, Linux, and Web
- **GitHub Actions CI/CD** for automatic builds
- **Proper gitignore** and project structure

## 📝 License

This project is licensed under the [MIT License](LICENSE).
You are free to use, modify, and distribute this template in your own projects.
