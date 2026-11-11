# Changelog

## 0.1.1 — 2026-11-11

Current snesrecomp and recomp-ui, and RecompLauncher's recommendations. The
framework brings its access-exact sound timing (a per-clock S-DSP), sprite
priority, brightness-rounding, HDMA and mosaic fixes: over the same test run
2423 of 3000 frames now match snes9x exactly, where 0.1.0 matched 1171. A
game that reads the controller by hand now gets fresh buttons on every read
($4016 strobe), and a save state loaded in another scene is no longer drawn
with the previous scene's registers. Save states from 0.1.0 keep loading,
with the music playing on (the old sound state is converted). With
[RecompLauncher](https://recomplauncher.com) the game builds on the
launcher's setup screen, Play goes straight into the game, Big Picture opens
full screen, and the renderer and shader are on the game's page. Controllers
are no longer read while the window is in the background ([General]
BackgroundInput = 1 restores that); the log keeps the last runs. The update
check on start stays; when RecompLauncher starts the game it leaves updates
to the launcher.

## 0.1.0 — 2026-11-06

First release: a setup pack that recompiles the game from your own ROM. Boots
through the Delphine and U.S. Gold logos, the opening cutscenes and the title
screen into the levels, at full speed; checked against snes9x with the same
input (same pictures, same pace). The cartridge has no battery: the game gives
passwords, and save states are kept in `build\saves\`. A fresh install starts
with no shader (the plain picture); scanline, CRT and upscaler presets
(ScaleFX, NNEDI3) are in Settings → Shader. Settings during play (Ctrl+L or
Select+L3), and a setting that needs a restart comes back to the same moment;
audio interpolation (I key: Gaussian, Cubic, Sinc); update check on start that
backs up your saves before installing; asks for the dedicated graphics card
on laptops with two; console-free Windows build.

The game keeps the console's speed (60 frames per second) through the
polygon cutscenes, where the host used to fall about 2% behind.

It ships with every framework fix of the earlier ports (see README → Framework
patches), so the problems found there do not come back here.
