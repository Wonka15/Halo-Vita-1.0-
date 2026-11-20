# Engine guide — color-coded source map

A beginner-friendly map of the Vita port's major systems. This guide points to
source files; it does not claim that every subsystem has been fully audited.
Use the source and platform notes as the authority when behavior or build
details matter.

## Color key

| Color | Area | What it covers |
| --- | --- | --- |
| 🔵 Blue | Graphics and rendering | Turning game draw requests into Vita GPU work |
| 🟣 Purple | Shaders and visual effects | Translating Xbox shader behavior for the Vita |
| 🟢 Green | Memory, textures, and assets | Storing and moving graphics data |
| 🟠 Orange | CPU and performance | Scheduling, clocks, frame timing, dynamic resolution |
| 🔷 Teal | Input, audio, and networking | Controls, motion input, sound, and communication |
| ⚪ Gray | Build, testing, and reference | Toolchain, platform setup, logs, and test material |

## How the pieces fit together

At a high level, the game asks to draw something. The Vita compatibility layer
prepares the graphics state and data, the shader translation code adapts
Xbox-era shader instructions, and the GXM backend submits GPU commands.

```text
Halo game code
    |
    v
Direct3D 8 compatibility layer
    |                 \
    v                  v
shader translation    prepared draw data
    |                  |
    +--------+---------+
             v
       Vita GXM backend
             |
             v
       PlayStation Vita GPU
             |
             v
          display
```

This is a conceptual map, not a promise that every draw follows one single
linear call path. Follow the actual call sites when debugging a specific issue.

## 🔵 Blue — Graphics and rendering

**Begin here if you want to understand how a frame is drawn.**

| File | Beginner's explanation |
| --- | --- |
| [`d3d8_gxm.c`](../port/vita/platform/d3d8_gxm.c) | Adapts the game's Direct3D 8-style graphics requests to the Vita renderer |
| [`vita_gxm.c`](../port/vita/host/vita_gxm.c) | Vita's GXM backend: prepares GPU programs and submits drawing work |
| [`vita_gxm.h`](../port/vita/include/vita_gxm.h) | Shared interface describing the data passed to the GXM backend |
| [`dynamic_resolution.c`](../port/vita/platform/dynamic_resolution.c) | Logic for adjusting render resolution |
| [`vita_video.c`](../port/vita/platform/vita_video.c) | Vita video/platform integration |

**Learning order:** read the interface header first, then the compatibility
layer, then the GXM backend. Start with one function at a time; do not try to
understand the entire renderer in one sitting.

## 🟣 Purple — Shaders and visual effects

**This is where Xbox graphics behavior is adapted for Vita shader programs.**

| File | Beginner's explanation |
| --- | --- |
| [`nv2a_vsh_cg.c`](../port/vita/platform/nv2a_vsh_cg.c) | Translates Xbox NV2A vertex-shader instructions into Cg shader source |
| [`nv2a_psh_cg.c`](../port/vita/platform/nv2a_psh_cg.c) | Translates pixel-shader and register-combiner behavior |
| [`vita_shader_cache.c`](../port/vita/host/vita_shader_cache.c) | Manages the Vita-side shader cache |
| [`vita_gxm.c`](../port/vita/host/vita_gxm.c) | Connects shader programs to GPU draw operations |

A vertex shader mainly transforms vertices (for example, where a model's
corners appear). A pixel/fragment shader helps determine the final color of
pixels. Lighting, texture sampling, blending, and transparency depend on
correct shader behavior.

## 🟢 Green — Memory, textures, and assets

**This area helps explain loading, memory pressure, and why some scenes are
more expensive than others.**

| File | Beginner's explanation |
| --- | --- |
| [`vita_textures.c`](../port/vita/platform/vita_textures.c) | Vita-specific texture handling |
| [`vgxm_memory.h`](../port/vita/include/vgxm_memory.h) | Memory interface used by the GXM renderer |
| [`vita_memory_watch.c`](../port/vita/platform/vita_memory_watch.c) | Memory-watch/debug support |
| [`vita_movie.c`](../port/vita/host/vita_movie.c) | Movie playback and frame handling |
| [`vita_gxm.c`](../port/vita/host/vita_gxm.c) | GPU resources, render targets, and rendering memory |

