<img src="path/to/kdenlive.png">

# DaVinci Resolve Layout for Kdenlive

**Version: 0.1.0-alpha**

A custom keyboard shortcut map for Kdenlive that mirrors DaVinci Resolve's editing workflow as closely as possible.

---

## What It Is

`Davinci Resolve Layout.shortcuts` is a Kdenlive shortcut file that remaps Kdenlive's default keybindings to match DaVinci Resolve's layout. The goal is getting Resolve users started in Kdenlive with less friction. 

This is a work in progress. Kdenlive and Resolve are different applications built on different philosophies, so not every shortcut has a direct equivalent. Where a 1:1 mapping exists, it'll be ported. Where it doesn't, the approach is: *if this tool existed in Resolve, how would it be mapped?* The mapping stays in the same language rather than forcing arbitrary assignments.

**Currently mapped (partial list):**
- Timeline playback: `J` / `K` / `L` (rewind / pause / play)
- Frame stepping: Arrow keys
- Snap to clips/cuts: `N`
- Select tool: `A`
- Razor blade tool: `B`
- Slip tool: `S`
- Render: `*` (in-lieu of 'Deliver Page')
- Dissolve transition: `Ctrl+T`
- Ripple Delete: `Shift+Backspace`
- Layout switching (i.e. Logging, Editing, etc): `!` `@`  `#` `$` `%`
- Standard file operations: `Ctrl+N`, `Ctrl+O`, `Ctrl+S`, `Ctrl+Shift+S`, `Ctrl+Q`

More mappings are actively being added. As of now it's a proof of concept but something simple such as cutting down a-roll and covering with b-roll should be feasible with relative ease. 

---

## Why It Was Made

DaVinci Resolve is a powerful, industry-standard NLE. But its linux variant has some big asterisks. When it works, it's incredible and indistinguishable from its Mac and Windows counterparts. When it doesn't work, well...make some different plans for your day. Kdenlive is a capable open-source alternative that runs natively on Linux, and it's growing every day. 

The friction of switching isn't really the features, it's the muscle memory. Years of blade cuts on `B`, and reaching for `Shift+Backspace` to ripple delete adds up. This shortcut layout exists to remove that friction so the transition to open-source tools feels like a continuation rather than a restart.

This is also a personal project: Resolve's shortcut logic is genuinely intuitive, and porting that UX to Kdenlive means the friction can live where it needs to; in the creative work itself. 

---

## How to Install

1. Download `Davinci_Resolve_Layout.shortcuts` from this repository.

2. Open Kdenlive.

3. Go to **Settings → Configure Kdenlive → Shortcuts**.

4. Click the **Import** button (folder icon) at the top of the Shortcuts panel.

5. Navigate to and select the downloaded `.shortcuts` file.

6. Click **OK** to apply.

7. Restart Kdenlive to ensure all bindings are active.

> **Tip:** Before importing, export your current shortcut layout first (**Settings → Configure Kdenlive → Shortcuts → Export**) so you can restore it if needed.

---

## Status & Contributing

This file covers the full list of Kdenlive's assignable shortcuts (~885 entries). Many are still mapped to `none` — either because no Resolve equivalent exists, or because the mapping logic is still being worked out for tools that behave differently between the two apps.

Contributions are welcome. If you have a mapping suggestion, especially for features where the two apps diverge, open an Issue or a PR with your reasoning.

---

## License

This isn't software so it's CC0-1.0 license Public Domain.
