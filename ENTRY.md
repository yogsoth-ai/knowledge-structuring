---
name: knowledge-structuring
description: Research Knowledge Structuring Engine — organizes acquired knowledge into ontologies, causal models, dimensional analyses, and argument maps via a structured wiki vault. Use this when you need to structure, organize, or systematize research knowledge beyond simple note-taking.
---

# Knowledge Structuring

Transforms raw research knowledge into structured, queryable representations. Four campaigns address complementary structuring needs — use one or combine them depending on the research phase.

## Campaign Routing

| Signal | Campaign |
|--------|----------|
| 构建本体、define concepts、taxonomy、classify | → ontology-building |
| 因果关系、causal mechanism、intervention、why does X cause Y | → causal-modeling |
| 维度分析、design space、combinations、what axes exist | → dimensional-analysis |
| 论证结构、claims、evidence strength、argument map | → argument-mapping |

## MCP Dependencies

| Server | Purpose |
|--------|---------|
| wiki-vault | Knowledge storage, search, graph, lint |
| brave-search | Web research for structuring evidence |
| apify | Google Scholar search |
| alphaxiv | arXiv paper content and search |
| semantic-scholar | Citation tracing, paper metadata |

## Topic-Size Classification

Classify the structuring task at campaign start. Size propagates to all strategies for budget tier selection.

| Size | Criteria | Example |
|------|----------|---------|
| Small | Single concept cluster, <20 source pages | "Structure attention mechanism variants" |
| Medium | Multi-concept domain, 20-50 source pages | "Build ontology of transformer architectures" |
| Large | Cross-domain, 50+ source pages | "Map causal relationships in protein folding" |

## Context-Management Protocol

- **Campaign start**: `context-init` — load or create campaign context file
- **After each strategy**: `context-checkpoint` + `knowledge-compilation` (wiki-vault tactic)
- **Campaign end**: final `context-checkpoint` with summary metrics

## Four-Level Hierarchy

```
ENTRY.md (this file) — campaign routing
  → Campaign (4): domain-specific structuring programs
    → Strategy (16): phased approaches with budgets
      → Tactic (10): multi-SOP orchestration patterns
        → SOP (32): single-responsibility operations
```

All skills are flat in `skills/`. Hierarchy is expressed via frontmatter `used-by` fields.

## Shared Principles

- **兵法书, not pipeline.** Skills teach principles. CC decides execution strategy autonomously.
- **Single unified vault.** All campaigns write to the same wiki-vault. Cross-campaign connections are a feature.
- **Budget enforcement.** Every strategy has S/M/L budget floors. Cannot exit until 80% met.
- **State Ledger.** Print progress before each iteration decision.
- **Adversarial Completeness Probe.** After budget gate passes, qualitative self-check for blind spots.