Useful questions while reading:
- Is this data stored in system RAM or graphics-accessible memory?
- Is it copied every frame, or reused?
- Who owns the allocation, and who releases it?
- Does the code handle alignment and cache visibility?

Do not change memory allocation rules until the allocation lifetime and GPU
ownership are understood.

## 🟠 Orange — CPU, performance, and frame timing

**Use this category when investigating slowdowns, stutter, or frame pacing.**

| File | Beginner's explanation |
| --- | --- |
| [`vita_cpu.c`](../port/vita/host/vita_cpu.c) | CPU-related platform support |
| [`vita_clocks.c`](../port/vita/host/vita_clocks.c) | Vita clock and frequency handling |
| [`vita_fourth_core.c`](../port/vita/host/vita_fourth_core.c) | Optional helper work using the fourth CPU core when supported |
| [`dynamic_resolution.c`](../port/vita/platform/dynamic_resolution.c) | Resolution adjustment as a graphics-performance tool |
| [`fill_stats.c`](../port/vita/platform/fill_stats.c) | Rendering/fill statistics support |

A slowdown can be CPU-limited, GPU-limited, memory-limited, or caused by
waiting on another thread. Lowering resolution mainly helps when GPU rendering
is the limiting factor; it cannot automatically fix expensive game simulation
or AI work.

**Measurement rule:** record the same scene, settings, device, and test
duration before and after a change. Label emulator results separately from
real Vita results. Never describe an optimization as successful based only on
a code change.

## 🔷 Teal — Input, audio, and networking

**These systems connect the game to the Vita's controls and communication
hardware.**

| File | Beginner's explanation |
| --- | --- |
| [`vita_controls.c`](../port/vita/host/vita_controls.c) | Controller mapping and touch-control support |
| [`vita_input.c`](../port/vita/host/vita_input.c) | Reads and processes Vita input |
| [`vita_pad.c`](../port/vita/platform/vita_pad.c) | Vita controller/platform integration |
| [`vita_net.c`](../port/vita/host/vita_net.c) | Vita networking integration |
| [`vita_ctrl_ports.c`](../port/vita/host/vita_ctrl_ports.c) | Controller port handling |

Audio and game-level networking also involve shared code outside these Vita
host files. Follow the relevant call sites into the shared game and platform
layers rather than assuming the Vita file contains the entire subsystem.

## ⚪ Gray — Build, testing, and reference

| Resource | Why it matters |
| --- | --- |
| [Vita platform README](../port/vita/README.md) | Platform-specific setup, installation, and behavior |
| [Repository README](../README.md) | Project identity and main navigation |
| [Roadmap](../ROADMAP.md) | Existing milestones and planned work |
| [Inherited README snapshot](UPSTREAM_README.md) | Historical long-form documentation; verify release-specific details |
| [License](../LICENSE) | Current repository license and redistribution obligations |
| [Legal notice](../LEGAL.md) | Game-data and intellectual-property boundaries |

## Suggested beginner learning path

1. **Graphics interface:** understand `vita_gxm.h` and the shape of a draw request.
2. **Graphics adapter:** see how `d3d8_gxm.c` prepares graphics work.
3. **GPU backend:** follow `vita_gxm.c` to the GXM draw submission.
4. **Shaders:** inspect the vertex and pixel shader translators.
5. **Memory:** learn how textures, buffers, and render targets are allocated.
6. **Performance:** study dynamic resolution and frame timing only after the
   rendering path makes sense.

## Status labels for future notes

Use these labels consistently in new documentation:

- 🟢 **Verified on hardware** — reproduced on a physical PS Vita; include model,
  settings, build, and test steps.
- 🟡 **Inspected in source** — code path reviewed, but runtime behavior not yet
  reproduced.
- 🔵 **In progress** — investigation or implementation is underway.
- ⚪ **Not tested** — no reliable verification yet.
- 🔴 **Known issue** — reproducible problem with steps and evidence.

A source reading is not a hardware test. Keep those statuses separate.
