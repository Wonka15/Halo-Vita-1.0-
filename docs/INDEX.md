# Project documentation index

A short map of the documentation in this repository. The root
[README](../README.md) is the project landing page; this page is the directory
for deeper material.

## Getting oriented

- [Repository overview](../README.md) — what this fork is and where to begin.
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

## Engine areas

| Area | Where to look |
| --- | --- |
| Vita graphics backend | `port/vita/host/vita_gxm.c` |
| Direct3D 8 compatibility layer | `port/vita/platform/d3d8_gxm.c` |
| Vita graphics interface | `port/vita/include/vita_gxm.h` |
| Vertex shader translation | `port/vita/platform/nv2a_vsh_cg.c` |
| Pixel shader translation | `port/vita/platform/nv2a_psh_cg.c` |
| Vita-specific overview | [port/vita/README.md](../port/vita/README.md) |

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
2. Read the Vita platform README.
3. Open the engine files listed above to follow a specific subsystem.
4. Use the research notes for deeper investigations.
5. Check the roadmap before treating an idea as implemented.
