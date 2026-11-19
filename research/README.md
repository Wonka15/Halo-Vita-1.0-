# Research workspace index

The `research/` directory is an engineering evidence archive, not a beginner tutorial. It contains compiler experiments, object/function reconstruction work, verification scripts, logs, and preserved intermediate artifacts.

**Start here:** read the short descriptions below, then open the folder's own README or report when one exists. Treat dated results as historical snapshots until they are re-run against the current source and toolchain.

## Main research groups

### Large reconstruction workspaces

| Folder | Contents | Notes |
|---|---|---|
| [`fifty_objects_20260925/`](fifty_objects_20260925/) | Large object/function reconstruction workspace | Very large evidence and worker tree; inspect its internal manifests and reports before changing anything. |
| [`fifty_objects_r2_20260924/`](fifty_objects_r2_20260924/) | Second reconstruction workspace / review round | Preserved as a separate round; do not merge it into the first workspace without comparing provenance. |
| [`compiler_application_20260925/`](compiler_application_20260925/) | Compiler-application experiments and supporting artifacts | Large dated experiment set; use its manifests and verification outputs to establish status. |

### Compiler and reconstruction investigations

| Folder | Contents |
|---|---|
| [`astra_breakthroughs_20260925/`](astra_breakthroughs_20260925/) | Compiler behavior, frame allocation, decal clipping, ABI census, and experiment controls. Has its own README. |
| [`astra_breakthroughs_20260925_r2/`](astra_breakthroughs_20260925_r2/) | Follow-up research round with narrower compiler-mechanism hypotheses. Has its own README. |
| [`astra_bitmap_autoaim_reconcile_20260926/`](astra_bitmap_autoaim_reconcile_20260926/) | Bitmap / auto-aim reconciliation evidence. |
| [`astra_compiler_application_reconcile_20260926/`](astra_compiler_application_reconcile_20260926/) | Compiler-application reconciliation notes. |
| [`astra_five_functions_20260926/`](astra_five_functions_20260926/) | Focused five-function investigation. |
| [`astra_frontier_pair_reconcile_20260926/`](astra_frontier_pair_reconcile_20260926/) | Paired frontier reconciliation work. |
| [`astra_frontier_reconcile_20260926/`](astra_frontier_reconcile_20260926/) | Frontier reconciliation evidence. |
| [`astra_get_pixel_disclosure_20260927/`](astra_get_pixel_disclosure_20260927/) | Get-pixel disclosure / investigation artifact. |

### Focused technical studies

| Folder | Contents |
|---|---|
| [`breakable_surfaces_closeout/`](breakable_surfaces_closeout/) | Evidence supporting the breakable-surfaces reconstruction. Start with its README. |
| [`circular_queue_obj/`](circular_queue_obj/) | Circular queue object investigation. |
| [`data_decode_memory_codegen/`](data_decode_memory_codegen/) | Data decoding and memory/code-generation notes. |
| [`data_packets_allocator_fixture/`](data_packets_allocator_fixture/) | Allocator fixture for data-packet work. |
| [`data_packets_verifier_init/`](data_packets_verifier_init/) | Verifier initialization investigation. |
| [`halo_r3_20260924/`](halo_r3_20260924/) | Halo R3 dated research snapshot. |
| [`public_key_crypt/`](public_key_crypt/) | Public-key cryptography investigation. |
| [`reconstructions/`](reconstructions/) | Small collection of reconstruction artifacts. |

## Standalone research files

- [`asm_credited_functions_audit.md`](asm_credited_functions_audit.md) — assembly / credited-function audit.
- [`PROMPT_fable5_finish_units_obj_20260826.md`](PROMPT_fable5_finish_units_obj_20260826.md) — preserved task prompt for the Fable 5 units-object work.

## How to read a research result

Before treating a result as a current fact, check:

1. **Baseline:** which commit, binary, source tree, and compiler version were used?
2. **Scope:** is this one function, one object, one translation unit, or a whole-program result?
3. **Evidence:** is the result measured, inferred, proposed, or explicitly rejected?
4. **Disposition:** was the change accepted into production, kept only as a research candidate, or parked?
5. **Reproducibility:** are commands, hashes, inputs, and verification outputs preserved?

A matching byte count or local function result is not automatically a verified whole-project improvement. Keep research-only candidates separate from production changes.

## Folder organization policy

- Keep dated rounds separate so their baselines and provenance remain clear.
- Preserve raw logs, manifests, scripts, and rejected experiments.
- Put a concise README in each substantial new investigation folder.
- Link new investigations from this index.
- Do not delete or consolidate evidence solely to reduce file count.
