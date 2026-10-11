# Mira-Main

Paper-based Minecraft server development for the Mira Factions ecosystem, targeting **Minecraft 26.2** with a future **classic 1.7-style cannoning** profile.

## Current Release

**Development baseline only.** Our first build is a pinned, unmodified Paper 26.2 server JAR. **Fuji/Sakura cannon physics have not been ported** and old Factions cannons are not yet validated.

[View releases](https://github.com/FiveSOCE/Mira-Main/releases)

## JAR Download

A direct JAR download will be added here once the CI build succeeds and a release asset has been verified.

[Build status](https://github.com/FiveSOCE/Mira-Main/actions/workflows/build-26.2.yml)

## Requirements

- Java 25
- Minecraft 26.2 server target
- GitHub Actions build runner or a local JDK 25 build environment

## Cannoning

Planned: legacy TNT impulse and water behaviour, sand stacking, collision handling, redstone timing, reliable explosions and cannon benchmarks. **Not yet implemented.**

## Upstream Sources

- [Paper](https://github.com/PaperMC/Paper) for the 26.2 baseline
- [Fuji](https://github.com/BadgersMC/Fuji) as a 1.21.11 Leaf + Sakura cannoning integration reference
- [Sakura](https://github.com/Samsuik/Sakura) for cannon physics implementation and newer-version comparisons

See [source pins](upstream-lock.yml) and [porting roadmap](docs/PORTING.md).

## Building

The workflow checks out a pinned Paper 26.2 commit and executes:

```bash
./gradlew applyPatches --no-daemon
./gradlew createPaperclipJar --no-daemon
```

The output is verified and released only if compilation passes.

## License

The server fork must preserve applicable Paper, Fuji, Sakura and other upstream licensing and attribution, including any GPL requirements. We cannot distribute modified GPL-covered server code under the usual FiveSOCE All Rights Reserved plugin licence.
