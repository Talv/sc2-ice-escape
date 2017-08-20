# Slide Escape Framework for Starcraft II

Brings rich set of utilities for making Ice Escape like maps on Starcraft II engine.

It's current configuration is made to recreate **Ice Baneling Escape** map design invented by **DeltaVelocity**. Although it was planned to also support other variants of Ice Escape like maps.

## Notable features

### Automatic terrain texture recognition

The native API function `string TerrainTexture (point pos);` has its precision limited to one square (IBE map size 256x256 - max.). Thus it's unusable for pathes, curves etc. Because the square in reality is built with 8x8 pixels.

To solve this problem a custom tool was made. To provide complete texture map data to be accessible from `Galaxy` code. Tool is available to download in its own repo: [sc2-texture-scanner](https://github.com/Talv/sc2-texture-scanner/releases)

------

### Basics

- Challenge system with automatic cleanup
- ...

---

### Unit controllers

- Routing
    - robust applying sets of orders - by providing point range
    - automatic looping: forward, backward
- Random move zones
- Stalker zones - for units triggered when passing by (such as feederlings/creepers in IBE)
- Sequence executors - for animations w/o issuing any orders

------

### Environmental Objects

- Creatures (any native SC2 unit can be used)
- Static obstacles (bushes, Dark Templars)
- Catapults
- Jump zones (cliff jumps)
- Buttons (several variants: push, hold, press)
- Gates
- Portals
- Turn forcers (direction arrows)
- Imitators: figures made of single components - such as crystal rings
- Spikes
- Powerups
- Dynamic surfaces - currently limited to movable Ice of fixed size and shape.
- Flamethrowers
- Electric fence

## Tutorial & Documentation

Proper docs are yet to be made. But here is something to get you started:

1. [Download mods & example map](https://gitlab.com/Talv/sc2-sef/repository/master/archive.zip) from this repository
2. Copy `SEF-IBE.SC2Mod` and `SEF-IBE-Assets.SC2Mod` into `Mods` folder in your SC2 directory.
3. Open in editor `Example-map-cv.SC2Map` which contains 6 challenges from *Cold Voyage*. Try to learn basing on examples! By modifying existing stuff.

*(Any changes made to terrain textures require rebuild of internal mappings used for collisions. Use mentioned tool: [sc2-texture-scanner](https://github.com/Talv/sc2-texture-scanner/releases))*

## Following arcade maps are based on this framework
- *Back to Brood Ice Escape*
- *Ice Baneling Escape: Cold Voyage*

## Credits
- **DeltaVelocity** - There simply would be nothing without him.
- **Chioy** - Designed pretty much all of the challenges for *Back to Brood Ice Escape* and *Ice Baneling Escape: Cold Voyage*.
- **Delphinium** and **NanaKey** - Provided 3d models of pillar & lighting beam used for electric fence.