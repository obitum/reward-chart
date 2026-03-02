# Minecraft Reward Chart

A Minecraft-themed reward chart for kids. Click blocks to "mine" them and track progress toward 101 blocks.

## Architecture

Simple web app with `index.html` (markup and JS) and `styles.css`. No build tools, no frameworks, no dependencies. Opens directly in a browser.

- State is persisted in `localStorage` under the key `minecraftRewards` (array of completed block numbers).
- All textures and sounds are sourced from [minecraft-assets (1.20.6)](https://github.com/InventivetalentDev/minecraft-assets/blob/1.20.6/assets/minecraft) and rendered with `image-rendering: pixelated`.

## How It Works

- 101 blocks in a 10-column grid, textured in geological layers (grass, dirt, cobblestone, deepslate).
- Milestone blocks (31, 51, 71, 81, 91, 101) use ore textures.
- Clicking a block toggles it mined/unmined with a stone-dig sound.
- A TNT-styled reset button triggers an animated sequence: random TNT placement, fuse sound, flashing, layered explosion sprites, then full reset.

## Asset Structure

```
assets/
  textures/
    blocks/        — block face textures (grass, dirt, ores, tnt, etc.)
    cursors/       — diamond pickaxe cursor images
  sounds/
    dig/           — stone dig sounds (stone1-4.ogg)
    explosion/     — explode1-4.ogg, fuse.ogg
  sprites/
    explosion/     — explosion_0 through explosion_15.png (sprite frames)
```

## Conventions

- CSS lives in `assets/styles.css`, JS stays inline in `index.html`.
- Use vanilla HTML/CSS/JS only. No libraries or frameworks.
- Minecraft aesthetic: pixelated rendering, authentic textures and sounds, blocky UI.
- Custom cursor (diamond pickaxe) on all interactive elements.
