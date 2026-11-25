# Changelog

The major changes to the RIS graphics add-on for Total War: ROME REMASTERED, newest release first.
Every change, small ones included, is in `CHANGELOG_DETAILED.txt` next to this file.
Every feature can be switched on and off live from the in-game overlay (Home key, then the RIS window).

The add-on is in alpha: expect bugs, crashes and look changes between releases.
Versions follow `0.0.N` while the add-on is this unstable: every release, fixes or features, adds 1 to N.
Later stages: `0.1.0` when the alpha is stable enough, `1.0.0-beta.1` for the beta, `1.0.0` for the first stable release.

## 0.0.5 (2026-11-25)

### Added

#### Lighting and shadows

- At a low sun, hills and buildings hide the sun from the ground, soldiers and trees behind them, hundreds of metres away ("Sun hidden by the terrain").
- Up to eight more torches and fires at each spot cast shadows (before only the two strongest did), and every soldier shadows every torch and fire, moving torches included.

#### Buildings

- Near walls, steps and roofs get real depth that shifts with the view and shadows itself at a low sun ("Building parallax").
- Masonry and roof tiles shadow their own grooves at a low sun and darken in cavities ("Building relief").
- Buildings gather grime in creases, wear on their edges, and moss or dust on sheltered ledges by climate ("Building weathering").
- Long walls stop showing their texture repeat in the distance ("Building hex tiling").

#### Soldiers and mounts

- Soldiers and horses show their own blood, which dries over time, and a pool of blood forms where each fallen body lies.
- Blood on the ground spreads out over a few seconds, dries from glossy to dull brown, and also stains grass, bodies and rocks.
- Paint wears off shield rims and armour edges as soldiers fight ("Edge wear").
- Soldiers shed their snow in slides as they march.

#### Snow

- Trees, rocks and still vegetation take snow in snowy battles; trees shake it off as falling flakes and let clumps slide to the ground beneath them.
- Fire melts the snow on nearby roofs, walls, tree crowns and ground.

#### Fire

- Fire-arrow volleys and flaming rocks can set fire to the trees they fly through, and fire arrows to the grass where they land, less often in wet weather.
- A burning tree first smoulders, then burns with steadier flames and smoke, lights its surroundings, and can go out part-way.

#### Image and overlay

- Depth of field in linear light, with no halos or ghost copies around objects (new Camera tab).
- Night shift: at night dim colours fade towards the blue-grey of night vision, while torches keep their colour ("Night shift").
- The Performance tab, with Measure on, shows every add-on effect as its own row with its pixel and triangle counts, each patched feature's cost, and a line in ReShade.log whenever a row spikes.

### Changed

- The tone map offers two curves: the game's own (with colours kept) and GT7.
- Snow builds up twice as fast: full cover in about a minute of heavy snow.
- Panel status lines say Active only when a feature really worked that frame, and Idle with the reason otherwise.
- The panel's search finds every setting by its name, heading, ini key or value.

### Performance

- Battles with many torches and fires use far less CPU for their lights: about 2.8 ms instead of 20 ms at 1,000 lights.
- Features you switch off no longer cost anything in the game's shaders; switching one back on rebuilds the shaders in about a second.
- After a battle the add-on frees about 1.5 GB of video memory it held for the battle (torch shadow maps, screen effects, bounce light).
- No stutter when the panel saves a setting, when the add-on is turned off and on in battle, or when a battle starts.
- Smaller spikes when walls collapse, and cheaper torch and fire shadows in big fires.
- Dry battles skip all the wetness work, and nights skip the sky work that the darkness hides.

### Fixed

- In big night battles burning buildings and fires no longer go unlit, and their light no longer jumps, flickers or collapses to one hot spot.
- Torch and fire shadows hold still with a still camera.
- On moonless nights, reflections in shade are no longer dimmed by a sun or moon that isn't there.
- Pausing a battle stops the fire, smoke and the sway of trees and grass.
- Siege rocks no longer leave lines of craters under their path, and rocks no longer catch fire.
- Charging chariots no longer leave their carts behind.
- Crash risks when ReShade reloads or another program closes its graphics device.

## 0.0.4 (2026-11-21)

New features now start switched on; each keeps its own checkbox, and switching one off gives the previous picture exactly.
The RIS window has a new layout: sections on the left, a search box, and a switch back to the old tabs.

### Added

- Linear light sum: sun, sky and torch light add up as real light does, with Sun scale and Moon scale sliders.
- Torch and fire shadow maps: the torches and fires that light the most of the screen get real shadow maps.
- Terrain weather: the ground gets wet, puddled, streaked and snowed on together with the buildings.
- Fire light comes from the flames, and a carried torch's light stays on its flame.
- Sea waves move the water surface itself near the camera.
- At night the lens flare follows the moon.

### Performance

- Battles with over 10,000 soldiers: soldier tracking costs about 0.5 ms instead of up to 4.2 ms.
- No hitch of about 30 ms when the camera cuts to another place.

### Fixed

- Bounce light crawled on a still camera and left red pools at night.
- Water sparkled, crests were jagged and rivers glowed.
- Crash risks when leaving a battle or loading the next one.

## 0.0.3 (2026-11-16)

### Added

- Street sky visibility and street reflection occlusion: narrow streets, courtyards and gates get less sky light and stop reflecting the open sky.
- Bounce light from what is on screen, and sun and moon bounce into shaded surfaces.
- Torch and fire shadows: torches and fires no longer light through walls.
- Dust, mud, blood, wetness and snow on soldiers and mounts.
- Snow on buildings, and wet buildings with puddles and streaks in rain.
- Rain on the lens.
- Units and Buildings tabs.

### Fixed

- Walls got far too much red ambient light at night.
- A crash when building snow was on together with the street reflection occlusion.

## 0.0.2 (2026-11-13)

The RIS TrueSky and RIS Battlemap add-ons are now a single add-on, `ris.addon64`, with a third part, the Graphics Engine.
Before installing, delete the old `ris_truesky.addon64` and `ris_battlemap.addon64` from the game folder.

### Added

- New ambient occlusion, contact shadows and sun-shadow filtering.
- Ambient light with a direction, and sky reflections that blur with roughness.
- Light through leaves, grass, ears and the thin parts of mounts, and skin and cloth highlights.
- New tone mapping, bloom, a traced lens flare and CMAA2 anti-aliasing.
- Terrain without visible tiling, with natural colour variation and rocky slopes.
- Distant trees drawn as impostors, and scrub continuing past the battle area.
- Height fog, a drifting mist layer, sunbeams through clouds and trees, and starlight.
- FFT ocean waves and a new water material.
- Siege impacts: craters, scorch marks and landed missiles.

## 0.0.1 (2026-11-05): Initial release

### Added

- RIS TrueSky: cloud shadows, rainbows, auroras, drifting clouds, a physically based sky, and lightning with thunder.
- RIS Battlemap: blood on the ground, arrows that stay, trees swaying in the wind, and butterflies.
