---
name: question-generation
description: SOP for generating research questions from promising gaps in the design space.
execution: sop
used-by: matrix-generation, gap-prioritization
---

# Question Generation

Generate actionable research questions from high-scoring gaps in the design space.

## Tool

CC file write + `vault_add_edge`

## Protocol

1. For each priority gap, formulate a research question: "What happens when we combine X with Y?"
2. Write `questions/<question-slug>.md` with frontmatter (type: question)
3. Body: the question, why it's interesting, what we'd need to answer it
4. Add edges: raises (gap → question), related_to (question → relevant dimensions)

## HARD-GATE

<HARD-GATE>
Questions must be specific and answerable, not vague. "How does X work?" is too broad.
"What is the effect of combining local attention with graph-based routing?" is specific.
</HARD-GATE>

## Yield

Returns: `{ questions_created: number, paths: string[] }`
