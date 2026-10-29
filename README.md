[DaVinci Resolve Layout for Kdenlive](https://github.com/zahntron/Davinci-Resolve-Shortcuts-for-Kdenlive/blob/main/Kdenlive.png)

# DaVinci Resolve Layout for Kdenlive

**Version: 0.2.0-beta**

A custom keyboard shortcut map for Kdenlive that mirrors DaVinci Resolve's editing workflow as closely as possible.

---

## What It Is

`Davinci_Resolve_Layout.shortcuts` is a Kdenlive shortcut scheme that remaps Kdenlive's default keybindings to match DaVinci Resolve's layout. Kdenlive already ships with its own defaults and an optional Premiere Pro style scheme. This adds Resolve to that list. The goal is getting Resolve users started in Kdenlive with less friction.

Kdenlive and Resolve are different applications built on different philosophies, so not every shortcut has a direct equivalent. Where a 1:1 mapping exists, it's ported. Where it doesn't, the approach is: *if this tool existed in Resolve, how would it be mapped?* The mapping stays in Resolve's language rather than forcing arbitrary assignments.

As of 0.2.0, around 100 actions are mapped with zero internal conflicts. That covers a complete assembly-to-fine-cut workflow: logging and marking, cutting down a-roll, covering with b-roll, trimming, retiming, markers, transitions, and handing off to render.

---

## What's Mapped

### Pages → Layouts

Resolve switches pages with `Shift+number`. Kdenlive doesn't have pages, but its workspace layouts serve the same purpose, so each page maps to the layout that does the same job.

| Resolve Page | Shortcut | Kdenlive Equivalent |
|---|---|---|
| Media | `Shift+2` | Logging layout |
| Edit | `Shift+4` | Editing layout |
| Fusion | `Shift+5` | Effects layout |
| Color | `Shift+6` | Color layout |
| Fairlight | `Shift+7` | Audio layout |
| Deliver | `Shift+8` | Render dialog |
| Project Settings | `Shift+9` | Project Settings |

> **Note:** This assumes Kdenlive's default layout order (1 Logging, 2 Editing, 3 Audio, 4 Effects, 5 Color). If you've reordered your layouts, adjust the `load_layout` slots to match.

### Playback & Navigation

| Action | Shortcut |
|---|---|
| Play / Pause | `Space` |
| Shuttle reverse / stop / forward | `J` / `K` / `L` |
| Step one frame | `Left` / `Right` |
| Jump one second | `Shift+Left` / `Shift+Right` |
| Previous / next edit point | `Up` / `Down` |
| Previous / next marker | `Shift+Up` / `Shift+Down` |
| Go to timeline start / end | `Home` / `End` |
| Go to clip start / end | `Ctrl+Shift+Left` / `Ctrl+Shift+Right` |
| Play in to out | `Alt+/` |
| Loop in to out | `Ctrl+/` |
| Toggle clip / timeline monitor | `Q` |
| Match frame (locate clip in bin) | `F` |
| Cinema viewer (monitor fullscreen) | `Ctrl+F` |
| Window fullscreen | `Ctrl+Shift+F` |

### Marking

| Action | Shortcut |
|---|---|
| Mark in / out | `I` / `O` |
| Go to in / out | `Shift+I` / `Shift+O` |
| Add marker | `M` |
| Edit marker | `Shift+M` |
| Delete marker | `Alt+M` |
| Previous / next keyframe | `[` / `]` |

### Tools

| Action | Shortcut |
|---|---|
| Selection | `A` |
| Trim (ripple) | `T` |
| Blade (razor) | `B` |
| Slip | `S` |
| Spacer (select forward) | `Y` |
| Snapping | `N` |

### Editing

| Action | Shortcut |
|---|---|
| Insert | `F9` |
| Overwrite | `F10` |
| Replace | `F11` |
| Split at playhead | `Ctrl+B` |
| Split all tracks at playhead | `Ctrl+Shift+B` |
| Delete (lift, leaves gap) | `Backspace` |
| Ripple delete | `Shift+Backspace` / `Del` |
| Lift zone | `Ctrl+Backspace` |
| Extract zone | `Ctrl+Shift+Backspace` |
| Trim start / end to playhead | `Shift+[` / `Shift+]` |
| Enable / disable clip | `D` |
| Link (group) / unlink | `Ctrl+Alt+L` / `Ctrl+Alt+Shift+L` |
| Target video track 1–8 | `Alt+1` – `Alt+8` |
| Target audio track 1–8 | `Ctrl+Alt+1` – `Ctrl+Alt+8` |

### Speed & Retiming

| Action | Shortcut |
|---|---|
| Change clip speed | `R` |
| Time remap | `Ctrl+R` |
| Freeze frame | `Shift+R` |
| Change clip duration | `Ctrl+D` |

### Transitions & Effects

| Action | Shortcut |
|---|---|
| Crossfade (same-track mix) | `Ctrl+T` |
| Dissolve composition (between tracks) | `Alt+T` |
| Paste effects | `Alt+V` |

### Timeline View

| Action | Shortcut |
|---|---|
| Zoom in / out | `Ctrl+=` / `Ctrl+-` |
| Zoom to fit | `Shift+Z` |

### Project & File

| Action | Shortcut |
|---|---|
| New sequence (timeline) | `Ctrl+N` |
| New bin folder | `Ctrl+Shift+N` |
| Import media | `Ctrl+I` |
| New project | `Ctrl+Alt+N` |
| Open / Save / Save As / Quit | `Ctrl+O` / `Ctrl+S` / `Ctrl+Shift+S` / `Ctrl+Q` |
| Undo / Redo | `Ctrl+Z` / `Ctrl+Shift+Z` |
| Cut / Copy / Paste | `Ctrl+X` / `Ctrl+C` / `Ctrl+V` |
| Preferences | `Ctrl+,` |
| Keyboard customization | `Ctrl+Alt+K` |
| Screen recording | `Ctrl+Shift+4` |

---

## Translation Notes

A few places where the two apps think differently, and how this layout handles it:

- **Crossfades vs. dissolves.** Resolve's `Ctrl+T` adds a standard transition at the cut. In Kdenlive, that same-track crossfade is called a **mix**, so `Ctrl+T` goes there. Kdenlive's Dissolve is a composition between two tracks, which lives on `Alt+T`.
- **New project vs. new timeline.** Resolve's `Ctrl+N` creates a new timeline, and projects live in the Project Manager. Kdenlive's equivalent of a timeline is a sequence, so `Ctrl+N` makes a sequence and new project moves to `Ctrl+Alt+N`.
- **Lift vs. ripple.** Resolve infers whether to lift or ripple from context. Kdenlive needs explicit actions, so clip and zone variants each get their own key in the same `Backspace` family.
- **Linked clips.** Kdenlive's groups behave like Resolve's linked selection, so they borrow Resolve's link shortcut.
- **The F10 menu.** Kdenlive binds `F10` to the hamburger menu by default. It's unbound here so `F9` / `F10` / `F11` work as Insert / Overwrite / Replace.

### Not Yet Mapped

These Resolve shortcuts have no clean Kdenlive equivalent yet:

- Nudge clip one frame (`,` / `.`)
- Append to end of timeline (`Shift+F12`)
- Fit to fill (`Shift+F11`)
- Linked selection toggle (`Ctrl+Shift+L`)

---

## Why It Was Made

DaVinci Resolve is a powerful, industry-standard NLE. But its Linux variant has some big asterisks. When it works, it's incredible and indistinguishable from its Mac and Windows counterparts. When it doesn't work, well... make some different plans for your day. Kdenlive is a capable open-source alternative that runs natively on Linux, and it's growing every day.

The friction of switching isn't really the features, it's the muscle memory. Years of blade cuts on `B` and reaching for `Shift+Backspace` to ripple delete add up. This shortcut layout exists to remove that friction so the transition to open-source tools feels like a continuation rather than a restart.

This is also a personal project. Resolve's shortcut logic is genuinely intuitive, and porting that UX to Kdenlive means the friction can live where it belongs: in the creative work itself.

---

## How to Install

1. Download `Davinci_Resolve_Layout.shortcuts` from this repository.
2. Open Kdenlive.
3. Go to **Settings → Configure Keyboard Shortcuts…**
4. Click **Manage Schemes**, then **More Actions → Import Scheme…**
5. Select the downloaded `.shortcuts` file.
6. Click **OK** to apply.
7. Restart Kdenlive to make sure all bindings are active.

> **Tip:** Before importing, export your current scheme first (**Manage Schemes → More Actions → Export Scheme…**) so you can restore it if needed.

### Non-US Keyboards

Some shortcuts are stored as the shifted character they produce on a US keyboard (the layout keys `@ $ & % ^ (` and the trim keys `{ }`). If one of these doesn't respond on your keyboard layout, rebind it once in the shortcuts dialog and Kdenlive will save it correctly for your layout.

---

## Status & Contributing

The file covers Kdenlive's full list of assignable actions (~880 entries). Around 100 are mapped. The rest are set to `none`, either because no Resolve equivalent exists or because the mapping logic is still being worked out for tools that behave differently between the two apps. The current focus is the editing workflow, with Color and Fairlight-style audio mappings as future candidates.

Contributions are welcome. If you have a mapping suggestion, especially for features where the two apps diverge, open an Issue or a PR with your reasoning. Please check for conflicts with existing bindings before submitting.

### Changelog

**0.2.0-beta**
- Expanded from ~20 to ~100 mapped actions
- Space is now Play / Pause, and `L` shuttles forward (previously swapped)
- `Ctrl+T` now adds a same-track crossfade (mix) and Dissolve moves to `Alt+T`
- `Ctrl+F` now opens the cinema viewer, and window fullscreen moves to `Ctrl+Shift+F`
- Layouts remapped to Resolve's `Shift+number` page keys
- Added insert / overwrite / replace on `F9` / `F10` / `F11`
- Added marking, markers, keyframe navigation, track targeting, retiming, and zoom
- Cleaned up stray empty alternate bindings

**0.1.0-alpha**
- Initial proof of concept with core transport, tools, and file operations

---

## License

This isn't software, so it's released under CC0-1.0 (public domain).
