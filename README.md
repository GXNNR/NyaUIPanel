# NyaUIPanel 3.0.1

## User Manual & Complete Function Guide

**Creator:** GX2NNR
**Discord:** gx2nnr
**Compatible with:** Adobe After Effects 2020+ (Windows installer included, manual install on macOS)

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [What's New in 3.0](#2-whats-new-in-30)
3. [Requirements](#3-requirements)
4. [Installation](#4-installation)
5. [First Launch](#5-first-launch)
6. [Interface Overview](#6-interface-overview)
7. [Modular Layout](#7-modular-layout)
8. [NyaUI Tools](#8-nyaui-tools)
   * [Declutter](#81-declutter)
   * [RenderHub](#82-renderhub)
   * [Precomp](#83-precomp)
   * [True Comp Duplicator](#84-true-comp-duplicator)
   * [Watch Tower](#85-watch-tower)
   * [MarkTools](#86-marktools)
   * [Expression Manager](#87-expression-manager)
   * [Reduce 2X](#88-reduce-2x)
   * [Hide Layer](#89-hide-layer)
   * [Comp Editor](#810-comp-editor)
   * [Move Attributes](#811-move-attributes)
9. [NyaPresets](#9-nyapresets)
10. [NyaScripts](#10-nyascripts)
11. [Settings and Themes](#11-settings-and-themes)
12. [Automatic Updates](#12-automatic-updates)
13. [Stability](#13-stability)
14. [Persistent User Data](#14-persistent-user-data)
15. [Backup and Migration](#15-backup-and-migration)
16. [Troubleshooting](#16-troubleshooting)
17. [Quick Reference](#17-quick-reference)
18. [Safety and Usage Notes](#18-safety-and-usage-notes)
19. [Video Tutorial](#19-video-tutorial)
20. [License](#20-license)
21. [Credits](#21-credits)

---

# 1. Introduction

**NyaUIPanel** is an Adobe After Effects extension created by **GX2NNR**.

It combines multiple production utilities into one dockable panel, reducing the need to repeatedly open separate scripts or perform repetitive After Effects operations manually.

NyaUIPanel is divided into three main sections:

### NyaUI
The main workflow and production tools, in a layout you can rearrange.

### NyaPresets
A searchable personal library for After Effects `.ffx` animation presets.

### NyaScripts
A searchable personal library and launcher for external After Effects scripts (`.jsx`, `.jsxbin`, `.js`).

User settings and libraries are stored separately from the panel itself, so updates never touch your data.

---

# 2. What's New in 3.0

* **Now an extension.** NyaUIPanel is no longer a ScriptUI `.jsx` file. It opens from `Window > Extensions` and docks like any native panel.
* **Modular layout.** Choose which buttons you see, drag them around, group them in sections, rename and recolor them, and pick a size.
* **New design.** Icon cards for every tool, three themes and a cleaner interface.
* **Pin anything.** Pin any script or preset as a button in NyaUI.
* **Watch Tower background service.** Folders are watched outside After Effects, so AE is only touched when a file actually appears or disappears.
* **Automatic updates.** New versions are downloaded, verified and installed in the background.
* **Stability.** Fixes panels freezing, buttons disappearing on hover, empty panels after switching workspaces, and the *"Cannot run a script while a modal dialog is waiting for response"* error.

<img width="340" height="560" alt="nya_new_edit" src="https://github.com/user-attachments/assets/4c5504d2-5d5b-4931-84be-aafa8d51011a" />
<img width="340" height="560" alt="nya_new_S" src="https://github.com/user-attachments/assets/55546e99-d759-44f3-b7ae-f54f5eddbf67" />
<img width="340" height="560" alt="nya_new_presets" src="https://github.com/user-attachments/assets/f1566197-de9e-4647-8a49-958a48eb6414" />
<img width="340" height="560" alt="nya_new_M" src="https://github.com/user-attachments/assets/5b0ed515-c66c-45d1-915a-cc423a901875" />


* **This is EasyLayer EasyLayersLite 3.0.0.**

<img width="440" height="330" alt="el_10_top" src="https://github.com/user-attachments/assets/b05139ee-442d-4f73-9d9c-77d52c42cfd4" />


See `CHANGELOG.md` for the full list.

---

# 3. Requirements

* Adobe After Effects 2020 or newer
* Windows (installer included) or macOS (manual install)
* The NyaUIPanel package from the [Releases page](https://github.com/GXNNR/NyaUIPanel/releases)

No administrator rights are needed: the extension installs in your user folder.

---

# 4. Installation

## 4.1 Upgrading from 2.x (important)

If you used a previous version, **remove the old file** from the ScriptUI Panels folder before installing:

```text
C:\Program Files\Adobe\Adobe After Effects <version>\Support Files\Scripts\ScriptUI Panels\NyaUIPanel V2.x.jsx / .jsxbin
```

If the old panel stays there, its Watch Tower timer can keep running and bring back the modal dialog error. Your presets, scripts and settings are kept and read automatically by 3.0.

## 4.2 Windows

1. Download `NyaUIPanel_<version>.zip` from the [Releases page](https://github.com/GXNNR/NyaUIPanel/releases) and extract it.
2. Close After Effects.
3. Double-click `INSTALAR_Windows.bat`.
4. Open After Effects and go to **Window → Extensions → NyaUIPanel**.

The installer copies two extensions into `%APPDATA%\Adobe\CEP\extensions`:

```text
com.nya.uipanel       the panel
com.nya.watchtower    the Watch Tower background service (no window)
```

It also enables loading of unsigned extensions for your user, which is required for extensions distributed outside Adobe Exchange.

## 4.3 macOS

1. In Terminal:

```text
defaults write com.adobe.CSXS.11 PlayerDebugMode 1
defaults write com.adobe.CSXS.12 PlayerDebugMode 1
```

2. Copy `com.nya.uipanel` and `com.nya.watchtower` to:

```text
~/Library/Application Support/Adobe/CEP/extensions/
```

3. Restart After Effects and open **Window → Extensions → NyaUIPanel**.

## 4.4 Uninstall

Run `DESINSTALAR_Windows.bat`. Your data in `Documents` is not removed.

---

# 5. First Launch

The panel opens with three tabs:

```text
NyaUI
NyaPresets
NyaScripts
```

and a gear button (**⚙ Settings**) on the right.

The status bar at the bottom shows the result of every action. The panel remembers the last tab you used.

---

# 6. Interface Overview

| Area | What it does |
| --- | --- |
| **NyaUI** | Tool buttons in sections you can rearrange |
| **NyaPresets** | `.ffx` preset library |
| **NyaScripts** | Script library and launcher |
| **⚙ Settings** | Theme, updates, layout export/import, data folders |
| **Status bar** | Result of the last action |
| **Top banner** | Update notices |

---

# 7. Modular Layout

Click **✎ Edit layout** in the NyaUI tab to enter edit mode. Click **✔ Done** when finished. Changes are saved automatically.

In edit mode you can:

* **Move buttons:** drag them to reorder, or drop them into another section.
* **Rename / recolor:** click a button to change its label and color. The color tints the icon and the border.
* **Hide:** click the **×** on a button. Hidden tools can be added back with **+ Button**.
* **+ Button:** add a hidden tool, any script file (`.jsx`, `.jsxbin`) or any preset file (`.ffx`) as a button.
* **+ Section:** create a new section. Sections can be renamed, moved up/down, collapsed or deleted.
* **Size:** **S** (compact list), **M** (cards) or **L** (large cards).

Outside edit mode, click a section title to collapse or expand it.

Layouts can be exported and imported from **⚙ Settings → NyaUI layout**, and reset to the default buttons at any time.

---

# 8. NyaUI Tools

---

## 8.1 Declutter

**DECLUTTER** organizes the project into folders at the project root and can remove unused duplicate imports.

### Built-in folders

```text
VIDEO   IMAGE   COMPOSITIONS   AUDIO   PSD   SOLIDS   3D   OTHER
```

Each folder gets its own label color and is created only when needed. Existing root folders with the same name are reused. **OTHER** (unknown formats) is only used when its checkbox is ticked, even with **All** enabled.

### Custom folders

Click **+ NEW FOLDER** to create your own rules:

* **Name** and **Color**
* **Extensions**, for example `png, jpg, mov`
* **Name contains**, for example `intro, title` (works for compositions and footage)

An item goes into a custom folder if its extension is listed **or** its name contains one of the words. Custom folders are checked before the built-in ones and are saved in `Documents\SYNC\NyaDeclutter.json`.

### Options

* **Only items loose in the project root:** items already inside your own folders are left alone.
* **Remove unused duplicates:** when the same file is imported several times, one copy is kept (preferably the one in use) and unused copies are removed.

### Undo

The whole operation is one undo step: `Organize Project`.

---

## 8.2 RenderHub

**RENDERHUB** opens a floating window to name and queue compositions for rendering.

### Adding compositions

Select compositions in the Project panel and press **+ ADD SELECTED**. The list supports search, **UP / DOWN** reordering, **REMOVE** and **CLEAR LIST**.

### Naming modes

* **CUSTOM:** name each render individually. An empty name uses the composition name.
* **ANIME CLIPS:** one base name, numbered automatically in list order, for example:

```text
Name - S01E1 (1)
Name - S01E1 (2)
Name - S01E1 (3)
```

### Output path

* **Global folder** for every composition, or
* **INDIVIDUAL** folders for the selected compositions.

### Options

* **Extension:** PNG, or AUTO (uses the Output Module template).
* **Clear queue first:** removes existing Render Queue items before sending.
* **Clear list after send**
* **Render now:** starts rendering right away (**SEND & RENDER**).

### Safety checks

Before sending, RenderHub checks for missing compositions, empty names, duplicate output names and missing folders (offering to create them). It also warns before overwriting existing files.

Settings are saved in `Documents\SYNC\NyaRenderHub.json`.

---

## 8.3 Precomp

**PRECOMP** precomposes **each selected layer individually**. Each new composition is trimmed to the length of its layer, and the precomp layer keeps the original in/out timing.

Uses the **Move attributes** switch (see [8.11](#811-move-attributes)).

---

## 8.4 True Comp Duplicator

**COMP-2X** is a third-party composition duplication script integrated into NyaUIPanel.

The original script was created by **Brennan Chapman**.

NyaUIPanel does not claim authorship or ownership of the original True Comp Duplicator code. The third-party source is integrated without modification; NyaUIPanel only provides access to it from its interface.

**True Comp Duplicator is not covered by the NyaUIPanel license.** It remains subject to its own license and terms.

https://aescripts.com/true-comp-duplicator/

---

## 8.5 Watch Tower

**WATCHTOWER** is a **folder mirror engine**: it keeps disk folders and your After Effects project in sync.

* Files that appear on disk are imported automatically.
* Files that disappear from disk are removed from the project, with safety checks.
* Items still in use whose source file is gone are labelled **red** and never removed.

### 8.5.1 How it works in 3.0

Watching is done by the **NyaWatchTower background service** (`com.nya.watchtower`), installed together with the panel:

* It starts with After Effects, has no window and does not depend on the workspace.
* It checks the folders **outside After Effects**.
* It only enters After Effects when a file actually appears or disappears. When nothing changes, it runs nothing inside AE.
* It never opens dialogs. If After Effects is busy or rendering, it waits and retries.

### 8.5.2 Interface

Click **WATCHTOWER** to open its screen inside the panel:

* **+ ADD FOLDER:** add a folder to watch
* **REPLACE:** replace the selected folder
* **Interval:** how often folders are checked (2–60 s)
* **OFF / ON:** turn auto-import on or off
* **Folder list:** missing folders show `[missing]`; double-click opens the folder
* **OPEN FOLDER:** open the selected folder in the file browser
* **IMPORT NOW:** sync immediately (this is also where large removals are confirmed)
* **REMOVE:** stop watching the selected folder (imported items stay in the project)
* **Status line:** a green dot means the service is watching

### 8.5.3 Mirror behavior

* **New files** are imported inside folder items tagged `NWT:<path>` that mirror the disk hierarchy.
* **Image sequences** (3 or more numbered files with the same prefix and extension) are imported as a single sequence.
* **Deleted files** are removed from the project only if the file is really gone and the item is not used in any composition.

### 8.5.4 Safety features

* **Stability check:** new files are imported only after they stop changing (at least 8 seconds old, or two checks with the same size), to avoid half-copied renders.
* **Batch limit:** at most 150 imports per sync; the rest continue on the next one.
* **In-use protection:** items used in compositions are labelled red, never removed.
* **Large removals on hold:** batches of 10+ items, or more than half of a folder, are not removed automatically. They show as *removals on hold* and are confirmed with **IMPORT NOW**.
* **Rendering protection:** nothing is imported while the Render Queue is rendering.

### 8.5.5 Status counters

```text
Watching | 1 missing | 12 waiting | 2 removals on hold | 5 in use (red) | 1 failed | last 14:32:10  +3 / -1
```

* **missing:** watched folders that cannot be accessed
* **waiting:** new files still being written
* **removals on hold:** large removals waiting for **IMPORT NOW**
* **in use (red):** items whose file is gone but are still used
* **failed:** imports that failed
* **last +N / -M:** time and result of the last change

### 8.5.6 Files

```text
Documents\SYNC\NyaWatchTower.json          folders, ON/OFF, interval
Documents\SYNC\NyaWatchTower.status.json   live status written by the service
Documents\SYNC\NyaWatchTower.log           errors from manual imports
```

Legacy `path1.json … path10.json` and `lastUsedPath.json` files from very old versions are migrated automatically and left in place.

---

## 8.6 MarkTools

**MARKTOOLS** (formerly Mark Cut) is a set of marker-driven tools in one window.

### Common controls

* **Marker color:** react to all markers or only to markers of one label color.
* **COMP / LAYER** switch on each tool: use composition markers or each layer's own markers.
* **REFRESH:** when a color filter is used, marker times are stored in the expression. If you move those markers, press REFRESH to update them.

### CUT

**CUT AT MARKERS** splits layers at the markers by duplicating and trimming them. It uses the selected layers, or all unlocked layers if none is selected. Undo: `MarkTools Cut at Markers`.

### SUBTITLES

**TXT TO MARKERS**: select one text layer and pick a `.txt` file with **one line per marker**. Each line is placed in Source Text at its marker. The number of lines must match the number of markers.

### BOUNCE

**POSITION / ROTATION / SCALE**: repeats the property's keyframes (2 or more) at every marker, with an overshoot controlled by **Amp**, **Freq** and **Decay**.

### PULSE

**APPLY PULSE**: pulses the selected single-value properties (effect sliders, etc.), or Opacity if no property is selected. It goes from **Base** to **Peak** with **Attack / Hold / Release** in frames, with optional **Ease**.

### SCROLLER

**SCROLLER NULL**: creates a null whose Position jumps (or eases with **Smooth**) through its keyframes at every marker, looping. Add 2 or more Position keyframes afterwards.

### NYA PROXIMITY

**APPLY PROXIMITY**: the selected layers grow in Scale when they get close to the scroller null (**Radius**, **Grow**).

### TOGGLE

**APPLY TOGGLE**: slides the selected layers between their Position keyframes at every marker (for example OFF and ON positions). The optional **Text** creates a text layer that cycles through a list of words, for example `OFF, ON` or `LOW, MID, HIGH`.

---

## 8.7 Expression Manager

**X-PRESER** extracts, stores, navigates, edits, loads and applies expressions.

* **Extract Expression:** reads every expression of the selected layer, remembering composition, layer and property path.
* **◀ / ▶:** browse the extracted or loaded expressions (`1/5`). Edits in the text box are kept while browsing.
* **▶ (toggle):** enable/disable the expressions of the selected layers.
* **❌:** removes all expressions from the selected layers.
* **Apply Expression:** writes the expression back to its original property. If that is not possible, it applies it to the currently selected properties.
* **▼:** load an expression file from `Documents\Expressions`, with search and **favorites (★)**.
* **Upload File (.txt):** load a text file from anywhere.
* **Save:** save the current text to `Documents\Expressions`.
* **Expressions Folder:** open the folder.

Favorites are stored in `Documents\SYNC\NyaXPreserFavorites.json`.

---

## 8.8 Reduce 2X

**REDUCE-2X** creates a reduced copy of the project for the selected composition(s):

1. Saves the current project.
2. Creates a folder named `<ProjectName>_<CompName>` next to it.
3. Runs After Effects' **Reduce Project** and saves the result there.
4. Opens that folder and asks whether to open the reduced project or return to the original.

Save your work before using it, since it changes the open project.

---

## 8.9 Hide Layer

**HIDELAYER** manages layers by **label color**, using the first selected layer as reference.

* **HIDE LAYERS (SAME COLOR)**
* **HIDE LAYERS (ARE NOT THIS COLOR)**
* **SHOW ALL:** enables every layer and turns Shy off

Options:

* **HIDE VISIBILITY:** turns the affected layers off.
* **ENABLE SHY:** marks the affected layers as Shy.

Settings are saved in `Documents\SYNC\NyaHCLSettings.json`.

---

## 8.10 Comp Editor

**COMP-MGR** opens **NyaCompManager V2.1**.

### Change Resolution

Enter width and height. The content is **scaled to fit**:

* Position, Scale and Anchor Point are mapped, including keyframes and spatial tangents.
* Parenting is respected, so nothing is scaled twice.
* Cameras and lights keep their framing (zoom, focus distance, aperture, falloff, radius).
* Precomps that are also used outside this hierarchy are left untouched.
* Locked layers are processed but never unlocked.
* Everything is validated first (After Effects limit: 30000 px).

### Change Duration

Accepted formats: `90`, `90.5`, `1:30`, `1:30:00`, `1:30,5`, `240f` (frames).

* Layers that reached the old end are extended to the new end. Layers with their own timing are left alone.
* Footage is clamped to its source length.
* The work area is adjusted.
* Locked layers are skipped.

### Change FPS

Enter a frame rate (for example `23.976`, `29.97`, `30`, `60`).

* The animation keeps its timing in seconds and keyframes snap to the new frame grid.
* Easing, continuity, auto-bezier and spatial tangents are preserved.
* Expressions using `time` or `frame` are counted so you can review them.
* Locked layers are skipped.

The **Change nested compositions** checkbox of each operation controls recursion into precomps. Every operation is a single undo step.

### Toggle Auto Scale 3D

Toggles an expression on the selected 3D layers that compensates Scale according to their Z distance from the active camera.

### NyaParallax

Prepares a parallax setup on the selected layers:

1. Enables 3D.
2. Applies the auto-scale expression.
3. Assigns Z positions (default distance `2500`).
4. Creates a 3D null named `Camera Controller` and parents the existing camera to it.

A camera must already exist in the composition.

---

## 8.11 Move Attributes

The **Move attributes** switch (ON / OFF) controls whether **PRECOMP** moves the layer's attributes into the new composition. Its state is remembered between sessions.

---

# 9. NyaPresets

A personal library for `.ffx` presets.

* **Search:** filters by name and description while typing.
* **Category filter** and **+** to create categories (default: VFX, Color, Audio, Text, Motion, Other).
* **Apply / double-click:** applies the preset to the selected layer(s).
* **Multi-select:** Ctrl/Shift-click.
* **★:** mark or unmark favorites. The **☆** button above the list shows favorites only.
* **📌:** pin the selected preset(s) as buttons in NyaUI.
* **Add:** pick one or more `.ffx` files, then choose a category and an optional description.
* **Edit:** name, category and description.
* **Delete:** removes entries from the library (the `.ffx` files are not deleted).
* **↻:** reload the library from disk.
* **⋯ menu:** export library (backup), import library (adds to the current one), open library folder, delete all.

Presets whose file no longer exists are shown in red.

---

# 10. NyaScripts

A personal launcher for `.jsx`, `.jsxbin` and `.js` scripts.

* **Add Script:** pick one or more files. The alias is the filename without extension, and duplicate paths are ignored.
* **Run / double-click / Enter:** runs the script.
* **Search**, **categories** (with **+**), **★ favorites** and the **☆** favorites filter.
* **📌:** pin the selected script as a button in NyaUI.
* **Edit:** change the alias and category (the file itself is not renamed).
* **Delete:** removes the entry (the file is not deleted).
* **⋯ menu:**
  * **Try to open as dockable panel:** runs scripts through their After Effects menu command (`app.findMenuCommandId` / `app.executeCommand`) when available.
  * **Export list (.qsl)** / **Import list (replace)**
  * **Open data folder**
  * **Delete ALL scripts**

Scripts run with `$.evalFile`; interfaces they return are kept alive so their windows do not close.

---

# 11. Settings and Themes

Open **⚙ Settings**:

* **Appearance:** After Effects (default), Black or Classic grey.
* **Updates:** automatic check, automatic install, and **Check now**.
* **NyaUI layout:** Export, Import, Reset.
* **Data:** open the SYNC folder, and **Reload host** (reloads the After Effects side of the panel without restarting).

---

# 12. Automatic Updates

NyaUIPanel checks for new versions in the background (every few hours while open).

When a new version is found, it:

1. Downloads the package without freezing After Effects.
2. Verifies its **SHA-256** fingerprint. If it does not match, nothing is installed.
3. Backs up the current version to `Documents\SYNC\NyaUIPanel_backup\<version>`.
4. Installs the panel and the Watch Tower service.
5. Shows a notice. The update applies after restarting After Effects.

You can disable automatic checking or installing in **⚙ Settings → Updates**. If an automatic install is not possible, the notice offers **Download manually**.

Users of 2.x versions get an update notice that opens the Releases page. Install 3.0 manually once (see [4.1](#41-upgrading-from-2x-important)); after that, updates are automatic.

---

# 13. Stability

Version 3.0 fixes the root cause of panels freezing, buttons disappearing on hover, empty panels after switching workspaces, and the *"Cannot run a script while a modal dialog is waiting for response"* error.

* **Own engine:** each panel runs in its own scripting engine, so a failure elsewhere cannot take it down.
* **No timers inside After Effects:** Watch Tower now runs as an external service and only touches After Effects when something changes.
* **No surprise dialogs:** background processes never open dialogs.
* **Non-blocking updates:** the update check never freezes After Effects at startup.

---

# 14. Persistent User Data

```text
Documents\SYNC\
    NyaUIPanel_layout.json        NyaUI buttons and sections
    NyaUIPanel_settings.json      theme, updates, last tab, Move attributes
    NyaUIPanel_update.json        update check cache
    NyaUIPanel_backup\            previous versions kept by the updater
    NyaWatchTower.json            Watch Tower folders and state
    NyaWatchTower.status.json     Watch Tower service status
    NyaWatchTower.log             Watch Tower errors
    NyaRenderHub.json             RenderHub settings
    NyaDeclutter.json             Declutter custom folders
    NyaXPreserFavorites.json      X-PRESER favorites
    NyaHCLSettings.json           Hide Layer settings

Documents\Expressions\            saved expressions

Documents\NyaPresets\
    library.json
    categories.json

Documents\NyaScripts\
    AfterEffectsScripts.txt
    AfterEffectsScripts_backup.txt
    NyaScriptsSettings.txt
    NyaScriptsCategories.txt
```

Libraries from older versions stored in `AppData\Roaming\NyaPresets` and `AppData\Roaming\NyaScripts` are migrated automatically on first launch.

---

# 15. Backup and Migration

Before reinstalling After Effects or moving to another computer, back up:

```text
Documents\SYNC
Documents\Expressions
Documents\NyaPresets
Documents\NyaScripts
```

Copy them to the same place on the new computer, install NyaUIPanel, and everything is restored, including your NyaUI layout.

You can also use the built-in **Export / Import** functions for presets, scripts and the NyaUI layout.

---

# 16. Troubleshooting

## NyaUIPanel does not appear in Window → Extensions

* Run `INSTALAR_Windows.bat` again with After Effects closed.
* Check that `%APPDATA%\Adobe\CEP\extensions\com.nya.uipanel\CSXS\manifest.xml` exists.
* Restart After Effects completely.

## The status bar shows "Host: ERR…"

The After Effects side of the panel could not load. Try **⚙ Settings → Reload host**. If it persists, reinstall and report the message.

## Buttons do nothing / "After Effects is busy"

A dialog is open in After Effects, or a long operation is running. Close it and try again. Also check that the tool has what it needs (active composition, selected layers, selected project items, markers or a camera).

## Watch Tower says "background service not detected"

* Make sure `com.nya.watchtower` exists in `%APPDATA%\Adobe\CEP\extensions`.
* Restart After Effects.
* Meanwhile, **IMPORT NOW** still syncs manually.

## Watch Tower is not importing new files

* Check that it is **ON** and that the folder is not `[missing]`.
* **waiting** is normal while files are still being written.
* If it shows **failed**, see `Documents\SYNC\NyaWatchTower.log`.

## "Update failed: downloaded file does not match the published SHA-256"

The package on the server is not the one that was published with that fingerprint. Nothing was installed. Use **Download manually** or wait for a corrected release.

## The modal dialog error still appears

Make sure the old `NyaUIPanel V2.x` file was removed from `ScriptUI Panels` (see [4.1](#41-upgrading-from-2x-important)). Another installed script using timers could also cause it.

## A preset or script cannot be used

Entries in red point to files that no longer exist. Use **Edit** / **Delete**, or add the file again from its new location.

## Developer console

With After Effects open, open in Chrome:

```text
http://localhost:8098   NyaUIPanel
http://localhost:8099   Watch Tower service
```

These consoles only work if the `.debug` files are present (development builds).

---

# 17. Quick Reference

| Section | Tool | Main Purpose |
| --- | --- | --- |
| NyaUI | DECLUTTER | Organize the project into folders, custom rules, remove unused duplicates |
| NyaUI | RENDERHUB | Name, route and queue compositions for rendering |
| NyaUI | PRECOMP | Precompose each selected layer trimmed to its length |
| NyaUI | COMP-2X | True Comp Duplicator (third party) |
| NyaUI | WATCHTOWER | Mirror disk folders into the project automatically |
| NyaUI | MARKTOOLS | Cut, subtitles, bounce, pulse, scroller, proximity and toggle driven by markers |
| NyaUI | X-PRESER | Extract, save, load and apply expressions |
| NyaUI | REDUCE-2X | Create a reduced project copy |
| NyaUI | HIDELAYER | Hide / Shy layers by label color |
| NyaUI | COMP-MGR | Resolution, duration, FPS, Auto Scale 3D, NyaParallax |
| NyaUI | Move attributes | Precomp option |
| NyaUI | Edit layout | Rearrange, hide, rename, recolor, sections, sizes, pins |
| NyaPresets | Library | Search, categories, favorites, pin, apply, import/export |
| NyaScripts | Launcher | Search, categories, favorites, pin, run, import/export |
| Settings | ⚙ | Themes, updates, layout backup, reload host |

---

# 18. Safety and Usage Notes

NyaUIPanel automates operations that can affect compositions, layers, project files, expressions and the Render Queue.

* Save important projects before large automated operations.
* Check your selection before running tools that work on selected items.
* RenderHub can clear the Render Queue (**Clear queue first**).
* Watch Tower, when ON, imports and removes items to mirror the disk; large removals always wait for your confirmation.
* Comp Editor's Change Resolution scales layer content, not just the composition.
* Keep backups of your personal libraries.
* Do not modify or redistribute NyaUIPanel except as permitted by the included license.
* Third-party components remain subject to their own licenses and terms.

---

# 19. Video Tutorial

https://youtu.be/6tYuLW5nhQA

The tutorial introduces NyaUIPanel and its workflow (recorded with a previous version; the tools work the same way).

---

# 20. License

NyaUIPanel is proprietary software created by **GX2NNR**.

The included license applies to the original components created by GX2NNR. Third-party software and resources are not covered by the NyaUIPanel license and remain subject to their respective licenses and terms.

For complete licensing information, see the included `LICENSE` file.

---

# 21. Credits

## NyaUIPanel

Created by **GX2NNR** · Discord: **gx2nnr**

Compatible with **Adobe After Effects 2020+**

## Third-Party Component

**True Comp Duplicator** by **Brennan Chapman**

True Comp Duplicator is a third-party After Effects script and is not owned by GX2NNR. It remains subject to its own licensing terms.

https://aescripts.com/true-comp-duplicator/

---

## Final Notes

NyaUIPanel is designed as a centralized workflow environment for Adobe After Effects:

```text
NyaUI         production and workflow tools, arranged your way
NyaPresets    preset organization
NyaScripts    script organization and execution
```

Keeping these functions together lets your most used tools stay one click away, without navigating through menus or separate folders.
