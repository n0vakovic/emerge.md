# Skill Traceability Evaluation Framework

Evaluate a skill's traceability maturity—can you reconstruct what happened and why?

---

## 1) Unified Maturity Rubric

| Level | Name | Core Question | Pass Criteria |
|-------|------|---------------|---------------|
| **0** | None | Does data exist? | No logs, no nodes, `print()` only |
| **1** | Captured | Is output recorded? | Data exists but unstructured or disconnected |
| **2** | Structured | Is schema consistent? | Single script can parse all records |
| **3** | Contextual | Is "why" preserved? | Reasoning retrievable for any decision |
| **4** | Linked | Can you traverse history? | Can group/walk decisions by session or entity |
| **5** | Correctable | Are overrides captured? | Human corrections queryable with before/after |
| **6** | Learning-ready | Can patterns emerge? | Non-author can extract insights from data |

---

## 2) Diagnostic Questions

| Level | Question | Evidence Required |
|-------|----------|-------------------|
| 1 | "What did it output yesterday?" | Can locate the data |
| 2 | "Parse all decisions programmatically" | Script works without special handling |
| 3 | "Why did it make decision X?" | `reasoning` or equivalent exists |
| 4 | "Show me everything from run Y" | Session/run grouping works |
| 5 | "What got corrected last month?" | Query returns override records |
| 6 | "What patterns repeat across runs?" | Analysis possible by someone unfamiliar |

---

## 3) Implementation: JSONL

**Minimum schema by level:**

```python
# Level 2 - Structured
{"timestamp": "ISO8601", "decision": "what"}

# Level 3 - Contextual
{"timestamp": "...", "decision": "...",
 "input": "raw input", "reasoning": "why", "confidence": "high|medium|low"}

# Level 4 - Linked
{"...", "session_id": "uuid", "run_id": "uuid", "skill_version": "1.0.0"}

# Level 5 - Correctable
{"...", "human_override": null | "new_value", "override_at": null | "ISO8601"}
```

**Diagnostic commands:**

```bash
# Level 2: Parseable?
cat skill.jsonl | jq -s 'length'

# Level 3: Reasoning exists?
cat skill.jsonl | jq 'select(.reasoning != null)' | head

# Level 4: Session isolation?
cat skill.jsonl | jq 'select(.session_id == "abc123")'

# Level 5: Corrections queryable?
cat skill.jsonl | jq 'select(.human_override != null)'
```

---

## 4) Implementation: Graph

**Node/edge schema by level:**

```cypher
// Level 2 - Structured
(:Decision {id, timestamp, value})-[:DECIDED_ON]->(:Entity)

// Level 3 - Contextual
(:Decision {reasoning, confidence})
(:Input)-[:TRIGGERED]->(:Decision)

// Level 4 - Linked
(:Session)-[:CONTAINS]->(:Decision)
(:Decision)-[:PRECEDED]->(:Decision)

// Level 5 - Correctable
(:Decision)-[:OVERRIDDEN_BY {reason}]->(:Decision)

// Level 6 - Learning-ready
(:Decision)-[:SIMILAR_TO {score}]->(:Decision)
(:Pattern)-[:EXTRACTED_FROM]->(:Decision)
```

**Diagnostic queries:**

```cypher
-- Level 2: Basic linkage?
MATCH (d:Decision)-[:DECIDED_ON]->(e:Entity)
RETURN e.name, count(d) ORDER BY count(d) DESC

-- Level 4: Session traversal?
MATCH (s:Session)-[:CONTAINS]->(d:Decision)
WHERE s.id = $session_id
RETURN d ORDER BY d.timestamp

-- Level 5: Corrections?
MATCH (d1)-[:OVERRIDDEN_BY]->(d2)
RETURN d1.value, d2.value, count(*)
```

---

## 5) Storage Selection Guide

| Signal | JSONL | Graph |
|--------|:-----:|:-----:|
| Quick start, low ceremony | **yes** | no |
| Append-only audit trail | **yes** | no |
| Entities have relationships | no | **yes** |
| Decisions reference each other | no | **yes** |
| Path traversal needed | no | **yes** |
| Cross-entity patterns | no | **yes** |

**Hybrid pattern:** JSONL for capture (L1-3), graph import for analysis (L4-6).

---

## 6) Common Gaps

| Transition | Typical Blocker |
|------------|-----------------|
| 1→2 | Inconsistent schema, mixed formats |
| 2→3 | No `reasoning` field—can't learn from decisions |
| 3→4 | No session linking—decisions lack context |
| 4→5 | Corrections happen but aren't captured |
| 5→6 | Only author knows how to query (bus factor = 1) |

---

## 7) Output Format

When evaluating a skill's traceability:

```
Skill: [name]
Current level: [0-6]
Evidence: [what you observed]
Key gap: [what's missing for next level]
Recommendation: [specific action]
```

---

*Origin: 2026-01-16 conversation re: unified traceability rubric*
