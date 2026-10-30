# L'Arsène's Ludicrous Larceny — DM Companion (Maps)

Unofficial supplemental **battlemaps** for the free adventure *L'Arsène's Ludicrous Larceny*,
packaged as a Foundry VTT (v12 / v13) **Scenes compendium**. Two sets:

- **Water Temple — "White Water Worship"** — a realistic top-down re-skin of the adventure's Map F
  (stone block walls, flagstone floors, a central water font).
- **The Lemnisciator** — a modular ∞-loop tileset (entrance, sealed entrance, four escalating
  straights, two bends, a plain crossroads, two infinity-mosaic crossroads, exit, sealed exit) for
  building the infinity-symbol trap dungeon that silently loops a party forever.
- **Aramachi Manor** — the mayor's manor (ground + upper floors) that the heist breaks into, as two
  scenes. See *Map credits* below for this map's provenance.

This module contains original AI-generated map art plus one CC BY-NC estate map (the manor, by
Morvold Press — see *Map credits*). Because that map is **NonCommercial**, treat the whole
compendium as non-commercial. It does not include the adventure's text, stat blocks, journals, or
other content — get those from the creators below.

## The original adventure — credit & where to get it

*L'Arsène's Ludicrous Larceny* is designed by **Humperdink's Wares** and **Loot Tavern**, and is
distributed free for non-commercial use.

- Free adventure PDF (Patreon): https://www.patreon.com/posts/39943717
- Humperdink's Wares: https://www.patreon.com/humpswares
- Loot Tavern: https://www.patreon.com/LootTavern
- **Original Foundry module** (actors, items, journals, maps, music):
  https://github.com/Jonwh25/larsenes
  — manifest: `https://github.com/Jonwh25/larsenes/releases/latest/download/module.json`
  — Foundry conversion by Plankdangerous (Gathering Hall Games), Jon Whitehouse, and the Foundry VTT
  Team. Original cartography by Tom Cartos and Jon Whitehouse.

Install that module for the adventure itself; this companion only adds alternate maps.

## Install this companion

In Foundry: **Add-on Modules → Install Module**, and paste this manifest URL:

```
https://github.com/mbmcclelland/larsenes-dm-companion/releases/latest/download/module.json
```

Enable it in your world, then open the compendium below. The maps are system-agnostic (no particular
game system required).

## Requirements & add-ons

| Add-on | Needed for | Link |
|---|---|---|
| **Foundry VTT** v12+ (verified v13) | everything | https://foundryvtt.com |
| **Monk's Active Tile Triggers** (`monks-active-tiles`) | **required** for the Lemnisciator teleport-loop macro | https://foundryvtt.com/packages/monks-active-tiles · https://github.com/ironmonk88/monks-active-tiles |
| **libWrapper** (`lib-wrapper`) | recommended — MATT uses it | https://foundryvtt.com/packages/lib-wrapper · https://github.com/ruipin/fvtt-lib-wrapper |
| The original **L'Arsène's Ludicrous Larceny** Foundry module | the actual adventure (actors, items, journals, maps, music) | https://github.com/Jonwh25/larsenes |
| **dnd5e** system | only if you run the 5e adventure (the maps themselves are system-agnostic) | https://foundryvtt.com/packages/dnd5e |

The maps and scenes work with just Foundry. Only the **loop macro** needs Monk's Active Tile Triggers
(and a GM connected during play, since MATT relays player-walked teleports through the GM client).

## Contents — where to find things

**Compendium Packs** tab → **L'Arsène's Ludicrous Larceny** folder → **L'Arsène's Larceny — Maps**
(Scenes). 14 scenes:

