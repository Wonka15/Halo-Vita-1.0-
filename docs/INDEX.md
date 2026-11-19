# Documentation index

This folder contains player guidance, engineering notes, audits, and historical research. Start with the topic you need rather than reading every file. The documentation tree is intentionally an archive: on this branch snapshot it contains 2,172 files, including 2,128 object-matching log files. You do not need to browse those one by one.

## Player and project documentation

- [Full player and setup guide](USER_GUIDE.md) — installation, game data, PC builds, multiplayer, controls, settings, performance, troubleshooting, building, credits, and license context.
- [Campaign house rules](campaign_house_rules.md) — campaign behavior and implementation notes.
- [Campaign throughput lessons](campaign_throughput_lessons.md) — performance and throughput observations.
- [Crossplay notes](crossplay.md) — networking and cross-platform behavior.
- [Fileshare notes](fileshare-friends.md) — map and file-sharing investigation.
- [Custom Edition cache format](custom_edition_caches.md) — technical notes on Custom Edition map/cache handling.
- [MCC / CEA map notes](mcc_cea_maps.md) — map-format research and compatibility notes.

## Engine, build, and reverse-engineering notes

- [Matching methodology](matching_methodology.md) — methodology used for function and object matching.
- [Exact-match acceleration playbook](exact_match_acceleration_playbook.md) — workflow for accelerating exact-match work.
- [Common constants](common_constants.md) — collected constants and references.
- [Assertions](assertions.md) — assertion-related notes.
- [Object matching logs](object_matching_logs/) — a large evidence archive of per-object and per-function ledgers. **Do not start by opening this folder.** First read the [object matching log guide](object_matching_logs/README.md), then use the [reconciliation queue](reconciliation_queue_20260907.md) to find the relevant work item.
- [Campaign prompts](campaign_prompts/) — prompt and task artifacts.
- [Superpowers notes](superpowers/) — supporting workflow material.

## Networking specifications

- [OpenCE network 32 specification](opence-net32-spec.md)
- [OpenCE network 39 specification](opence-net39-spec.md)
- [OpenCE network 41 specification](opence-net41-spec.md)

## Audits and dated investigations

These are specialist or historical records. They are retained for traceability; they are not all current implementation instructions.

- [Security review: 1.1.1 beta 1](security-review-1.1.1-beta.1.md)
- [Cross-build tag intake](crossbuild_h1_tags_intake_20260906.md)
- [User source reconstruction map](user_source_reconstruction_map_20260906.md)
- [Opus campaign tooling audit](opus_campaign_tooling_audit_20260904.md)
- [Opus unfinished-session reconciliation backlog](opus_unfinished_session_reconciliation_backlog_20260903.md)
- [Reconciliation queue](reconciliation_queue_20260907.md)
- [Common-pool ordering investigation](common_pool_ordering_20260922.md)
- [Linker common comparison baseline](linker_common_comparison_base_20260922.md)
- [Object-diff data relocation investigation](objdiff_data_relocation_defect_20260922.md)
- [Xbox link probe](xbox_link_probe_20260924.md)
- [Shape-transfer executor strategy](shape_transfer_executor_strategy.md)
- [Fake-match review](fake_match_review.md)
- [Players matching notes](players_matching_notes.md)

## Research workspace

The [research index](../research/README.md) is the entry point for experiment folders, reconstruction outputs, and supporting artifacts. It groups the large dated workspaces and focused technical investigations without moving or deleting the underlying evidence.

## Where to begin

1. For playing the game, start with the [user guide](USER_GUIDE.md).
2. For the next development tasks, read [the roadmap](../ROADMAP.md).
3. For technical investigations, choose a topic above and check its date and status before treating it as current.
