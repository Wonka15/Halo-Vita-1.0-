<div align="center">

<img src="docs/logo.png" alt="Halo CE for PS Vita logo" width="150">

# Halo CE Vita — Wonka15 Edition

**An independent development edition for PlayStation Vita, focused on learning, experimentation, performance research, and real-hardware testing.**

**Repository owner and edition maintainer: [Wonka15](https://github.com/Wonka15)**

[![License: GPL-3.0-only](https://img.shields.io/badge/license-GPL--3.0--only-orange)](LICENSE)
[![Platform: PS Vita](https://img.shields.io/badge/platform-PS%20Vita%20%2F%20PS%20TV-003791)](#project-focus)

</div>

> **About this edition:** This is Wonka15's independent development edition, based on the [original Halo CE Vita project](https://github.com/BirchWoodGod/halo-ce-vita). Wonka15 maintains this repository and is responsible for changes made specifically in this edition. Original code, releases, contributors, and licensing remain credited to their respective authors. This is not the upstream project.

> **Game files:** No proprietary Halo game data is included. You must provide your own legally obtained game files. See the [player guide](docs/USER_GUIDE.md).

## Start here

| I want to… | Go to |
|---|---|
| Understand this edition | [Project focus](#project-focus) |
| Install and play | [Player guide](docs/USER_GUIDE.md) |
| Build from source | [Build instructions](docs/USER_GUIDE.md#building) |
| See planned work | [Roadmap](ROADMAP.md) |
| Browse research | [Research index](research/README.md) |
| Find technical documentation | [Documentation index](docs/INDEX.md) |
| Report a problem | [GitHub Issues](https://github.com/Wonka15/Halo-Vita-1.0-/issues) |

## Project focus

Wonka15's development work focuses on careful improvements that can be explained and tested.

- **Real hardware first:** test on a physical PS Vita; emulator results alone do not prove compatibility.
- **Fat and Slim:** record which Vita model was used.
- **Performance:** investigate frame rate, frame pacing, loading, resolution, memory, and graphics settings.
- **Clear evidence:** document what changed and how it was tested.
- **Easy to understand:** keep guides short and organize deeper technical material separately.

### Testing policy

Do not describe a feature or performance improvement as verified until it has been tested. Record the Vita model, build, settings, test area, and measurement method whenever possible.

## Repository map

| Location | Purpose |
|---|---|
| `port/` | Platform-specific port code |
| `source/` | Decompiled game engine source |
| `libs/` | Supporting libraries |
| `tools/` | Build and development tools |
| `docs/` | Player guide and technical documentation |
| `research/` | Experiments and engineering evidence |
| `ROADMAP.md` | Project history and planned work |
| `LICENSE` / `LEGAL.md` | License and legal information |

## Original releases

For releases from the original project, visit [BirchWoodGod's releases](https://github.com/BirchWoodGod/halo-ce-vita/releases). Those downloads are not builds made by Wonka15. Any future builds from this edition will be clearly identified.

## Credits and license

This edition builds on the work of the original port author and many other contributors. See the [credits in the player guide](docs/USER_GUIDE.md#credits), the [GPL-3.0-only license](LICENSE), and [legal notes](LEGAL.md). The game and its proprietary assets are not included.
