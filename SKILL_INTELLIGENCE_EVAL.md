# Skill Intelligence Evaluation Framework

Evaluate whether a workflow *feels* intelligent—appropriate behavior without explicit instruction.

---

## 1) Intelligence Qualities

| Quality | What It Means | Absence Feels Like |
|---------|---------------|-------------------|
| **Memory** | Adapts from past corrections | Repeating the same mistakes |
| **Calibration** | Friction matches confidence | Everything gets same treatment |
| **Voice** | Uses your terms, not generic | Talking to a stranger |
| **Awareness** | Notices session/context patterns | Oblivious to what's happening |
| **Connection** | Links across time and entities | Every item is isolated |
| **Humility** | Knows its limits, says so | Confidently wrong |
| **Flexibility** | Adapts pace/batch to you | Rigid, one-size-fits-all |
| **Agency** | Suggests improvements to itself and the system | Waits to be told everything |
| **Restraint** | Disappears when not needed | Always present, always asking |
| **Predictability** | Behavior user can anticipate | Surprising in unwanted ways |
| **Resourceful** | Discovers, uses, and seeks available sources, tools, and capabilities | Works with limited means, ignores available help |

---

## 2) Maturity Levels Per Quality

### Memory

| Level | Behavior |
|-------|----------|
| 0 | No memory. Each run independent. |
| 1 | Logs corrections but doesn't use them. |
| 2 | Uses corrections within session. |
| 3 | Persists corrections across sessions. |
| 4 | Generalizes patterns from corrections. |

**Diagnostic:** "I corrected this same thing last week. Did it learn?"

---

### Calibration

| Level | Behavior |
|-------|----------|
| 0 | Same friction for everything. |
| 1 | Has confidence scores but doesn't act on them. |
| 2 | Shows confidence to user ("high/low"). |
| 3 | Adjusts friction based on confidence (auto-approve high, review low). |
| 4 | Calibrates confidence model from outcomes. |

**Diagnostic:** "Does it ask me about things it should know? Does it auto-handle things it's sure about?"

---

### Voice

| Level | Behavior |
|-------|----------|
| 0 | Generic language, no personalization. |
| 1 | Accepts custom terms when told. |
| 2 | Remembers terms within session. |
| 3 | Persists vocabulary across sessions. |
| 4 | Adopts your patterns without being told. |

**Diagnostic:** "Does it use 'homotechno' or 'human-technology integration'?"

---

### Awareness

| Level | Behavior |
|-------|----------|
| 0 | No session awareness. |
| 1 | Tracks basic session stats. |
| 2 | Notices patterns ("you're saving a lot of X"). |
| 3 | Adapts behavior to session context. |
| 4 | Anticipates based on context ("focus mode?"). |

**Diagnostic:** "Does it notice when this session is different from usual?"

---

### Connection

| Level | Behavior |
|-------|----------|
| 0 | Each item isolated. |
| 1 | Links items within same run. |
| 2 | Links to recent history (last week). |
| 3 | Links across full history. |
| 4 | Surfaces non-obvious connections. |

**Diagnostic:** "Does it know I saved something similar before?"

---

### Humility

| Level | Behavior |
|-------|----------|
| 0 | Always confident, often wrong. |
| 1 | Has confidence scores internally. |
| 2 | Expresses uncertainty to user. |
| 3 | Degrades gracefully (pass-through when unsure). |
| 4 | Explains what it can't do and why. |

**Diagnostic:** "When it doesn't know, does it admit it or guess?"

---

### Flexibility

| Level | Behavior |
|-------|----------|
| 0 | Fixed batch size, fixed flow. |
| 1 | Configurable parameters. |
| 2 | Suggests adjustments based on feedback. |
| 3 | Auto-adjusts within session. |
| 4 | Learns optimal parameters per user/context. |

**Diagnostic:** "Does batch size adapt to how I'm doing?"

---

### Agency

| Level | Behavior |
|-------|----------|
| 0 | Only does what it's told. |
| 1 | Logs potential improvements. |
| 2 | Surfaces suggestions for self-improvement when asked. |
| 3 | Proactively suggests improvements to itself. |
| 4 | Suggests structural/process improvements to the broader system. |

**Diagnostic:** "Has it suggested updating its own rules? Has it proposed changes to how work is organized?"

---

### Restraint

| Level | Behavior |
|-------|----------|
| 0 | Always active, always asking. |
| 1 | Can be configured to run silently. |
| 2 | Defaults to silent for stable patterns. |
| 3 | Surfaces only exceptions. |
| 4 | Knows when user wants engagement vs. automation. |

**Diagnostic:** "Does it disappear when it should? Does it show up when needed?"

---

### Predictability

| Level | Behavior |
|-------|----------|
| 0 | Behavior varies unexpectedly. User can't anticipate. |
| 1 | Consistent within session, varies across sessions. |
| 2 | Documented behavior, user can learn the rules. |
| 3 | Explains what it will do before doing it. |
| 4 | User can accurately predict behavior in new situations. |

