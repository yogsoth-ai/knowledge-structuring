<!-- markdownlint-disable -->

<div align="center">

> *"The art of war teaches us to rely not on the likelihood of the enemy's not coming, but on our own readiness to receive him."* — Sun Tzu

</div>

# 🧠 knowledge-structuring

*Multi-campaign skill repo for structured knowledge construction across research domains.*

**knowledge-structuring is not a pipeline.** It is a collection of campaigns — each a self-contained doctrine for building a specific type of knowledge structure (ontologies, causal models, dimensional matrices, argument maps). CC has full autonomy at the campaign and strategy level. Skills teach principles and provide SOPs; they do not prescribe execution order.

---

## ⚡ What It Does

- 🏗️ **Ontology Building** — extract concepts, type relations, validate taxonomies, refine hierarchies
- 🔗 **Causal Modeling** — identify variables, map mechanisms, collect evidence, analyze interventions
- 📐 **Dimensional Analysis** — discover dimensions, enumerate combinations, score novelty, prioritize gaps
- ⚔️ **Argument Mapping** — extract claims, link evidence, assess strength, synthesize positions
- 📚 **Wiki-Vault Integration** — all campaigns write to a unified vault via embedded wiki-vault skills

---

## 🎯 Design Philosophy

- **兵法书, not pipeline.** Campaigns are teaching material. CC reads them, internalizes the principles, and executes with full autonomy. Only SOPs approach fixed workflows.
- **Single unified vault.** All campaigns write to the same vault. Cross-domain connections emerge naturally from the typed graph.
- **Budget-gated depth.** Every strategy has quantitative floors (S/M/L tiers). Cannot exit until 80% met.
- **Adversarial completeness.** After budget gate passes, a qualitative self-check probes for coverage gaps.
- **State ledger transparency.** Progress is printed before every iteration — no silent drift.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│  CAMPAIGN (4)                                                │
│  ontology-building · causal-modeling · dimensional-analysis  │
│  argument-mapping                                            │
├─────────────────────────────────────────────────────────────┤
│  STRATEGY (16)                                               │
│  domain-scoping · concept-extraction · relation-typing ···   │
│  variable-identification · mechanism-mapping ···             │
│  dimension-discovery · combination-mapping ···               │
│  claim-extraction · evidence-linking-arg ···                 │
├─────────────────────────────────────────────────────────────┤
│  TACTIC (10)                                                 │
│  concept-decomposition · hierarchy-construction ···          │
│  counterfactual-reasoning · evidence-weighing ···            │
│  axis-extraction · matrix-generation ···                     │
│  claim-decomposition · strength-assessment                   │
├─────────────────────────────────────────────────────────────┤
│  SOP (36)                                                    │
│  seed-concept-search · source-gathering · concept-page ···  │
│  variable-page-creation · mechanism-edge-creation ···        │
│  dimension-page-creation · axis-validation ···               │
│  claim-page-creation · evidence-attachment ···               │
├─────────────────────────────────────────────────────────────┤
│  WIKI-VAULT SKILLS (8 embedded)                              │
│  knowledge-compilation · vault-maintenance                   │
│  wiki-search · wiki-graph-query · wiki-add-edge             │
│  wiki-ingest-source · wiki-compile-page · wiki-lint-fix     │
└─────────────────────────────────────────────────────────────┘
```

### Campaigns

| Campaign | Strategies | Tactics | SOPs | Purpose |
|----------|-----------|---------|------|---------|
| ontology-building | 5 | 3 | 10 | Build domain ontologies |
| causal-modeling | 5 | 3 | 10 | Construct causal graphs |
| dimensional-analysis | 3 | 2 | 6 | Map design spaces |
| argument-mapping | 3 | 2 | 6 | Structure debates |

### Enforcement Mechanisms

| Mechanism | Layer | Purpose |
|-----------|-------|---------|
| Budget Table | Campaign | S/M/L quantitative floors per metric |
| State Ledger | Strategy | Progress table printed before every iteration |
| Budget Gate | Strategy | Cannot exit until 80% of targets met |
| Adversarial Probe | Strategy | Qualitative self-check after budget gate |
| Minimum Yield | Tactic | Hard floor on output per invocation |
| HARD-GATE | SOP | Precondition that must be satisfied |

### MCP Dependencies

| Server | Tools Used |
|--------|-----------|
| wiki-vault | vault_search, vault_add_edge, vault_query_graph, vault_graph_stats, vault_lint, vault_index |
| context-management | context-init, context-checkpoint |

---

## 📂 Skill Hierarchy

All skills live flat in `skills/<name>/SKILL.md`. Hierarchy is expressed via frontmatter `used-by` field:

```yaml
---
name: concept-extraction
execution: strategy
used-by: ontology-building    # ← parent campaign
---
```

### Four Levels

| Level | Execution | Autonomy | Count |
|-------|-----------|----------|-------|
| Campaign | campaign | Full — CC decides strategy order, iteration count | 4 |
| Strategy | strategy | High — CC decides tactic selection, iteration within budget | 16 |
| Tactic | tactic | Moderate — CC decides SOP order, has minimum yield | 10 |
| SOP | sop | Low — follows protocol, wraps single tool operation | 36 + 8 |

---

## 🚀 Quick Start

```bash
# Clone
git clone https://github.com/yogsoth-ai/knowledge-structuring.git

# Deploy skills to Claude Code
cp -r skills/* ~/.claude/skills/
```

### Prerequisites

- [wiki-vault](https://github.com/yogsoth-ai/wiki-vault) MCP server running
- [context-management](https://github.com/yogsoth-ai/context-management) available

---

## 📄 License

[Apache-2.0](LICENSE)

---

*Part of the [Yogsoth AI](https://github.com/yogsoth-ai) ecosystem. Built by [Pthahnix](https://github.com/Pthahnix).*
