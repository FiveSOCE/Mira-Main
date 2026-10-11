# Mira-Main 26.2 cannoning port plan

## Baseline
Start with a pinned Paper 26.2 checkout and a verified, runnable Paperclip JAR.
Do not describe that output as a Fuji-based build or as supporting legacy cannon physics.

## Source audit and patch ordering
1. Compare Fuji's patch inventory against Leaf 1.21.11 and Sakura 1.21.11.
2. Identify Sakura physics patches related to TNT acceleration, water movement, explosion vectors, falling blocks, redstone update order, entity collision and stacking.
3. Diff current Paper 26.2 internals and evaluate whether Sakura 26.3.x already supplies forward-port equivalents.
4. Port only selected cannoning behaviour, small coherent patch sets at a time, preserving original authorship, patch credits and licensing.
5. Run compilation and a headless boot check after each patch set. Do not bundle incompatible optimisations solely to recreate the Fuji brand.

## Acceptance gates
- P0: Build Paper 26.2 Paperclip baseline from pinned source and archive SHA256.
- P1: Start baseline with a fresh world; verify EULA, Java 25 and plugin directory.
- P2: Port legacy TNT/water and falling-block mechanics.
- P3: Port redstone timing and deterministic explosion processing.
- P4: Measure 12 classic reference cannon designs on modified 1.8.8 and target 26.2.
- P5: Validate MiraFactions claims/protection and plugin ecosystem.
- P6: Stress test, document incompatibilities, and publish versioned server release.

## Reference test IDs
C01 dry TNT, C02 water-protected propellant, C03 N/S/E/W, C04 multi-TNT,
C05 sand launch, C06 vertical sand stacker, C07 hybrid cannon,
C08 water-wall breach, C09 redstone timing, C10 compressor,
C11 long range, C12 chunk border.

Record trajectories (tick, position, velocity), priming/detonation tick,
block changes, stack output and mspt. Compare to captured legacy baseline.

## Licensing
Fuji documents GPL-3.0 obligations and notices inherited from its upstream stack.
Paper/Sakura/Fuji may have distinct file-level obligations.
The server fork and corresponding source must preserve relevant upstream licenses,
notices, author credits and source availability. The FiveSOCE exclusive plugin
license must not be applied to the modified GPL-covered server binaries.
