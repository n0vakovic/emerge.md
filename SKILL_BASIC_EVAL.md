---
name: skill-basic-eval
description: Evaluate any AI skill against Anthropic best practices for authoring quality. Use when reviewing, comparing, or improving skills. Scores 10 criteria on a 0-4 scale for a total of /40.
---

# Skill Basic Evaluation Framework

Evaluation based on Anthropic's published best practices for skill authoring.

## Criteria

Score each criterion 0-4. Evidence required for each score.

### 1. Description Quality

| Level | Criteria |
|-------|----------|
| 0 | Missing or empty description |
| 1 | Vague ("helps with projects") |
| 2 | Says what it does but missing trigger phrases |
| 3 | Includes what + when + specific trigger phrases |
| 4 | Specific, third-person, includes triggers, file types, negative triggers, under 1024 chars |

**Check:** Does description answer "what does it do?" AND "when should Claude use it?"
**Check:** Written in third person? (not "I can help" or "You can use")
**Check:** Includes terms users would actually say?

### 2. Conciseness

| Level | Criteria |
|-------|----------|
| 0 | Explains things Claude already knows (what a PDF is, how libraries work) |
| 1 | Some unnecessary context, mostly relevant |
| 2 | Mostly concise, few redundant explanations |
| 3 | Every paragraph justifies its token cost |
| 4 | Minimal, dense, only non-obvious information. Challenge: remove any sentence — does output quality degrade? |

**Check:** Does it explain concepts Claude already knows?
**Check:** Could any section be cut without degrading output?
**Anthropic principle:** "Context window is a public good."

### 3. Progressive Disclosure

| Level | Criteria |
|-------|----------|
| 0 | Everything in one massive file, no structure |
| 1 | Structured SKILL.md but no reference files |
| 2 | References exist but nested more than one level deep |
| 3 | SKILL.md under 500 lines, references one level deep, clear links |
| 4 | SKILL.md is a lean table of contents, references organized by domain, long files have TOC |

**Check:** SKILL.md under 500 lines?
**Check:** All references linked directly from SKILL.md (not nested)?
**Check:** Reference files over 100 lines have table of contents?

### 4. Degrees of Freedom

| Level | Criteria |
|-------|----------|
| 0 | All instructions same specificity regardless of task fragility |
| 1 | Some variation but inconsistent |
| 2 | Generally appropriate but some mismatches |
| 3 | High freedom for judgment tasks, low freedom for fragile operations |
| 4 | Explicitly calibrated per section. Fragile ops have exact scripts, judgment tasks have principles. Documented why. |

**Check:** Are database migrations (fragile) treated differently from code reviews (judgment)?
**Check:** Does it say "run exactly this" for dangerous operations?
**Check:** Does it give room for adaptation where multiple approaches are valid?
**Anthropic analogy:** Narrow bridge with cliffs = low freedom. Open field = high freedom.

### 5. Decision Clarity

| Level | Criteria |
|-------|----------|
| 0 | Linear steps only, no branching |
| 1 | Implicit decision points (reader must infer) |
| 2 | Some if/then but mixed with prose |
| 3 | Explicit conditional workflows with clear criteria |
| 4 | Decision tree with measurable thresholds, fallbacks defined, ambiguous cases addressed |

**Check:** When the task branches, is the branch point explicit?
**Check:** Are thresholds concrete ("if >100K nodes") not vague ("if large dataset")?

### 6. Failure Handling

| Level | Criteria |
|-------|----------|
| 0 | No error handling mentioned |
| 1 | Generic "handle errors" instruction |
| 2 | Common errors listed without solutions |
| 3 | Common errors with specific recovery steps |
| 4 | Errors handled in code (scripts), not just language. Feedback loops: validate → fix → repeat. "Solve, don't punt." |

**Check:** If something fails, does the skill say what to do?
**Check:** Are validation scripts provided for critical operations?
**Check:** Is there a validate → fix → retry loop?
**Anthropic principle:** "Code is deterministic; language interpretation isn't."

