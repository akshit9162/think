---
name: think
description: "Think a problem through with mental models: picks the 3-5 that actually fit from a ~50-model library (first principles, inversion, premortem, second-order thinking, sunk cost, opportunity cost, expected value & Kelly, margin of safety, circle of competence, the Mom Test, barbell, optionality, bottlenecks, feedback loops, etc.), runs each against the specific situation using sourced thinking steps, then connects them into one recommendation. Trigger: `/think`, 'think this through', 'think about this properly', 'use mental models', 'first-principles this', 'invert this', 'premortem this', 'what am I missing', 'should I keep going or quit'. Short answer by default; `/think deep` gives the full per-model breakdown. Also use for a real decision, plan, or stuck problem where a single structured pass is enough. For high-stakes decisions wanting multiple adversarial perspectives, use llm-council instead."
---

# Think

One structured pass over a problem using mental models. The point is **connecting** models,
not listing them — never recite the library, never define a model the user didn't ask about.

## Files

- `models/index.md` — every model, grouped, with one-liners, depth, and selection heuristics.
  **Always read it first.**
- `models/<slug>.md` — 26 "Deep" models with sources, **When to Avoid**, **Thinking Steps**
  and **Coaching Questions** (or Process / Red Flags for the deciqAI ones).
- `CREDITS.md` — origins and MIT licences.
- Your own models (optional): drop files in the same shape into `~/.claude/mental-models/` or
  `.mental-models/` in a project; check both before selecting, and a user model wins a name clash.

## Process

1. **Restate the problem in one line**, including what a good outcome looks like. If the goal
   or a key constraint is genuinely unknown and changes the answer, ask one question;
   otherwise state the assumption and proceed. If the problem touches a project the user
   keeps notes on (CLAUDE.md, memory files, a wiki, a README), read those first — specifics
   from real context are what make the answer useful.
2. **Read `models/index.md`, and glob `~/.claude/mental-models/*.md` and `.mental-models/*.md`
   for the user's own models; then pick 3–5 models from different groups.** Use the selection
   heuristics. Prefer models that pull against each other (e.g. Optionality vs. Opportunity
   Cost, Sunk Cost vs. Margin of Safety) — the tension is where insight comes from. Pick for
   fit, not fame.
3. **Read the file for every Deep model picked.** Walk its Thinking Steps against the user's
   actual facts; don't paraphrase the framework away. **Check its When to Avoid** — if it
   applies, say so and drop or downweight that model.
4. **Apply each model** against the user's own numbers, names and constraints. Find the one
   non-obvious insight each model gives. Bad: "Opportunity cost is what you give up." Good:
   "The 6 weekends on the side project are the 6 weekends the launch doesn't get its content." If two
   models land on the same insight, keep the sharper one.
5. **Connect.** Where do the models agree, where do they conflict, which wins and why?
6. **Recommend.** One clear call, the single next action, and the signal that would change
   the call.

## Output format

### Default: short (~150–250 words)

Lead with the answer. The models do the work, but the output only shows what they found.

```
**Call:** <the recommendation, 1–2 sentences>

**Why:**
- **<Model>:** <one-line finding using the user's specifics>
- **<Model>:** <one-line finding>
- **<Model>:** <one-line finding>
- **Tension:** <where models disagreed and which won — omit if none>

**Next:** <one action>. **Change course if:** <signal>.
```

Add a one-line **Check first:** only for a real blocker (legal, eligibility, missing data).
No lens definitions, no "What it asks", no per-model sections.

### Deep: `/think deep …`, or the user asks for the full reasoning

Use when the user types `deep`, says "show your reasoning" or "full breakdown", or the
decision is high-stakes and irreversible. Up to ~500 words.

```
**Problem:** <one line>

**Lenses:** <Model> (why) · <Model> (why) · <Model> (why)

### <Model 1>
**What it asks:** …
**Applied:** …
**Non-obvious insight:** …

### <Model 2>
…

### Connecting them
<agreements, tensions, which wins and why; any When-to-Avoid caveats> — the longest section

### Call
<recommendation> — next action: <one step>. Change course if: <signal>.
```

Cite a model's source only when it strengthens the point. If a Deep model's Coaching
Question would sharpen the decision, end with it (deep mode only).

## Special modes

- **"premortem this"** → lead with `premortem`, use its output table (keep it to the top 5 rows in short mode) (failure mode · prob ·
  severity · mitigation · trigger), then add 1–2 supporting lenses.
- **Customer or demand validation** → lead with `the-mom-test`; output interview questions
  plus what counts as a real commitment.
- **Bet or position sizing** → lead with `expected-value-and-kelly` plus `margin-of-safety`;
  show the arithmetic.

## When not to use

- Factual lookups or simple yes/no questions — just answer.
- Pure coding or debugging tasks.
- High-stakes decisions where the user wants debate from several perspectives — use `llm-council`.

## Growing the library

To add a model, copy the shape of any Deep file (frontmatter `type: mental-model`, title,
description, sources; then When to Avoid, Thinking Steps, Coaching Questions), save it to
`models/<slug>.md`, and add a row to `models/index.md`. More sourced models:
deciqAI/knowledge-skills (~250, many domain-specific — pick selectively).
