# RIS TrueSky Features

Atmospheric and sky effects for Total War: ROME REMASTERED:

- **Cloud shadows on the ground.** Clouds cast accurate shadows onto terrain, units, buildings, and trees using the game's depth buffer and trueSKY's cloud volume.
- **Physical rainbows.** Dynamic primary and secondary rainbows appear under proper rain, sun angles, and atmospheric conditions, fully occluded by terrain.
- **Dynamic auroras.** High-altitude auroral curtains with real-time motion, multi-layer color profiles, and subtle terrain lighting render during clear winter nights.
- **Cloud motion (wind).** TrueSKY cloud layers drift naturally over real-time using preset wind directions and speeds, preventing clouds from locking in place.
- **Physically based sky & atmosphere.** Replaces the default flat Nishita-style scattering with a modern model featuring multiple scattering, stratospheric aerosol, and realistic sunset/twilight hues.
- **Lightning strikes & thunder.** Storm clouds generate realistic stepped and return-stroke lightning bolts, casting dynamic flash illumination across the sky and ground, paired with positional thunder audio.

This add-on is independent of the RIS Battlemap add-on. It uses the same ReShade, runs beside it, and shares no code or settings with it (their settings share one overlay window, a tab each). It writes trueSKY values into the game's memory each frame and injects rendering passes for enhanced lighting and effects, leaving the game executable and original files untouched.

# RIS Battlemap Features

Battlefield effects for Total War: ROME REMASTERED:
- **Blood on the battlefield.** Blood decals are stamped on the ground where soldiers fight, and stay for the rest of the battle.
- **Stuck arrows stay.** Arrows stuck in the ground stay for as long as you choose, instead of vanishing after the game's own time.
- **Trees in the wind.** Battle trees sway: crowns lean and rock, leaves flutter.
- **Butterflies.** Butterflies, a dragonfly and a hawkmoth fly over the grass and by the trees the game draws, each species with its own size, wingbeat and flight.

This add-on is independent of the RIS TrueSky add-on. It uses the same ReShade, runs beside it, and shares no code or settings with it (their settings share one overlay window, a tab each). It reads the game's draw calls and adds draws of its own. It never reads or writes game memory and never changes the exe or any game file.


## Install

1. Install **ReShade 6.8 or later, the "with full add-on support" build**, for `Total War ROME REMASTERED.exe` with the DirectX 10/11/12 API. (Skip this if the RIS TrueSky add-on is already installed.)
2. Run `build.bat`. It needs Visual Studio 2022 Build Tools with "Desktop development with C++".
3. Copy these three items from `build\` into the folder that holds ReShade's `dxgi.dll` (the game folder):
   - `ris_battlemap.addon64`
   - `ris_battlemap.ini`
   - the `ris_battlemap\` folder (the decal textures, in `ris_battlemap\decals\`)
4. In game, press Home, then open the **RIS** window, **Battlemap** tab (shared with the RIS TrueSky add-on's **TrueSky** tab; drag the window into the main overlay to dock it if it opens floating). Changes save to the ini by themselves, and edits to the ini are picked up while the game runs.