| Scene | Notes |
|---|---|
| Water Temple — White Water Worship | Map F re-skin, full resolution (5120×3328) |
| Lemnisciator — Entrance / Entrance (Sealed) | the only tile with a visible door; the sealed version loops back |
| Lemnisciator — Straight 1–4 | the biology escalates bare → fleshy across a lap, then resets |
| Lemnisciator — Bend Left / Bend Right | |
| Lemnisciator — Crossroads (plain X) / (∞ knot) / (∞ organic) | the ∞-knot is the recommended loop centerpiece |
| Lemnisciator — Exit / Exit (Sealed) | swap sealed → open to release the party |
| Aramachi Manor — Ground Floor / Upper Floor | the manor the heist breaks into — "Noble Estate" by Morvold Press, CC BY-NC 4.0 |

Four whole-∞ concept renders also ship under `art/maps/lemnisciator/concepts/` (as art, not scenes).

## The Lemnisciator loop (silent teleport)

A compendium **macro** wires the infinity-loop for you using **Monk's Active Tile Triggers (MATT)**.

**Requires:** the `monks-active-tiles` module, enabled. A **GM must stay connected** during play —
MATT relays player-walked cross-scene teleports through the GM client.

**Setup:** open **Compendium Packs → L'Arsène's Larceny — Macros**, and run **"Build the
Lemnisciator Loop"** (as GM). It imports the 11 loop scenes into a **Lemnisciator** folder and wires
a hidden "on-enter" teleport across the top edge of each ring scene. Safe to re-run — it rebuilds the
teleports each time.

**How the loop runs:** drop the party on **Lemnisciator — Entrance** and have them walk toward the
top of the map. Each time they reach the top edge they're silently dropped at the bottom of the next
scene, so "forward" never ends:

```
Entrance → Entrance (Sealed) → Straight 1 → Bend Right → Straight 2 → Crossroads (∞)
         → Straight 3 → Bend Left → Straight 4 → Exit (Sealed) → back to Entrance (Sealed) …
```

The biology escalates bare→fleshy across a lap then resets — the tell that they're looping.

**Releasing them:** the **Exit** scene (the open door) is deliberately left **unwired**. To let the
party out, send them to **Lemnisciator — Exit** and point its door wherever your adventure continues
(add your own MATT teleport, or just move them).

**Tuning:** landings are bottom-centre and the trigger band is the top ~2 rows of each 768×768 tile.
Adjust the hidden tiles per scene if you want, and add **walls** so players are funnelled along a
corridor and can't see the seams (recommended but optional).

## Map credits & licensing

This repository is **multi-licensed**:

- **Water Temple** and **Lemnisciator** maps + all module code/scene definitions — original work by
  the repo owner, **MIT** (see `LICENSE`).
- **Aramachi Manor** (`art/maps/manor-ground.webp`, `art/maps/manor-upper.webp`) — the **"Noble
  Estate"** battlemap by **Morvold Press**, licensed **Creative Commons Attribution–NonCommercial
  4.0 International (CC BY-NC 4.0)**: https://creativecommons.org/licenses/by-nc/4.0/ . See
  `art/maps/MANOR-LICENSE.txt`.
  - **Creator:** Morvold Press — https://www.patreon.com/morvoldpress
  - Source: "Noble Estate" (Jul 16, 2020) —
    https://www.patreon.com/morvoldpress/posts/noble-estate-of-39392892
  - **NonCommercial:** because this map is CC BY-NC, the compendium as a whole may be used and shared
    for **non-commercial** purposes only; do not use it commercially while the manor map is bundled.

## Notes & roadmap

- **Grid:** each scene carries a best-guess grid — use Foundry's **Grid Configuration** to align it
  to the map before play.
- **The silent teleport loop is now included** as a one-click setup macro — see below. (Per-scene
  **walls & lighting** are still up to you; the maps ship as backgrounds.)
- The water-temple map is an original rendering derived from the layout of the adventure's Map F; the
  Lemnisciator tiles are wholly original.

## Licensing

Module code and scene definitions: **MIT** (see `LICENSE`). The map art is original work provided
for non-commercial personal table use. *L'Arsène's Ludicrous Larceny* and its original maps remain
the property of their respective creators. This is an unofficial fan supplement, not affiliated with
or endorsed by Humperdink's Wares, Loot Tavern, or the original Foundry conversion team.
