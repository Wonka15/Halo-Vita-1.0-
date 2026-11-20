# Project documentation index

A short map of the documentation in this repository. The root
[README](../README.md) is the project landing page; this page is the directory
for deeper material.

## Color-coded technical guides

The [Engine guide](ENGINE_GUIDE.md) is the beginner-friendly source map.
It uses a consistent color key:

| Color | Category | Start here |
| --- | --- | --- |
| 🔵 Blue | Graphics and rendering | `d3d8_gxm.c`, `vita_gxm.c`, `vita_gxm.h` |
| 🟣 Purple | Shaders and visual effects | `nv2a_vsh_cg.c`, `nv2a_psh_cg.c`, `vita_shader_cache.c` |
| 🟢 Green | Memory, textures, and assets | `vita_textures.c`, `vgxm_memory.h`, `vita_memory_watch.c` |
| 🟠 Orange | CPU and performance | `vita_cpu.c`, `vita_clocks.c`, `dynamic_resolution.c` |
| 🔷 Teal | Input, audio, and networking | `vita_controls.c`, `vita_input.c`, `vita_net.c` |
| ⚪ Gray | Build, testing, and reference | platform README, roadmap, legal and license files |

## Getting oriented

- [Repository overview](../README.md) — what this fork is and where to begin.
- [Engine guide](ENGINE_GUIDE.md) — how the major Vita systems fit together.
- [Vita platform notes](../port/vita/README.md) — Vita-specific architecture,
  build details, runtime behavior, and testing.
- [Roadmap](../ROADMAP.md) — inherited milestones and recorded future ideas.
- [Legal notice](../LEGAL.md) — project purpose, game-data boundaries, and
  intellectual-property notice.
- [License](../LICENSE) — GNU GPL v3 currently used by this repository.
- [Inherited README snapshot](UPSTREAM_README.md) — the long-form guide
  preserved from before the Wonka15 landing-page cleanup. Check its release
  links and version-specific instructions against the relevant upstream
  release before relying on them.

## Research and engineering notes

The `docs/` and `research/` directories contain detailed investigations,
test notes, comparison material, and working records. They are intentionally
kept separate from the main landing page so readers can start with the
high-level documentation and open specialist notes only when needed.

Useful entry points include:

- [Custom Edition cache notes](custom_edition_caches.md)
- [Crossplay notes](crossplay.md)
- [Matching methodology](matching_methodology.md)
- [Common constants](common_constants.md)
- [Assertions](assertions.md)

Research folders may contain intermediate or historical work. Treat
conclusions as provisional unless the document records a reproducible
verification and its current status.

## Suggested reading order

1. Read the root README.
2. Read the [color-coded engine guide](ENGINE_GUIDE.md).
3. Read the Vita platform README.
4. Open source files from one color category at a time.
5. Use research notes for deeper investigations.
6. Check the roadmap before treating an idea as implemented.
