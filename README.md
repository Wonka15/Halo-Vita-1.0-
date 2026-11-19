<div align="center">

<img src="docs/logo.png" alt="Halo CE for PS Vita logo" width="150">

# Halo CE Vita — Wonka15 Development

**An independent development workspace for learning, experimentation, performance research, and real-hardware testing on PlayStation Vita.**

[![License: GPL-3.0-only](https://img.shields.io/badge/license-GPL--3.0--only-orange)](LICENSE)
[![Platform: PS Vita](https://img.shields.io/badge/platform-PS%20Vita%20%2F%20PS%20TV-003791)](#project-focus)

</div>

> **Project lineage:** This repository is an independent development copy based on the [original Halo CE Vita project](https://github.com/BirchWoodGod/halo-ce-vita). Original work, releases, contributors, and licensing remain credited to their respective authors. This repository is not the upstream project.

> **Game data:** No proprietary Halo game data is included. You must supply your own legally acquired game files. See the [installation and user guide](docs/USER_GUIDE.md).

## Start here

| I want to… | Go to |
|---|---|
| Understand the project and its current direction | [Project focus](#project-focus) |
| Install or play the existing Vita build | [Installation guide](docs/USER_GUIDE.md#install) |
| Learn controls, settings, multiplayer, and performance options | [Player guide](docs/USER_GUIDE.md) |
| Build the project from source | [Build instructions](docs/USER_GUIDE.md#building) |
| See planned work and known follow-ups | [Roadmap](ROADMAP.md) |
| Browse technical notes and research | [Documentation index](docs/INDEX.md) |
| Report a problem or suggest a change | [GitHub Issues](https://github.com/Wonka15/Halo-Vita-1.0-/issues) |

## Project focus

The `ndev` branch is the main personal development workspace. The goal is to make careful, measurable improvements while keeping the original project's history and contributions clear.

- **Real Vita testing:** prioritize tests on physical PS Vita hardware; emulator results alone do not confirm compatibility.
- **Fat and Slim comparisons:** record the hardware model used for each test.
- **Performance research:** investigate frame rate, frame pacing, loading, resolution, memory use, and graphics settings.
- **Reproducible changes:** document what changed, why it changed, and how it was tested.
- **Clear documentation:** keep the front page short and put detailed procedures in dedicated guides.

### Testing policy

A feature or performance improvement is not considered verified until it has been tested. Benchmark notes should record the Vita model, build or commit, settings, test area, and measurement method whenever possible.

## Repository map

| Folder / file | What it contains |
|---|---|
| `port/` | Platform-specific code, including the Vita port |
| `source/` | Decompiled game engine source |
| `libs/` | Supporting libraries and compatibility code |
| `tools/` | Build, audit, and development tools |
| `docs/` | Guides, technical notes, audits, and screenshots |
| `research/` | Experimental investigations and supporting artifacts |
| `ROADMAP.md` | Project history, planned work, and open tasks |
| `LICENSE` / `LEGAL.md` | License terms and legal project information |

## Releases and downloads

For the original project's official public releases, use the [BirchWoodGod upstream releases page](https://github.com/BirchWoodGod/halo-ce-vita/releases). Do not assume an upstream VPK is a build produced by this repository. Any future Wonka15 builds will be identified separately, with the applicable license and attribution preserved.

## Credits and license

This work builds on substantial prior decompilation, porting, rendering, and community contributions. See the [full credits and acknowledgments](docs/USER_GUIDE.md#credits) and the repository's [GPL-3.0-only license](LICENSE). The game itself and its proprietary assets are not included.