**Diagnostic:** "Can I guess what it will do next? Am I surprised in bad ways?"

---

### Resourceful

| Level | Behavior |
|-------|----------|
| 0 | Only uses direct input and default capabilities. |
| 1 | Uses pre-configured sources and tools. |
| 2 | Discovers what sources, tools, and capabilities are available. |
| 3 | Applies appropriate resources to the task. |
| 4 | Proactively suggests resources, techniques, identifies capability gaps. |

**Diagnostic:** "Does it know what's available? Does it apply the right resources? Does it suggest approaches or name what's missing?"

**Resource types:**

| Type | Examples |
|------|----------|
| Sources | Files, Slack, GitHub, Notion, arxiv, sibling workflows |
| Tools | Static analysis, test runner, linter, debugger |
| Techniques | GraphRAG, deep search, tree-sitter parsing |
| Capabilities | Web search, code execution, API access |

**Examples by domain:**

| Level | Code | Research | Tasks |
|-------|------|----------|-------|
| 0 | Only the file you pointed to | Only the paper you gave | Only task description |
| 1 | Follows imports, runs default linter | Follows citations | Reads project metadata |
| 2 | "I see tests, CI logs, PRs, and static analysis available" | "Arxiv search available, author has other papers" | "You have Slack, GitHub, Notion connected" |
| 3 | Combines code + tests + PR comments + linter output | Synthesizes related papers + arxiv results | Checks Slack + GitHub + Notion for context |
| 4 | "Run deeper static analysis? Search similar repos? If I had debugger access..." | "GraphRAG the paper corpus? Need the dataset to verify?" | "GraphRAG your decision logs? If you tracked outcomes..." |

---

## 3) Quick Assessment

Rate each quality 0-4, sum for overall score:

| Quality | Score (0-4) |
|---------|-------------|
| Memory | |
| Calibration | |
| Voice | |
| Awareness | |
| Connection | |
| Humility | |
| Flexibility | |
| Agency | |
| Restraint | |
| Predictability | |
| Resourceful | |
| **Total** | **/44** |

**Interpretation:**
- 0-11: Mechanical (does the job, feels robotic)
- 12-22: Functional (works, occasional intelligence)
- 23-33: Adaptive (feels like it's learning)
- 34-44: Intelligent (feels like a partner)

---

## 4) Priority Matrix

Not all qualities matter equally for every workflow:

| Workflow Type | High Priority | Medium Priority | Lower Priority |
|---------------|---------------|-----------------|----------------|
| **Enrichment** (adding metadata, summaries) | Memory, Voice, Humility | Calibration, Connection, Resourceful | Restraint, Agency |
| **Routing** (categorizing, triaging) | Calibration, Memory, Restraint | Connection, Agency, Predictability | Voice, Flexibility, Resourceful |
| **Research** (exploring, gathering) | Connection, Awareness, Resourceful | Memory, Agency | Restraint, Calibration |
| **Automation** (background tasks) | Restraint, Calibration, Humility, Predictability | Memory, Agency | Voice, Awareness, Resourceful |
| **Synthesis** (combining sources) | Connection, Memory, Resourceful | Voice, Agency, Awareness | Restraint, Flexibility |
| **Creation** (writing, generating) | Voice, Humility, Flexibility | Memory, Awareness, Resourceful | Restraint, Calibration |
| **Monitoring** (watching, alerting) | Restraint, Calibration, Predictability | Awareness, Memory, Resourceful | Voice, Flexibility |
| **Communication** (notifications, updates) | Voice, Restraint, Predictability | Calibration, Awareness | Memory, Connection, Resourceful |
| **Code analysis** (debugging, reviewing) | Resourceful, Connection, Memory | Calibration, Agency, Humility | Voice, Flexibility |

---

## 5) Output Format

When evaluating a skill's intelligence:

```
Skill: [name]
Overall: [X/36] - [Mechanical/Functional/Adaptive/Intelligent]

Strengths:
- [Quality]: [Level] - [evidence]

Gaps:
- [Quality]: [Level] - [what's missing]

Priority improvements:
1. [Quality] [current→target]: [specific action]
2. [Quality] [current→target]: [specific action]
```

---

## 6) Relationship to Other Frameworks

```
SKILL_EVOLUTION_EVAL.md      → Where on execution→intelligence ladder?
SKILL_TRACEABILITY_EVAL.md   → Can you reconstruct what happened?
SKILL_INTELLIGENCE_EVAL.md   → Does it feel intelligent? (this doc)
SKILL_INTELLIGENCE_DEMO.md   → What would target state look/feel like?
```

**Traceability enables intelligence:** You can't have Memory (L3+) without traceability. You can't have Calibration (L4) without logging outcomes. Connection requires queryable history.

**But traceability ≠ intelligence:** A workflow can have perfect logs and still feel robotic. Intelligence is about *using* the data to behave appropriately.

---

*Origin: 2026-01-16 conversation re: "what makes a workflow feel intelligent"*
