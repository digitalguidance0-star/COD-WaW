# Call of Duty WaW Zombies — V15 ONSLAUGHT DIRECTOR

Browser-based Three.js FPS zombie survival sandbox inspired by Call of Duty: World at War Zombies.

This build focuses on high-intensity arcade survival, premium visual atmosphere, modular gameplay systems, and expandable architecture for future versions.

## Author
- `®TSCREATES`
- GitHub: https://github.com/digitalguidance0-star

## Overview
This project is a single-file, ES module-powered FPS experience with:
- Progressive waves
- Multi-weapon inventory
- Deployables (claymores, traps, turrets, portal)
- Powerups and perks
- Boss rounds
- Post-processing and atmospheric FX
- Minimap and survival HUD systems

## Core Gameplay Loop
1. Survive incoming zombie waves.
2. Earn score from hits/kills/headshots.
3. Buy weapons, perks, and utilities.
4. Use tactical tools (knife, trap, turret, portal, grenades, claymores).
5. End wave, receive supply refill, scale into harder rounds.

## Major Systems

### 1) Adaptive Wave Director
- Dynamic round profile generation (`spawnRate`, `totalToSpawn`, `maxAlive`, health/speed scales)
- Wave transition flow with clear-state gating
- Threat/intensity tracking displayed in HUD

### 2) AI Behavior Layer
- Zombie type variants: `normal`, `runner`, `brute`, `boss`
- Stun state handling from weapon impacts
- Group behavior with pack speed bonus
- Separation steering to reduce body-clumping
- Flank bias and obstacle repulsion around interactable props

### 3) Combat Systems
- Hitscan firearm combat with head/body ray checks
- Per-weapon recoil/spread/fire mode logic
- Reload timing and reserve ammo handling
- Melee combat knife (`Y`) with backstab one-hit mechanic
- Combo multiplier scoring system
- Hit marker and damage feedback overlays

### 4) Deployables & Tactical Tools
- Claymores (`F`)
- Electric traps (`G`)
- Tesla turrets (`T`)
- Volatile grenades (`H`)
- Persistent portal device (`Z` place/teleport, `L` pickup)

### 5) Portal Rules (Current Behavior)
- One portal device per game (`maxPortalDevices = 1`)
- Press `Z` first time: place portal
- Press `Z` again: teleport to placed portal every time
- Press `L`: pick up/remove portal so you can place again elsewhere

### 6) Player State
- Health + armor + stamina bars
- Regen delay system
- Downed/bleedout state with self-revive option (`Q`, score cost)
- Sprint and ADS movement modifiers

### 7) Visual & Atmosphere
- Three.js post-processing bloom
- Fog and day/night color cycle
- Thunder flash events + atmosphere pulse
- Rain, ash storm, blood particles, decals, blood pools
- Dynamic vignette and camera shake intensity

### 8) UI/HUD
- Score, round, ammo, weapon, fire mode
- Deployable counters and teleport state
- Threat and combo cards
- Boss health indicator
- Interaction prompt and temporary powerup messaging
- Minimap with perk-based visibility logic

## Controls
- `W A S D`: Move
- `SHIFT`: Sprint
- `SPACE`: Jump
- `Mouse Left`: Fire
- `Mouse Right`: ADS
- `R`: Reload
- `Y`: Melee Combat Knife
- `E`: Interact
- `H`: Throw grenade
- `F`: Place claymore
- `G`: Place trap
- `T`: Place turret
- `Z`: Place portal / teleport to placed portal
- `L`: Pick up portal
- `Q`: Self-revive while downed (score cost)
- `Mouse Wheel` / `1..N`: Weapon switching

## Weapons
- M1911
- MP5
- Double-Barrel
- MP40
- Thompson
- Kar98k
- Strela-P

Weapon handling includes:
- Fire mode (`semi` / `auto`)
- Fire rate
- Spread
- Magazine + reserve
- Recoil behavior

## Perks
- Jugger-Nog
- Speed Cola
- Engineer

## Powerups
- Max Ammo
- Insta-Kill
- Double Points
- Armor Vest
- Volatile Grenade
- Electric Trap
- Tesla Turret
- Portal Device

## Round Supply Rules
At each wave transition, player receives:
- `+3` traps
- `+3` turrets
- `+3` claymores
- `+3` grenades

Portal device is intentionally excluded from round refill.

## Tech Stack
- HTML/CSS/JavaScript (single-file game structure)
- Three.js (`0.150.1`) via ES module import map
- EffectComposer + RenderPass + UnrealBloomPass
- Web Audio API (procedural SFX)

## Project Structure
- `index.html`: Main playable build
- `base.html`: Additional project file (if used for alternate baseline/testing)

## Run Locally
Because browser module policies can block file imports from raw `file://`, use a local server.

Example with Node:
```bash
npx serve .
```
Then open the served URL in a modern browser.

## Browser Recommendations
- Chrome/Edge latest
- Hardware acceleration enabled
- WebGL enabled

## Performance Notes
- Uses delta time clamping in update loop
- Runtime entity cleanup for particles/decals/pools
- Controlled zombie alive cap per round profile
- Scalable architecture favors additive features over rewrites

## Troubleshooting
- No audio: click inside game first to unlock/resume audio context.
- No rendering: verify WebGL is enabled in browser.
- Module import errors: run with a local server, not direct file opening.
- Input not working: ensure pointer lock is active (click game view).

## Roadmap Ideas
- Split systems into module files (`ai/`, `combat/`, `ui/`, `fx/`)
- Add nav-grid/pathfinding for tighter zombie routing
- Add save/load progression and persistent unlocks
- Add configurable graphics tiers and advanced options menu
- Add formal test harness for wave/profile balancing

## Credits
- Project by `®TSCREATES`
- GitHub: https://github.com/digitalguidance0-star
# COD-WaW
