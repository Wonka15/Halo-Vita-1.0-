# Halo: Combat Evolved — Vita Edition

**A personal development fork maintained by [Wonka15](https://github.com/Wonka15).**

This repository is a fork of the Halo CE Vita project. It preserves the upstream
codebase and its history while providing a separate place for Wonka15's
experiments, documentation, testing, and future changes.

> **Project status:** This is a source-code fork and development workspace.
> Do not treat it as an official release or assume that a new VPK is available
> unless one is published in this repository's Releases.

## Start here

| I want to… | Go to |
| --- | --- |
| Understand the project and its structure | [Project guide](docs/INDEX.md) |
| Learn how to build and test the Vita port | [Vita platform notes](port/vita/README.md) |
| Review planned work and inherited milestones | [Roadmap](ROADMAP.md) |
| Explore technical notes and investigations | [Research index](docs/INDEX.md#research-and-engineering-notes) |
| Understand credits, copyright, and legal boundaries | [Legal notice](LEGAL.md) · [License](LICENSE) |

## What this project is

Halo: Combat Evolved for PS Vita is a native port built from the decompiled
Xbox game code. It is not an Xbox emulator: the game's code is compiled for
the Vita, while the graphics and platform layers adapt the original systems
to Vita hardware.

This fork is intended for careful learning and development around the
existing codebase, including graphics, performance, compatibility, and
documentation. Changes will be identified as fork-specific work; upstream
authors and contributors remain credited for their work.

## Repository map

| Path | Purpose |
| --- | --- |
| `source/`, `libs/` | Game code and supporting libraries |
| `port/vita/host/` | Vita-specific runtime and GXM renderer |
| `port/vita/platform/` | Vita platform compatibility and graphics translation |
| `port/vita/include/` | Interfaces shared by Vita components |
| `port/` | Platform-specific implementations |
| `tools/`, `config/` | Build, packaging, and project tooling |
| `docs/` | Technical documentation and research notes |
| `research/` | Working investigations and analysis |
| `ROADMAP.md` | Project milestones and planned work |

For a guided explanation of the code, begin with the [project documentation
index](docs/INDEX.md).

## Building

Build requirements and commands can change with the toolchain. Use the
maintained instructions in [port/vita/README.md](port/vita/README.md) and
the relevant platform documentation rather than relying on copied commands
from an older release guide.

## Downloads

There is no claim of a new Wonka15 release in this documentation update.
Check this fork's [Releases](https://github.com/Wonka15/Halo-Vita-1.0-/releases)
for builds published by Wonka15. For upstream releases and their provenance,
consult the upstream project's own release page.

The repository does not include Halo game data. Users must supply their own
lawfully obtained game files. Do not upload or redistribute proprietary game
assets.

## Credits and licensing

This fork builds on work by the original port authors and the wider Halo
decompilation and homebrew communities. See the inherited credits and
attribution in [the reference guide](docs/UPSTREAM_README.md), along with
[LEGAL.md](LEGAL.md).

The repository currently carries **GNU GPL v3**. This cleanup does not change
the license. Preserve the applicable license text, copyright notices, and
third-party license requirements in any redistribution. Fork-specific
changes should be clearly identified so they are not mistaken for upstream
work.

## Contributing to this fork

Before changing engine code:

1. Identify the component and trace its callers.
2. Record the current behavior and a reproducible test case.
3. Make a focused change rather than replacing a subsystem wholesale.
4. Build and test on the Vita where practical; label emulator-only results.
5. Document measured results and keep upstream attribution intact.

No performance improvement should be claimed without a repeatable test.
