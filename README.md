# RIS Shader Engine Overhaul

A ReShade add-on for Total War: ROME REMASTERED that overhauls battle graphics: lighting, shadows, sky, fog, water, terrain, trees and battlefield effects.
It was made for the RTR: Imperium Surrectum (RIS) mod and also works with the base game.
It never changes the game's executable or any game file on disk.

See [CHANGELOG.md](CHANGELOG.md) for what each release adds and fixes.

# Features

All features are configurable and can be enabled or disabled live through the in-game overlay (`Home` key).

## Lighting and Shadows

- Physically based sky and atmospheric lighting, with realistic sunset and twilight colours.
- Cloud shadows across terrain, units, buildings, vegetation and water.
- Directional ambient lighting: upward-facing surfaces receive sky light, downward-facing surfaces receive ground light, and creases receive less sky illumination.
- Screen-space light bounce from visible surfaces, allowing sunlit walls, ground and fires to illuminate nearby shaded areas. Optional for soldiers.
- Sun and moon light bounce from nearby illuminated surfaces into shaded areas.
- Street sky visibility: reduced sky illumination in narrow streets, courtyards and gate passages, affecting buildings, terrain, grass and trees, optionally soldiers.
- Street reflection occlusion: prevents streets and courtyards from reflecting the open sky.
- Torch and fire shadows, preventing light from passing through walls.
- Physically based torch and fire lighting, with flickering, extended reach and configurable light falloff.
- Coloured light bounce in shaded creases of skin and pale coats.
- Sunlight transmission through backlit leaves and grass blades.
- Adjustable light transmission through thin parts of horses, camels and elephants, as well as ears and fingers.
- Ambient occlusion with soft contact darkening beneath soldiers and inside formations.
- Coloured ambient occlusion on buildings.
- Contact shadows beneath feet, shields, helmets, grass and rocks.
- Specular occlusion on soldiers and buildings, reducing reflections in shaded areas, creases and beneath overhangs.
- Improved sun-shadow filtering, with consistent softness at different distances, naturally widening shadows and reduced shadow acne.
- Sunlight colour derived from TrueSKY atmospheric conditions, transitioning from warm orange at low sun to white at noon.
- Cloth sheen under both direct sunlight and sky illumination, including subtle highlights in shade, overcast conditions and at night.
- Two-layer skin highlights, combining a sharp oily specular core with a softer surrounding sheen.
- Ground relief derived from terrain normal maps, providing additional detail for ambient occlusion and contact shadows.
- Sky reflections with roughness-based blur and battlefield ground reflections below the horizon.

## Soldiers and Mounts

- Dynamic dust, mud and blood accumulation as real materials, based on each soldier's individual battle history.
- Wet soldiers and mounts, becoming darker and smoother in rain and gradually drying afterwards.
- Snow accumulation on soldiers standing in snow, with snow being shed as they move.
- Normal maps on distant soldiers, maintaining consistent surface detail and highlights across LOD transitions.
- Smoother edges on cut-out parts of soldiers and mounts.
- Smooth transitions and fades between soldier and mount detail levels.

## Buildings

- Dynamic snow accumulation on buildings.
- Wet building materials during rain, including puddles and water streaks.
- Improved distant building highlights.
- Physically influenced ambient occlusion, specular occlusion and light bounce.

## Terrain

- Hexagonal texture blending with randomly rotated tiles, eliminating visible texture tiling at both near and far distances.
- Broad, natural colour variation across the terrain.
- Terrain layers blending along stone surface relief rather than through simple flat fades.
- Rocky grey surfaces on steep terrain.
- Darker terrain in areas where water would naturally accumulate or flow.
- Enhanced definition of ridges, hollows and scree.
- Improved terrain lighting beyond the battle area.
- Terrain normal-map relief contributing to ambient occlusion and contact shadows.

## Trees, Grass and Vegetation

- Distant tree impostors baked from each tree's most detailed model, maintaining accurate appearance from every viewing angle, including from above.
- Impostors receive lighting consistent with nearby detailed trees.
- Configurable tree LOD levels before impostors take over.
- Scrub and low woodland extending beyond the battle area according to terrain conditions.
- Wind-driven tree animation, with swaying crowns and fluttering leaves.
- Grass animation driven by the same wind as trees.
- Softer leaf and grass edges.
- Smooth transitions between detailed trees and distant impostors, including MSAA support.
- Sunlight transmission through backlit leaves and grass blades.
- Butterflies, dragonflies and hawkmoths flying over grass and around trees.

## Sky, Fog and Weather

- Physically based sky and atmosphere.
- Dynamic clouds moving according to each sky's wind conditions.
- Height fog, densest near the ground and progressively thinning with height, following terrain contours and receiving sunlight and sky illumination.
- Low-altitude drifting mist.
- Sunbeams through cloud gaps and tree canopies.
- Smoke, dust and other battlefield effects fading naturally into atmospheric fog.
- Dynamic lighting applied to the game's existing mist patches.
- Physically bright sun, maintaining a consistent appearance in fog.
- Lightning during storms, with sky and ground flashes and thunder delayed according to distance.
- Physically positioned primary and secondary rainbows, appearing when rain and sun conditions are appropriate.
- Auroras on clear winter nights, featuring animated curtains and subtle illumination on terrain and clouds.
- Starlight from the Milky Way illuminating clouds and fog at night, following each sky's star brightness.
- Aurora illumination affecting clouds.

## Water

- FFT-based ocean wave simulation.
- Calmer, shorter waves for rivers and lakes.
- New physically based water material.
- Smooth wave detail at close range, without repeating wave patterns towards the horizon.
- Reflections of moving skies and clouds, including off-screen portions of the sky.
- Cloud shadows affecting water surfaces.

## Battlefield Effects

- Persistent blood decals on the ground where soldiers fight.
- Blood decals with surface relief and specular highlights, allowing wet blood to catch sunlight.
- Configurable persistence duration for arrows embedded in the ground.
- Siege impact effects, including craters and scorch marks where onager rocks land.
- Landed siege projectiles and ammunition remaining on the battlefield, including rocks, bolts, javelins and pila.
- Animated butterflies, dragonflies and hawkmoths across the battlefield.

## Image and Post-Processing

- Four tone-mapping operators:
  - Original game tone mapping.
  - AgX.
  - ACES 2.0.
  - GT7.
- Hue-preserving highlight roll-off, retaining colour detail in bright areas instead of clipping to white.
- Stable image brightness as the sun enters and leaves the camera's view.
- New bloom with smooth, stable transitions and no sudden appearance or disappearance.
- Optional FFT bloom, adding glare streaks and starburst effects around bright light sources.
- Physically simulated lens flare, tracing light through a real camera lens design, with colour influenced by lens coatings and visibility affected by trees, buildings and clouds.
- CMAA2 anti-aliasing as an alternative to the game's FXAA.
- Rain on the camera lens, with realistic drops on the front glass during battles in rainy conditions. Does not affect the interface.
- Clean silhouettes of units and trees against the sky.

## Optional Rendering Corrections

These options are disabled by default and can be enabled individually.

- Preserve brightness on rough surfaces.
- Match normal-map strength to the game's original rendering pipeline.
- Correct bump-map direction on buildings.
- Render the back faces of soldier model parts.

## In-Game Overlay

- Unified RIS configuration overlay, accessible through the `Home` key.
- Separate **Units** and **Buildings** configuration tabs.
- Live enabling and disabling of individual rendering features.
- Per-pass GPU/rendering timings in the Performance view, available as an optional overlay feature.
- Save buttons across all tabs, each saving all three `.ini` configuration files.

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