### 7. Examples & Specificity

| Level | Criteria |
|-------|----------|
| 0 | No examples |
| 1 | Abstract examples with placeholders ("Project A", "Task 1") |
| 2 | Some concrete examples but incomplete |
| 3 | Concrete input/output pairs for common scenarios |
| 4 | Multiple diverse examples showing range, edge cases covered, examples use real-world entities |

**Check:** Are examples literal input→output pairs?
**Check:** Do examples show the range of valid outputs (not just one pattern)?
**Anthropic principle:** "Avoid offering too many options — provide a default with an escape hatch."

### 8. Consistency & Hygiene

| Level | Criteria |
|-------|----------|
| 0 | Mixed terminology, broken references, time-sensitive info |
| 1 | Mostly consistent but some variations |
| 2 | Consistent terminology, some stale content |
| 3 | One term per concept throughout, no time-sensitive info, forward slashes only |
| 4 | Consistent naming, kebab-case folder, no README.md in skill folder, old patterns in collapsible sections, dependencies listed and verified |

**Check:** Does it mix terms? ("API endpoint" vs "URL" vs "route")
**Check:** Any time-sensitive content? ("Before August 2025...")
**Check:** File paths use forward slashes?
**Check:** Dependencies explicitly listed?

### 9. Model Robustness

| Level | Criteria |
|-------|----------|
| 0 | Only tested with one model or untested |
| 1 | Works with one model class |
| 2 | Works with Sonnet, minor issues elsewhere |
| 3 | Tested across Haiku, Sonnet, Opus with appropriate guidance levels |
| 4 | Adapts guidance density to model capability. Haiku gets more detail, Opus gets less. Documented. |

**Check:** Has it been tested with multiple model sizes?
**Check:** Does instruction density match model capability?
**Anthropic guidance:** "What works perfectly for Opus might need more detail for Haiku."

### 10. Testability

| Level | Criteria |
|-------|----------|
| 0 | No test cases, no success criteria |
| 1 | Informal testing only |
| 2 | Some trigger tests (should/shouldn't trigger) |
| 3 | Trigger tests + functional tests + baseline comparison |
| 4 | Evaluation-driven development. Tests created before documentation. 3+ evaluation scenarios. Measurable success criteria. |

**Check:** Are there defined test cases?
**Check:** Are trigger tests explicit (should trigger on X, should NOT trigger on Y)?
**Check:** Is there a baseline comparison (with vs without skill)?
**Anthropic principle:** "Build evaluations BEFORE writing extensive documentation."

---

## Scoring

| Criterion | Score (0-4) |
|-----------|-------------|
| Description Quality | |
| Conciseness | |
| Progressive Disclosure | |
| Degrees of Freedom | |
| Decision Clarity | |
| Failure Handling | |
| Examples & Specificity | |
| Consistency & Hygiene | |
| Model Robustness | |
| Testability | |
| **Total** | **/40** |

**Interpretation:**
- 0-10: Rough draft — needs structural work before use
- 11-20: Functional — runs but has clear gaps
- 21-30: Solid — follows best practices, ready for production
- 31-40: Exemplary — could be published as a reference skill

---

## Output Format

```
# Skill Basic Evaluation: [name]

## Score: [X/40] — [Rough draft/Functional/Solid/Exemplary]

Strengths:
- [criterion]: [level] — [evidence]

Gaps:
- [criterion]: [level] — [what's missing]

## Recommendations
1. [criterion] [current→target]: [action]
2. [criterion] [current→target]: [action]

## One-line summary
[Score]/40. [Key strength]. [Key gap]. [One recommended action].
```

---

## Sources

- [Complete Guide to Building Skills for Claude (PDF)](https://resources.anthropic.com/hubfs/The-Complete-Guide-to-Building-Skill-for-Claude.pdf?hsLang=en)
- [Skill Authoring Best Practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices)
