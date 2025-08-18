This repo uses Godot 4.x with GDScript. Keep guidance generic and portable so it works across machines and platforms.

Code style
- Use snake_case for variables and functions, PascalCase for classes and enums, and SCREAMING_SNAKE_CASE for constants.
- Use @onready for node references accessed in _ready().
- Prefer explicit typing when beneficial (e.g., `var player: Player`).

Project structure (general)
- Scenes (.tscn)
	- Place level/root scenes in a `levels/` directory.
	- Put reusable/component scenes under `scenes/` (subfolders like `characters/`, `interactables/`, `ui/`, etc.).
- Scripts (.gd)
	- Store gameplay and UI scripts under `scripts/` mirroring the scene layout when practical.
- Assets
	- Keep raw art/audio in `assets/` and commit Godot import sidecars (`*.import`).
- Deprecated
	- Move temporarily unused content to `deprecated/` instead of deleting immediately.

Running locally
- Prefer VS Code tasks to run the project: a task named "Run Godot Project" (editor) and one named "Run Game" (play).
- Avoid committing machine-specific paths; rely on tasks and repo-relative paths.

Repo hygiene
- Ignore the `.godot/` folder and other generated artifacts; keep `export_presets.cfg` under version control to share export settings when applicable.
- Do not hard-code absolute paths in project or settings files.

This repo uses Godot 4.x with GDScript. Keep guidance generic and portable so it works across machines and platforms.

Code style
- Use snake_case for variables and functions, PascalCase for classes and enums, and SCREAMING_SNAKE_CASE for constants.
- Use @onready for node references that need to be accessed in _ready().
- Prefer explicit typing when beneficial, e.g. `var player: Player`.

Code style
- Use snake_case for variables and functions, PascalCase for classes and enums, and SCREAMING_SNAKE_CASE for constants.
- Use @onready for node references accessed in _ready().
- Prefer explicit typing when beneficial (e.g., `var player: Player`).

Project structure (general)
- Scenes (.tscn)
	- Place level/root scenes in a `levels/` directory.
	- Put reusable/component scenes under `scenes/` (subfolders like `characters/`, `interactables/`, `ui/`, etc.).
- Scripts (.gd)
	- Store gameplay and UI scripts under `scripts/` mirroring the scene layout when practical.
- Assets
	- Keep raw art/audio in `assets/` and commit Godot import sidecars (`*.import`).
- Deprecated
	- Move temporarily unused content to `deprecated/` instead of deleting immediately.

Running locally
- Use the VS Code task "Run Godot Project" to open the Godot editor for scene creation.
- Use the VS Code task "Run Game" for quick testing without the editor.

Running locally
- Prefer VS Code tasks to run the project: a task named "Run Godot Project" (editor) and one named "Run Game" (play).
- Avoid committing machine-specific paths; rely on tasks and repo-relative paths.
