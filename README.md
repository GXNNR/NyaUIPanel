# NyaUIPanel V2.5.7

## User Manual & Complete Function Guide

**Creator:** GX2NNR
**Discord:** gx2nnr
**Compatible with:** Adobe After Effects 2020+

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Requirements](#2-requirements)
3. [Installation](#3-installation)
4. [First Launch](#4-first-launch)
5. [Interface Overview](#5-interface-overview)
6. [NyaUI](#6-nyaui)
   * [Auto Folders (Declutter)](#61-auto-folders)
   * [Render Queue (RenderHub)](#62-render-queue)
   * [Easy Precompose](#63-easy-precompose)
   * [True Comp Duplicator](#64-true-comp-duplicator)
   * [Watch Tower](#65-watch-tower)
   * [Mark Cut](#66-mark-cut)
   * [Expression Manager](#67-expression-manager)
   * [Reduce 2X](#68-reduce-2x)
   * [Hide Layer](#69-hide-layer)
   * [Comp Editor (Comp-Mgr)](#610-comp-editor)
   * [Auto Scale 3D](#611-auto-scale-3d)
   * [NyaParallax](#612-nyaparallax)
   * [Modal Dialog Integration](#613-modal-dialog-integration)
7. [NyaPresets](#7-nyapresets)
8. [NyaScripts](#8-nyascripts)
9. [Panel Resizing](#9-panel-resizing)
10. [Persistent User Data](#10-persistent-user-data)
11. [Backup and Migration](#11-backup-and-migration)
12. [Updating the Panel](#12-updating-the-panel)
13. [Troubleshooting](#13-troubleshooting)
14. [Quick Reference](#14-quick-reference)
15. [Recommended Workflow](#15-recommended-workflow)
16. [Safety and Usage Notes](#16-safety-and-usage-notes)
17. [Video Tutorial](#17-video-tutorial)
18. [License](#18-license)
19. [Credits](#19-credits)

---

# 1. Introduction

**NyaUIPanel** is a custom Adobe After Effects ScriptUI panel created by **GX2NNR**.

The panel combines multiple production utilities into one interface, reducing the need to repeatedly open separate scripts or perform repetitive After Effects operations manually.

NyaUIPanel is divided into three main sections:

### NyaUI
Contains the main workflow and production utilities.

### NyaPresets
Provides a searchable personal library for Adobe After Effects `.ffx` animation presets.

### NyaScripts
Provides a searchable personal library for external After Effects scripts such as `.jsx`, `.jsxbin`, and `.js`.

The panel also stores user settings and library data separately from the main panel file.

---

# 2. Requirements

Before installing NyaUIPanel, make sure you have:

* Adobe After Effects 2020 or newer
* A supported operating system for your After Effects installation
* The NyaUIPanel package
* Permission to copy files into the After Effects installation directory

The exact Adobe folder name depends on the version of After Effects installed on your computer.

For example:

```text
Adobe After Effects 2024
Adobe After Effects 2025
Adobe After Effects 2026
```

---

# 3. Installation

## 3.1 Windows Installation

### Step 1 — Open the ScriptUI Panels directory

Navigate to:

```text
C:\Program Files\Adobe\Adobe After Effects 2024\Support Files\Scripts\ScriptUI Panels
```

Replace `Adobe After Effects 2024` with your installed version when necessary.

For example:

```text
C:\Program Files\Adobe\Adobe After Effects 2026\Support Files\Scripts\ScriptUI Panels
```

### Step 2 — Copy the NyaUIPanel file

Copy the NyaUIPanel file into the `ScriptUI Panels` directory.

Example:

```text
NyaUIPanel V2.5.7.jsxbin
```

### Step 3 — Restart After Effects

Close After Effects completely and open it again.

### Step 4 — Open the panel

In After Effects, go to:

**Window → NyaUIPanel V2.5.7**

The panel should now be available as a ScriptUI panel.

---

# 4. First Launch

After opening NyaUIPanel, the main interface contains three tabs:

```text
NyaUI
NyaPresets
NyaScripts
```

The panel stores its libraries and settings separately from the main panel file.

This allows the main panel file to be replaced during an update without normally requiring your preset and script libraries to be recreated.

---

# 5. Interface Overview

## NyaUI

The main production toolbox.

Available functions:

```text
Auto Folders (Declutter)
Render Queue (RenderHub)
Easy Precompose
True Comp Duplicator
Watch Tower
Mark Cut
Expression Manager
Reduce 2X
Hide Layer
Comp Editor (Comp-Mgr)
Auto Scale 3D
NyaParallax
```

## NyaPresets

Preset library and manager for `.ffx` files.

## NyaScripts

Script library and launcher for external After Effects scripts.

The NyaUI section also includes an **UPDATE** button.

---

# 6. NyaUI

NyaUI contains the main After Effects workflow tools.

---

## 6.1 Auto Folders

**Auto Folders** (labeled **DECLUTTER** in the panel) is a project-organization utility.

It automates folder management inside an After Effects project and can also remove unused duplicate imports.

### Opening Auto Folders

From NyaUI, click:

**DECLUTTER**

An **Organization Options** dialog opens.

### Categories

The tool automatically moves project items into named folders at the **project root**:

```text
VIDEO
IMAGE
COMPOSITIONS
AUDIO
PSD
```

Each folder is created only if it does not already exist. Existing folders with the same name at the root are reused.

### Options Dialog

* **All** — when checked, every category is enabled and individual checkboxes are disabled
* Individual category checkboxes (VIDEO, IMAGE, COMPOSITIONS, AUDIO, PSD) — selectively enable only certain categories
* **Remove unused duplicates** — when checked (default), removes FootageItem duplicates of the same file that are **not used** anywhere in the project

### Supported file types

Auto Folders recognizes a large range of extensions per category (video, image, audio, PSD/PSB). Unrecognized extensions are left in place.

### How it works

1. A snapshot of the project items is taken before any change (so item order changes do not require multiple passes).
2. Each item is classified by type (Comp, Footage + extension) and moved to the matching folder.
3. If **Remove unused duplicates** is enabled, duplicate imports of the same file are collapsed: the one currently in use is kept, unused ones are removed.
4. Failed deletions are reported at the end.

### Undo

The whole operation is contained inside a single undo group named:

```text
Organize Project
```

---

## 6.2 Render Queue

The **Render Queue** (labeled **RENDERHUB** in the panel) tool prepares selected compositions for rendering.

### What it does

The function:

1. Starts an After Effects undo group.
2. Removes existing items from the Render Queue.
3. Reads the selected project items.
4. Uses the selected compositions.
5. Reverses the selection order before processing.
6. Adds the compositions to the Render Queue.
7. Asks which naming mode should be used.
8. Requests an output folder.
9. Configures the first output module.
10. Creates PNG output names automatically.
11. Finishes with a completion message.

### Selecting compositions

Before using Render Queue, select the compositions you want to process in the After Effects Project panel.

The tool uses the current **Project panel selection** rather than requiring each composition to be manually added to the Render Queue.

### Custom Name Mode

The tool can ask for a custom name for each selected composition.

Example:

```text
Opening
Fight Scene
Ending
```

Each composition can receive its own custom output name.

### AnimeClips Mode

The alternate naming mode uses a base name.

Example:

```text
Name - S01E1
```

When multiple compositions are selected, the tool automatically generates numbered names such as:

```text
Name - S01E1 (1)
Name - S01E1 (2)
Name - S01E1 (3)
```

### Output Folder

After naming, the tool asks you to select the output folder.

The generated Render Queue items are assigned to that location.

The tool configures the generated output as:

```text
PNG
```

### Important

**Render Queue removes the existing Render Queue items before adding the selected compositions.**

Do not use this function while relying on unrelated items already waiting in the Render Queue.

---

## 6.3 Easy Precompose

**Easy Precompose** (labeled **PRECOMP** in the panel) is a streamlined precomposition utility.

It reduces the number of manual steps normally required when creating a precomposition.

Use it when you want to perform the panel's predefined precompose workflow from a single button.

The panel-level **Move attributes ON/OFF** checkbox (bottom of the NyaUI tab) controls whether the precompose moves layer attributes into the new composition.

---

## 6.4 True Comp Duplicator

**True Comp Duplicator** (labeled **COMP-2X** in the panel) is a third-party composition duplication script integrated into NyaUIPanel.

The original script was created by **Brennan Chapman**.

NyaUIPanel does not claim authorship or ownership of the original True Comp Duplicator code.

The third-party source is integrated without modification. NyaUIPanel provides an interface-level integration that allows the functionality to be accessed from the NyaUI interface.

**True Comp Duplicator is not covered by the NyaUIPanel license.**

It remains subject to its own license and terms.

For licensing and source information, refer to the original True Comp Duplicator distribution:

https://aescripts.com/true-comp-duplicator/

---

## 6.5 Watch Tower

**Watch Tower** (labeled **WATCHTOWER** in the panel) is a **folder mirror engine** for After Effects.

It keeps selected disk folders and your After Effects project in sync, in both directions:

* Files that appear on disk are imported automatically.
* Files that disappear from disk are removed from the project (with safety checks).
* Items that are still in use but whose source files are gone are flagged in red instead of being removed.

Watch Tower uses a **mirror** model: the folder on disk is the source of truth. There is no separate snapshot or database file that can get out of sync.

### 6.5.1 Opening Watch Tower

From NyaUI, click:

**WATCHTOWER**

A resizable Watch Tower window opens. If the window is already open, clicking the button re-focuses it instead of opening a duplicate.

Watch Tower can also run in the background: the scheduler persists even if the panel is closed, until you explicitly turn it OFF.

### 6.5.2 Interface

The Watch Tower window contains:

* **SELECT FOLDER** — replace the currently selected watched folder
* **+** — add a new watched folder to the list
* **OFF / ON** — two-segment toggle; the active segment is highlighted
* **Folder list** — all saved folders; folders that no longer exist are shown with `[missing]` prefix
* **OPEN FOLDER IN EXPLORER** — opens the selected folder in the OS file browser
* **IMPORT FILES** — forces an immediate scan of the selected folder (ignores cache/stability checks)
* **REMOVE PATH** — stops watching the selected folder (does not remove already imported items from the project)
* **Status line** — live status summary (see 6.5.6)

### 6.5.3 Auto-sync modes

Watch Tower has two operating states:

* **OFF** — the scheduler is not running. No background scanning, no auto-imports, no auto-removals. Manual actions (IMPORT FILES, +, SELECT FOLDER) still work but no periodic check happens.
* **ON** — the scheduler fires a scan every `interval` seconds (default 4s, range 2–60s). Newly found files are imported; missing files trigger removal logic with safety checks.

The OFF/ON state is persisted in `NyaWatchTower.json`. When you reopen the panel, if Watch Tower was ON, it resumes automatically.

### 6.5.4 Mirror behavior

For each watched folder:

* **New files → imported** into the After Effects project, inside folder items tagged `NWT:<path>` that mirror the disk hierarchy.
* **Image sequences → merged**: three or more numerically numbered files with the same prefix and extension are imported as a single sequence entry (requires AE to recognize them as a sequence).
* **Deleted files → removed** from the project, but only if:
  1. The file is confirmed gone from disk (not just unreadable for a moment).
  2. The item is not currently in use in any composition (if it is, its label is set to red and it is **kept**, never deleted automatically).
  3. A safety confirmation is accepted, if the deletion batch is large (10+ items, or more than 50% of tracked items).
  4. Any prior "no" answer for the same batch is respected within the current session.

### 6.5.5 Safety features

* **Stability check** — new files are only imported if they are at least 8 seconds old (or `interval * 2`, whichever is larger). This avoids importing half-copied files.
* **Batch import limit** — at most 150 files are imported per cycle. Additional files wait for the next scan, keeping After Effects responsive.
* **In-use protection** — items still used in a composition are flagged but never removed automatically.
* **Declined cache** — if you answer **No** to a large-deletion confirmation, Watch Tower remembers and does not re-ask for the same batch during the session.
* **Scheduler pause on modal dialogs** — see [6.13 Modal Dialog Integration](#613-modal-dialog-integration).
* **Rendering protection** — Watch Tower skips the scheduled scan while the Render Queue is actively rendering.

### 6.5.6 Status counters

The status line shows a compact summary:

```text
Watching | 3 missing | 12 waiting | 2 removals on hold | 5 in use (red) | 1 failed | last 14:32:10  +3 / -1
```

* **missing** — watched folders that cannot be accessed
* **waiting** — new files that are still too fresh to be imported
* **removals on hold** — items pending confirmation for a large deletion batch
* **in use (red)** — items whose source file is gone but which are still referenced by a composition
* **failed** — imports that failed (see log)
* **last +N / -M** — cumulative added / removed counts from the last scan

### 6.5.7 Configuration files

Config and log live in:

```text
Documents\SYNC\NyaWatchTower.json
Documents\SYNC\NyaWatchTower.log
```

The JSON file stores the watched folder list, the currently selected index, the OFF/ON state, and the scan interval.

### 6.5.8 Migration from older versions

If a `NyaWatchTower.json` is not present, Watch Tower looks for the legacy files:

```text
Documents\SYNC\path1.json ... path10.json
Documents\SYNC\lastUsedPath.json
```

and migrates the folder list from them. The old files are **not deleted** — they are left in place in case you need them.

### 6.5.9 Removal from disk vs. removal from project

* **Removing a path** from Watch Tower stops watching the folder but does **not** delete anything from the After Effects project.
* **Deleting a file from disk** (outside AE) triggers the mirror removal on the next scan, subject to the safety checks in 6.5.5.

---

## 6.6 Mark Cut

**Mark Cut** (labeled **MARKCUT** in the panel) automatically splits layers at composition markers.

This is useful when composition markers are being used as edit points.

### Basic workflow

1. Open the composition you want to process.
2. Place composition markers where cuts should occur.
3. Make the composition active.
4. Click **MARKCUT**.

The script reads the composition's marker times.

The marker positions are sorted before processing.

The marker positions are then used as layer split points.

### Final cut

The composition duration is also added as a final cut position.

This allows the composition's end boundary to be processed as part of the operation.

### Undo

The operation is contained inside an After Effects undo group named:

```text
Cut at Markers
```

The complete operation can therefore be reverted using After Effects' normal Undo command.

---

## 6.7 Expression Manager

**Expression Manager** (labeled **X-PRESER** in the panel) is an expression library and management tool.

It allows expressions to be extracted, stored, navigated, enabled or disabled, loaded, and applied.

When opened, the tool creates or uses:

```text
Documents\Expressions
```

### Opening Expression Manager

From NyaUI:

**X-PRESER**

A separate resizable Expression Manager window opens.

### Expression display

The interface includes a counter showing the current position in the expression collection.

Example:

```text
1/5
```

This means the first expression of five stored entries is currently selected.

### Extract Expression

**Extract Expression** reads expressions from selected layers.

Stored information includes:

* Composition name
* Layer index
* Property path
* Expression text

### Expression navigation

The manager includes:

**Previous** — Moves to the previous stored expression.

**Next** — Moves to the next stored expression.

**Play / Toggle** — Controls whether the current expression is enabled.

**Delete All** — Removes the stored expression entries managed by the tool.

### Load from Folder

The manager can load expression files from the Expressions folder.

This allows previously saved expressions to be reused.

Favorites are stored in:

```text
Documents\SYNC\NyaXPreserFavorites.json
```

### Apply Expression

**Apply Expression** attempts to place the current expression onto the intended After Effects property.

The manager first attempts to use the original property associated with the stored expression.

If the original property cannot be used as expected, it can attempt a fallback using currently selected properties.

### Upload File

**Upload File (.txt)** allows a text file containing an expression to be loaded into the manager.

### Save Expression

Expression text can be saved to:

```text
Documents\Expressions
```

### Expressions Folder

The **Expressions Folder** button opens the folder used by Expression Manager.

---

## 6.8 Reduce 2X

**Reduce 2X** (labeled **REDUCE-2X** in the panel) creates a reduced copy of the current project.

The tool saves the project and creates a separate reduced version without requiring the user to manually perform the complete process.

### Project handling

The tool:

1. Saves the current project.
2. Reads the current project file.
3. Determines the relevant selected project item or composition.
4. Creates a dedicated output folder based on the project and composition.
5. Creates a reduced project file.
6. Uses After Effects' project-reduction command.
7. Opens the appropriate project based on the user's choice.

The generated folder follows the pattern:

```text
<ProjectName>_<CompName>
```

### Important

Because this operation can change the project context and open another `.aep`, save your work before using it.

The function itself also saves the project before continuing.

---

## 6.9 Hide Layer

**Hide Layer** (labeled **HIDELAYER** in the panel) allows layers to be managed according to their After Effects label color.

The tool uses the label color of the first selected layer as the reference color.

### Opening Hide Layer

From NyaUI:

**HIDELAYER**

The tool opens a window titled:

```text
NyaHideColorLayer
```

### Available actions

#### HIDE LAYERS (SAME COLOR)

Targets layers using the same label color as the selected reference layer.

#### HIDE LAYERS (ARE NOT THIS COLOR)

Targets layers whose label color is different from the selected reference color.

#### SHOW ALL

Restores all layers to a visible/non-shy state.

### Hide Visibility

The:

```text
HIDE VISIBILITY
```

checkbox determines whether the tool changes normal layer visibility.

When enabled, affected layers can be disabled through their `enabled` state.

### Enable Shy

The:

```text
ENABLE SHY
```

checkbox controls the After Effects Shy property for affected layers.

The tool can therefore be used for visibility management, Shy management, or both.

### Show All behavior

**SHOW ALL** enables every layer and disables Shy for every layer in the active composition.

### Settings storage

Hide Layer stores its checkbox settings in:

```text
Documents\SYNC\NyaHCLSettings.json
```

The `SYNC` folder is created automatically when needed.

---

## 6.10 Comp Editor

**Comp Editor** (labeled **COMP-MGR** in the panel) is a composition-management utility with careful handling of transforms, parenting, keyframes, cameras and precompositions.

It provides three primary operations — Change Resolution, Change Duration, Change FPS — plus three 3D helper buttons.

### Opening Comp Editor

From NyaUI:

**COMP-MGR**

A resizable **NyaCompManager V2.1** window opens. If it is already open, clicking the button re-focuses the existing window.

### 6.10.1 Change Resolution

Click **CHANGE RESOLUTION** and enter a width and height. Only comps that pass validation are touched — if any nested comp would exceed After Effects' 30000-pixel limit, the entire operation aborts before any change is made.

Behavior:

* The active composition is resized to the new width/height.
* Layer transforms are adjusted so **content is scaled to fit** (uniform scale, `min(sx, sy)`).
* **Position, Scale, Anchor Point** are mapped — including all their keyframes and their **spatial tangents** — so animations are preserved.
* **Parenting is respected**: a layer that is parented to another layer already scaled by its parent will not be scaled twice.
* **Cameras and lights** are adjusted so their framing is preserved: `zoom`, `focusDistance`, `aperture` (cameras) and `falloffDistance`, `radius` (lights) are all updated.
* **Shared precomps are detected and left untouched** — a precomp that is also used outside the current hierarchy is treated as plain footage and not resized, preventing it from breaking unrelated compositions.
* **Layers showing precomps that get resized** have their Anchor Point adjusted to follow the new center.
* **Locked layers are still processed** (their transforms are updated) but their `locked` state is never changed.

Behavior on AE's automatic adjustments: After Effects may reposition or rescale layers showing precomps when the source comp is resized. Comp Editor snapshots those layers before resizing and restores the original values before applying its own transformation, so the final result is fully predictable.

The **Change nested compositions** checkbox controls recursion into nested precomps.

### 6.10.2 Change Duration

Click **CHANGE DURATION** and enter a duration. Accepted formats:

```text
90          (seconds)
90.5        (seconds with decimal)
1:30        (MM:SS)
1:30:00     (HH:MM:SS)
1:30,5      (decimal with comma)
240f        (frames — uses comp.frameRate)
```

Behavior:

* The active composition duration is changed to the new value.
* **Layers whose outPoint reaches the old end** are extended (or truncated) to the new end.
* Layers with their own timing (e.g. a 2-second intro in a 30-second comp) are **left untouched** in their timing — you keep your creative timing.
* **Locked layers are skipped**, never unlocked.
* The `outPoint` of footage layers is clamped to the source duration if needed (no more `Value out of range` errors).
* **Work area** is scaled proportionally if it covered the whole comp; otherwise only trimmed if it extends past the new end.

The **Change nested compositions** checkbox controls recursion into nested precomps.

### 6.10.3 Change FPS

Click **CHANGE FPS** and enter a frame rate (e.g. `23.976`, `29.97`, `30`, `60`).

Behavior:

* The active composition frame rate is changed to the new value.
* **Keyframes are re-timed to the new grid**: an animation that visually lasted 1 second at 24 fps still lasts 1 second at 30 fps, and its keys snap to exact frame positions of the new grid.
* **Easing, temporal continuity, auto-bezier and spatial tangents are preserved** when keys are re-timed.
* **Expressions containing `time` or `frame`** are detected and reported (their behavior may change when fps changes — review those expressions manually).
* The comp duration is re-rounded to the nearest frame at the new fps.
* **Locked layers are skipped**, never unlocked.
* **Markers are re-timed** along with the keyframes when duration is scaled.

The **Change nested compositions** checkbox controls recursion into nested precomps.

### 6.10.4 Validation and safety

All three operations share the same safety guarantees:

* **Pre-validation** — all target comps are validated (max 30000 px, max 999 fps, max 3 hours) before any change is applied.
* **Undo group always closed** — even if an error occurs mid-operation, `EndUndoGroup` is guaranteed. A single Ctrl+Z reverts the whole operation.
* **Locked layers are skipped** (not unlocked).
* **Shared precomps are excluded** from recursive operations.
* **Failed items are counted** and reported at the end with a summary alert.

### 6.10.5 Auto Scale 3D and NyaParallax

These two buttons behave exactly as before and are **not** affected by the resolution/duration/fps changes:

* **TOGGLE AUTO SCALE 3D** — toggles the auto-scale expression on selected 3D layers.
* **NYAPARALLAX** — prepares a camera-based 3D parallax setup on selected layers (activates 3D, applies scale expression, assigns Z positions, creates a Camera Controller null parent for the active camera).

Both use the same "no camera" alert if no CameraLayer exists in the active comp.

### 6.10.6 Version

The current Comp Editor is **NyaCompManager V2.1**.

---

## 6.11 Auto Scale 3D

**Auto Scale 3D** is an After Effects expression-based scaling system.

It provides controls to:

* Enable the scale expression
* Disable the scale expression
* Apply the scale expression

The expression uses the active camera's zoom and the layer's Z position.

The system compensates the layer scale according to its distance from the camera.

This is useful when building camera-based 3D scenes where layers move along the Z axis.

---

## 6.12 NyaParallax

**NyaParallax** is a preparation tool for camera-based 3D parallax.

When triggered, it performs the following workflow:

1. Activates 3D.
2. Applies the automatic scale expression.
3. Assigns Z positions.
4. Creates a camera controller.
5. Parents the camera to the controller.

### Default Z position

The system uses:

```text
2500
```

as the default Z value when assigning depth.

### Camera Controller

The script creates a 3D null named:

```text
Camera Controller
```

The camera is then parented to that controller.

This provides a central control layer for moving the camera setup.

### Completion message

When the operation finishes, the tool displays:

```text
Parallax Complete.
```

---

## 6.13 Modal Dialog Integration

NyaUIPanel V2.5.7 introduces automatic Watch Tower pause during native modal dialogs.

### The problem

After Effects does not allow ExtendScript to run while a native modal dialog (`alert`, `confirm`, `prompt`, `Folder.selectDialog`, `File.openDialog`, `File.saveDialog`, `Window.show()` on a `"dialog"` window) is open.

If Watch Tower's scheduler fires in that moment, After Effects shows an error.

### The fix

All NyaUIPanel features that need to open a native dialog now route through dedicated wrappers:

* `nyaAlert(...)` — pauses Watch Tower, calls `alert`, resumes
* `nyaConfirm(...)` — same for `confirm`
* `nyaPrompt(...)` — same for `prompt`
* `nyaDlg(obj, method, ...)` — same for `Folder.selectDialog` / `File.openDialog` / `File.saveDialog`
* `nyaShow(window)` — same for `Window.show()`

The pause uses a reference counter, so nested dialogs work correctly. Watch Tower is only paused while at least one modal dialog is open. When the last dialog closes, the scheduler resumes automatically if Watch Tower was in ON state.

### What this means for you

* **No more "script cannot run while a modal dialog is open" errors** when Watch Tower is active and you click a button that opens a dialog.
* The behavior is transparent — no visible difference in NyaUIPanel's UI.
* The pause is only applied to the Watch Tower scheduler; it does not affect any other background task.

---

# 7. NyaPresets

**NyaPresets** is a preset-management system for Adobe After Effects `.ffx` files.

It allows users to build a personal searchable preset library.

Available categories include:

```text
VFX
Color
Audio
Text
Motion
Other
```

---

## 7.1 Adding Presets

Click:

**Add Preset**

You can select one or multiple `.ffx` files.

During the process you can assign:

* Category
* Description

The presets are then added to the library.

---

## 7.2 Applying Presets

Select a preset and click:

**Apply**

A preset can also be applied by double-clicking it in the list.

---

## 7.3 Searching Presets

The search field filters the preset library while typing.

Use the **X** control to clear the search.

The category dropdown provides an additional filter.

For example:

```text
Motion
```

displays presets assigned to the Motion category.

Search and category filtering can therefore be combined.

---

## 7.4 Editing Presets

### Edit Name

Allows the selected preset's information to be edited.

The editing interface can modify:

* Name
* Category
* Description

### Delete Preset

Removes selected preset entries from the library.

Multiple entries can be selected for removal.

### Refresh

Reloads the preset library.

A successful reload displays:

```text
Library reloaded
```

---

## 7.5 NyaPresets Settings

The settings system includes library-management features such as:

**Export** — Exports the current preset library.

**Import** — Imports a previously saved library.

This is useful for backups or transferring your preset database to another system.

Both Export and Import use UTF-8 encoding so libraries containing non-ASCII characters transfer correctly.

---

## 7.6 NyaPresets Storage

The preset system stores its library under:

```text
Documents\NyaPresets\library.json
Documents\NyaPresets\categories.json
```

The folder is created automatically on first launch.

If `Documents\NyaPresets` cannot be created for permission reasons, the panel falls back to `Folder.userData\NyaPresets`.

Older versions used `Folder.userData\NyaPresets` only. On first launch of V2.5.7, the library is migrated automatically from the legacy location to `Documents\NyaPresets` (the legacy file is kept).

---

# 8. NyaScripts

**NyaScripts** is a personal script launcher.

It allows After Effects scripts to be registered once and executed later from the NyaUIPanel interface.

Supported file types include:

```text
.jsx
.jsxbin
.js
```

---

## 8.1 Adding Scripts

Click:

**Add Script**

Select the script you want to register.

NyaScripts automatically creates an alias based on the filename.

Example:

```text
MyTool.jsx
```

becomes:

```text
MyTool
```

The extension is removed from the displayed alias.

The system also checks for duplicate file paths.

---

## 8.2 Running Scripts

A stored script can be executed directly from the NyaScripts list.

Double-clicking a script launches it.

Before execution, NyaScripts validates that the referenced file still exists.

---

## 8.3 Script Execution Modes

NyaScripts supports two execution approaches.

### Standard Mode

The script file is evaluated directly using After Effects' scripting environment.

This is handled through:

```text
$.evalFile
```

### Dockable Panels Mode

When Dockable Panels mode is enabled, NyaScripts attempts to execute the script through an After Effects menu command.

This uses:

```text
app.findMenuCommandId()
```

and:

```text
app.executeCommand()
```

This mode is intended for scripts that behave as After Effects panels or menu-based tools.

---

## 8.4 Keeping Script Interfaces Alive

When a script creates a persistent UI, NyaScripts can keep the returned interface alive using:

```text
$.global.__nyaScriptsKeptAlive
```

This helps prevent certain script-generated interfaces from being immediately destroyed after execution.

---

## 8.5 Searching Scripts

The search field filters the library using the stored script aliases.

The list updates as the search text changes.

Use the **X** button to clear the filter.

---

## 8.6 Renaming Scripts

**Edit Name** changes the alias shown inside NyaScripts.

It does not rename the actual `.jsx`, `.jsxbin`, or `.js` file.

Example:

Actual file:

```text
D:\AfterEffects\Scripts\Example.jsx
```

Displayed alias:

```text
My Animation Tool
```

The file remains:

```text
Example.jsx
```

---

## 8.7 Deleting Scripts

**Delete Script** removes the script entry from the NyaScripts library.

This is a library operation.

It does not physically delete the original script file from your computer.

---

## 8.8 Refreshing NyaScripts

Click:

**Refresh**

to reload the saved script library.

This is useful after modifying the library or when you want to force the UI to reload its stored data.

---

## 8.9 Exporting the Script Library

NyaScripts can export its script list using the:

```text
.qsl
```

format.

The exported file stores the library information so it can be imported later.

---

## 8.10 Importing the Script Library

Importing a `.qsl` library allows a previously exported script collection to be restored.

The import process asks for confirmation before replacing the current list.

This prevents accidental replacement of the current script library.

---

## 8.11 Delete All Scripts

NyaScripts includes a **Delete All Scripts** operation.

Because this affects the entire stored script list, the tool displays a confirmation dialog before deleting the entries.

---

## 8.12 NyaScripts Storage

NyaScripts stores its information under:

```text
Documents\NyaScripts\
```

The main files include:

```text
AfterEffectsScripts.txt
AfterEffectsScripts_backup.txt
NyaScriptsSettings.txt
NyaScripts_errors.log
```

### AfterEffectsScripts.txt
Stores the script library.

### AfterEffectsScripts_backup.txt
Used as a backup of the script library data.

### NyaScriptsSettings.txt
Stores persistent settings such as execution mode.

### NyaScripts_errors.log
Stores error information generated by the script system.

If `Documents\NyaScripts` cannot be created for permission reasons, the panel falls back to `Folder.userData\NyaScripts`. Legacy files are migrated automatically on first launch.

---

# 9. Panel Resizing

NyaUIPanel is resizable.

When the available panel width becomes too small, the NyaUI button layout automatically changes orientation.

This allows the controls to adapt to different panel sizes and dock positions.

The panel can be used:

* As a floating panel
* As a docked After Effects panel
* In a narrow workspace
* In a wider custom workspace

---

# 10. Persistent User Data

NyaUIPanel separates its executable panel from several user-data locations.

Personal libraries and settings are not intended to be stored inside the After Effects `ScriptUI Panels` installation folder.

Known storage locations include:

### Expressions

```text
Documents\Expressions
```

### X-PRESER favorites

```text
Documents\SYNC\NyaXPreserFavorites.json
```

### Hide Layer

```text
Documents\SYNC\NyaHCLSettings.json
```

### Watch Tower

```text
Documents\SYNC\NyaWatchTower.json
Documents\SYNC\NyaWatchTower.log
```

### NyaPresets

```text
Documents\NyaPresets\library.json
Documents\NyaPresets\categories.json
```

(fallback: `Folder.userData\NyaPresets`)

### NyaScripts

```text
Documents\NyaScripts\
```

with:

```text
AfterEffectsScripts.txt
AfterEffectsScripts_backup.txt
NyaScriptsSettings.txt
NyaScripts_errors.log
```

(fallback: `Folder.userData\NyaScripts`)

---

# 11. Backup and Migration

Before reinstalling After Effects, moving to another computer, or performing a major system migration, create backups of your personal NyaUIPanel data.

Important data includes:

```text
Documents\Expressions
```

```text
Documents\SYNC
```

(this single folder contains X-PRESER favorites, Hide Layer settings, and all Watch Tower configuration and logs)

```text
Documents\NyaPresets
```

(or `Folder.userData\NyaPresets` if Documents is not writable)

```text
Documents\NyaScripts
```

(or `Folder.userData\NyaScripts` if Documents is not writable)

If you maintain a large preset or script library, use the built-in **Import / Export** functions whenever practical.

---

# 12. Updating the Panel

The NyaUI footer contains an:

```text
UPDATE
```

button.

The button opens the current NyaUIPanel update/download location.

Current update location:

https://drive.google.com/drive/folders/1RY5AVB7WREy8Iq3WeXNmjxkkGnneyMGl?usp=sharing

## Recommended update procedure

1. Close After Effects.
2. Keep a backup of your current panel file.
3. Install the new NyaUIPanel version in the same `ScriptUI Panels` directory.
4. Start After Effects again.
5. Open NyaUIPanel through the **Window** menu.

Your libraries are stored separately from the main panel file and are designed to remain available when the panel is updated.

---

# 13. Troubleshooting

## NyaUIPanel does not appear in the Window menu

Check the following:

* The file is inside `Scripts\ScriptUI Panels`.
* The file is compatible with the installed After Effects version.
* After Effects was restarted after installation.
* The filename and extension are correct.

---

## A NyaUI function does nothing

Many NyaUI functions depend on the current After Effects context.

Depending on the tool, this may include:

* An active composition
* Selected layers
* Selected project items
* Composition markers
* A camera
* 3D layers

Make sure the required project elements are selected before running the operation.

---

## Render Queue gives unexpected results

Remember that **Render Queue clears the existing Render Queue items before adding the selected compositions**.

Also verify that the correct compositions are selected in the Project panel.

---

## Mark Cut does nothing

Check that:

1. A composition is active.
2. The composition contains markers.
3. The layers you want to process are present.

The tool relies on composition marker positions as cut points.

---

## Hide Layer does not behave as expected

Make sure:

* A composition is active.
* At least one layer is selected.
* The selected layer has the label color you want to use as the reference.

The first selected layer determines the reference color.

---

## Watch Tower is not importing new files

Check:

1. The OFF/ON toggle is set to **ON**.
2. The watched folder is selected in the list (not the `[missing]` prefix).
3. The new files are **at least 8 seconds old** — Watch Tower waits before importing to avoid half-copied files.
4. The status line shows **waiting** but nothing else — this is normal while files are still "young".
5. If the status shows **failed**, open `Documents\SYNC\NyaWatchTower.log` to see the exact error.

You can also click **IMPORT FILES** to force an immediate scan that bypasses the stability check.

---

## Watch Tower asks to remove files repeatedly

Watch Tower asks a "large deletion" confirmation only when 10+ items or more than 50% of the tracked items would be removed. If you answered **No**, it will not ask again during the same session for the same batch (the exact signature is remembered).

If you answered **Yes** and items were still not removed, they were probably **in use** in a composition. Those are flagged in red (`label = 1`) but never removed automatically — review them manually.

---

## Watch Tower shows "script cannot run while a modal dialog is open"

This error should not happen in V2.5.7 or later. All NyaUIPanel features that open native dialogs route through the `nya*` wrappers, which pause Watch Tower's scheduler while the dialog is open.

If you still see this error:

1. Confirm you are running V2.5.7 or later.
2. Confirm no external script is opening a native dialog without using the wrappers.
3. Check `NyaWatchTower.log` for the exact timestamp.

---

## Comp Editor: "Change Resolution" does not seem to scale content

Make sure you are running V2.5.7. Older versions only moved layers to the center without scaling them. The current Comp Editor scales content properly, respecting parenting, keyframes, spatial tangents, and shared precomps.

If shared precomps are being left alone when you expected them to scale, this is by design — a precomp that is also used outside the current hierarchy is left untouched to prevent breaking unrelated compositions.

---

## Comp Editor: "Change Duration" does not extend a layer

By design, Change Duration only extends layers whose `outPoint` already reached the previous comp duration. Layers with their own shorter timing (intros, stingers, overlays) are left alone so your creative timing is preserved.

If you want every layer scaled proportionally, this is not exposed in the current UI — use a proportional retime approach manually or contact the author.

---

## Comp Editor: "Change FPS" changes my animation timing

By design, Change FPS keeps the animation in **seconds** and snaps keyframes to the new frame grid. If you were thinking in frames (e.g. "this is a 12-frame animation"), the visual duration will be preserved but the frame count will change. To keep frame numbers instead, this requires manual adjustment or direct script access.

---

## A preset cannot be applied

Check whether the original `.ffx` file still exists at its stored location.

Then use:

**NyaPresets → Refresh**

If the original preset has been moved manually, its stored library entry may no longer point to the correct file.

---

## A script cannot be executed

Verify:

* The script file still exists.
* Its extension is `.jsx`, `.jsxbin`, or `.js`.
* The stored file path is correct.
* The script is compatible with your After Effects version.

Then use:

**NyaScripts → Refresh**

For additional information, inspect:

```text
Documents\NyaScripts\NyaScripts_errors.log
```

(or `Folder.userData\NyaScripts\NyaScripts_errors.log` if Documents is not writable)

---

# 14. Quick Reference

| Section    | Tool                 | Main Purpose                                                                 |
| ---------- | -------------------- | ---------------------------------------------------------------------------- |
| NyaUI      | Auto Folders (DECLUTTER) | Project organization + removal of unused duplicate imports               |
| NyaUI      | Render Queue (RENDERHUB) | Add selected compositions to the Render Queue and automatically name outputs |
| NyaUI      | Easy Precompose (PRECOMP) | Streamline precomposition                                              |
| NyaUI      | True Comp Duplicator (COMP-2X) | Third-party composition duplication integration                    |
| NyaUI      | Watch Tower          | Mirror disk folders into AE with auto-import and safe auto-removal           |
| NyaUI      | Mark Cut (MARKCUT)   | Split layers at composition markers                                          |
| NyaUI      | Expression Manager (X-PRESER) | Extract, save, load, and apply expressions                          |
| NyaUI      | Reduce 2X (REDUCE-2X) | Create a reduced project copy                                              |
| NyaUI      | Hide Layer (HIDELAYER) | Manage visibility/Shy using label colors                                  |
| NyaUI      | Comp Editor (COMP-MGR) | Modify composition settings (resolution, duration, fps) with full safety  |
| NyaUI      | Auto Scale 3D        | Maintain scale based on camera/depth                                         |
| NyaUI      | NyaParallax          | Prepare camera-based 3D parallax                                             |
| NyaPresets | Add Preset           | Add `.ffx` files                                                             |
| NyaPresets | Apply                | Apply stored presets                                                         |
| NyaPresets | Search               | Find presets                                                                 |
| NyaPresets | Edit Name            | Edit preset information                                                      |
| NyaPresets | Delete               | Remove preset entries                                                        |
| NyaPresets | Import/Export        | Back up and transfer preset libraries                                        |
| NyaScripts | Add Script           | Add scripts to the library                                                   |
| NyaScripts | Run                  | Execute registered scripts                                                   |
| NyaScripts | Search               | Find scripts                                                                 |
| NyaScripts | Edit Name            | Rename aliases                                                               |
| NyaScripts | Delete Script        | Remove library entries                                                       |
| NyaScripts | Import/Export        | Back up and transfer script libraries                                        |
| NyaScripts | Settings             | Configure execution behavior                                                 |

---

# 15. Recommended Workflow

A typical NyaUIPanel workflow can look like this:

### Project Preparation

Use:

**NyaUI → DECLUTTER**

to organize the project and remove unused duplicate imports.

### Composition Preparation

Use:

**COMP-MGR**

to adjust:

* Resolution (with proper scaling of content and parenting)
* Duration (with optional extension of layers that reach the end)
* FPS (with proper keyframe retiming)

### 3D Setup

Use:

**NYAPARALLAX**

when a camera-based depth setup is required.

### Repetitive Expression Work

Use:

**X-PRESER**

to save and reuse expressions.

### Repetitive Effects

Use:

**NyaPresets**

to keep frequently used `.ffx` presets organized.

### External Tools

Use:

**NyaScripts**

to keep frequently used scripts accessible from the same panel.

### Disk-to-Project Sync

Use:

**WATCHTOWER**

when you want a folder on disk to be mirrored into your AE project automatically (imports new files, removes gone files safely).

### Final Rendering Preparation

Use:

**RENDERHUB**

to batch selected compositions into the Render Queue and automatically organize their output names.

### Marker-Based Cutting

Use:

**MARKCUT**

when composition markers define your edit points.

---

# 16. Safety and Usage Notes

NyaUIPanel automates operations that can affect compositions, layers, project files, expressions, and the Render Queue.

For that reason:

* Save important projects before large automated operations.
* Verify your selection before using tools that operate on selected items.
* Be aware that Render Queue clears existing queue items.
* Be aware that Watch Tower, when ON, will import and (with confirmation) remove items from the project to mirror the disk.
* Be aware that Comp Editor's Change Resolution will scale layer content, not just center it.
* Keep backups of your personal libraries.
* Do not modify or redistribute the original NyaUIPanel components except as permitted by the included license.
* Third-party components remain subject to their own licenses and terms.

---

# 17. Video Tutorial

Video tutorial:

https://youtu.be/6tYuLW5nhQA

The tutorial provides a visual introduction to NyaUIPanel and demonstrates its workflow.

---

# 18. License

NyaUIPanel is proprietary software created by **GX2NNR**.

The included license applies to the original components created by GX2NNR.

Third-party software and resources are not covered by the NyaUIPanel license and remain subject to their respective licenses and terms.

For complete licensing information, see the included:

```text
LICENSE
```

file.

---

# 19. Credits

## NyaUIPanel

Created by:

**GX2NNR**

Discord:

**gx2nnr**

Compatible with:

**Adobe After Effects 2020+**

## Third-Party Component

**True Comp Duplicator**

Original author:

**Brennan Chapman**

True Comp Duplicator is a third-party After Effects script and is not owned by GX2NNR.

The original third-party component remains subject to its own licensing terms.

Original source:

https://aescripts.com/true-comp-duplicator/

---

## Final Notes

NyaUIPanel is designed as a centralized workflow environment for Adobe After Effects.

Its three main systems serve different purposes:

```text
NyaUI
Production and workflow tools

NyaPresets
Preset organization

NyaScripts
Script organization and execution
```

Keeping these functions together allows frequently used tools to remain accessible without repeatedly navigating through the After Effects interface or separate folders.