# RIS Shader Engine Overhaul

A ReShade add-on for Total War: ROME REMASTERED that overhauls battle graphics: lighting, shadows, sky, fog, water, terrain, trees and battlefield effects.
It was made for the RTR: Imperium Surrectum (RIS) mod and also works with the base game.
It never changes the game's executable or any game file on disk.

See [CHANGELOG.md](CHANGELOG.md) for everything it adds and fixes.

## Features

The add-on has three parts, each with its own tab in the in-game window.

**Graphics Engine**
- Modern ambient occlusion, contact shadows and softer, sharper sun shadows.
- Ambient light from the sky's direction, and reflections that follow each surface's roughness.
- Sunlight through backlit leaves and grass, skin highlights and cloth sheen.
- New tone mapping (the game's curve, AgX, ACES 2.0 or GT7), bloom, a simulated lens flare and CMAA2 anti-aliasing.
- Terrain without visible tiling, with natural colour variation and rocky slopes.
- Fixes for defects in the game's own shaders, such as rough surfaces too dark in reflections and skin and leaves glowing in shade.

**TrueSky**
- Cloud shadows on the ground, clouds that drift with the wind, and a physically based sky with realistic sunsets.
- Height fog that follows the terrain, a low drifting mist, and sunbeams through clouds and trees.
- Rainbows, auroras on winter nights, lightning with thunder, and starlight at night.
- Ocean waves, and water that reflects the moving sky.

**Battlemap**
- Blood on the ground, stuck arrows and landed siege projectiles that stay, and craters where rocks land.
- Trees, grass and capes that move in the wind.
- Distant trees drawn as detailed impostors that look right from every angle.
- Butterflies and other insects over the grass and around the trees.

## Requirements

- Total War: ROME REMASTERED (DirectX 11).
- ReShade 6.8 or later, the build **with full add-on support**, installed for `Total War ROME REMASTERED.exe` with the DirectX 10/11/12 API.

## Install

1. Install ReShade as above, if it isn't installed yet.
2. Copy these into the game folder, next to ReShade's `dxgi.dll`:
   - `ris.addon64`
   - `ris_battlemap.ini`, `ris_engine.ini` and `ris_truesky.ini`
   - the `ris_battlemap` folder (decals, impostors, insects and thunder sounds)
3. If you used an earlier version, delete `ris_truesky.addon64`, `ris_battlemap.addon64` and `ris_engine.addon64` from the game folder.
   Your existing `.ini` files can stay.

## Use

- In game, press **Home** to open ReShade, then the **RIS** window.
- The window has a tab for each part: **Battlemap**, **Graphics Engine** and **TrueSky**.
  If it opens floating, drag it into ReShade's main window to dock it.
- Every feature can be switched on and off live, during a battle.
- Changes are saved to the `.ini` files by themselves, and edits made to the files are picked up while the game runs.

## Notes

- Distant tree impostors cover the RIS mod's trees; with other trees the game's own distant trees are kept.
- Some features need the game's own settings on: ambient occlusion needs the game's SSAO, and the edge smoothing features need MSAA.

## Uninstall

Delete `ris.addon64`, the three `.ini` files and the `ris_battlemap` folder from the game folder.
