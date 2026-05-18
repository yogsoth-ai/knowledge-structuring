---
name: edge-batch-creation
description: SOP for creating multiple edges in a batch — efficient bulk relationship creation.
execution: sop
used-by: relation-typing, hierarchy-construction, concept-decomposition
---

# Edge Batch Creation

Create multiple edges efficiently. Used when a set of relationships has been identified and needs to be committed to the graph.

## Tool

`vault_add_edge` (called multiple times)

## Protocol

1. Receive list of (source, target, edge_type) triples
2. Validate all paths exist
3. Call vault_add_edge for each triple
4. Report successes and failures (duplicates are expected, not errors)

## HARD-GATE

<HARD-GATE>
All source and target paths must exist before batch creation begins.
Validate the full batch upfront, not one-by-one.
</HARD-GATE>

## Yield

Returns: `{ attempted: number, created: number, duplicates_skipped: number }`
