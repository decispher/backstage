---
'@backstage/plugin-catalog-backend': patch
---

Moved the `next_stitch_at` stitch queue column from `refresh_state` to the `final_entities` table, and removed `next_stitch_ticket` from `refresh_state` in favor of reusing the existing `stitch_ticket` column in `final_entities` for the same purpose. This change improves semantic alignment since stitching operates on a per-entity-ref basis and the output belongs to `final_entities`. The migration handles existing data and is fully reversible.
