# Demo 3 — Gating with multi-agent review

**Duration:** ~4 minutes live.
**Goal:** show the audience how three independent agents review the
same section in parallel — substance, proofreading, citations — and
each one writes a report you can act on.

**Cached.** The three reports were pre-run against §8 on 2026-06-09
and live under `cached_reports/`. During the demo you "run" the
commands (which appear to execute instantly) and the cached files
appear.

---

## Pre-talk setup

1. Copy the three cached reports into the real project's
   `quality_reports/` directory the day before the talk:
   ```bash
   cp demo_assets/demo3_multi_agent_review/cached_reports/section_8_*.md \
      quality_reports/
   ```
2. Confirm they're visible there.
3. Have the prompts (`prompts/*.txt`) open in tabs so you can show
   what each agent was told.

---

## Live demo script

### Step 1 (~30 sec) — Frame the problem

Open §8 in the editor. Project a couple of its more complex paragraphs.

**Say:** *"This is one section of the paper. It's eight pages of text,
twelve tables of numbers, twenty citations. If a referee is reading
this for the first time, what are the three things most likely to catch
their eye? Substance error. Typo or grammar mistake. Bad citation.
Three different reviewers, three different lenses. Let's spawn them all."*

### Step 2 (~30 sec) — Show the agent prompts

Quickly flip through `prompts/proofreader.txt`, `domain_reviewer.txt`,
`bib_validate.txt`. Don't read them in full — just show that each is
short and that each targets a single lens.

**Say:** *"Three prompts, one per reviewer. Each one is a paragraph
long. The agent does the rest."*

### Step 3 (~30 sec) — Spawn the agents (cached)

In the Claude session, type or paste:

```
Run /validate-bib and spawn the proofreader and domain-reviewer
sub-agents in parallel on Paper/sections/08_results.tex. Save each
report to quality_reports/section_8_<agent>.md.
```

Because the reports are pre-staged, the files appear "instantly".

**Say:** *"In the real workflow this takes three or four minutes — the
agents read the section in parallel and write their reports. For the
demo I pre-ran them so we can walk through what they caught."*

### Step 4 (~60 sec) — Open the proofreader report

Open `cached_reports/section_8_proofreader.md` in the editor.

Walk through the HIGH severity section (5 findings, all grammar /
punctuation / citation arity).

**Say:** *"The proofreader catches five high-severity items, all in
sixty seconds. Missing commas. A comma splice. A multi-key cite that
typesets badly with natbib. These are the things that would otherwise
get caught in the second round of copy editing — but caught here
before I commit."*

### Step 5 (~45 sec) — Open the domain-reviewer report

Open `cached_reports/section_8_domain.md`.

Read the MAJOR section header. Walk through M1 (Smith vs. Krugman
framing overstates the contrast) without going line by line.

**Say:** *"This is the more interesting one. The domain reviewer
catches a substantive issue — my own §4 already concedes that Stigler's
formalisation of Smith leaves room for increasing returns, but my §8
prose drops that hedge and reverts to a clean Smith-vs-Krugman binary.
The reviewer also notes that the distinctiveness result is closer to a
spatial-differentiation prediction than a pure Krugman prediction. This
is the kind of thing a careful referee would flag, and now I can fix it
before submission."*

### Step 6 (~30 sec) — Open the bib-validate report

Open `cached_reports/section_8_bib_validate.md`.

**Say:** *"Manuscript-wide bibliography check. Sixty-two citation keys
in the paper, all resolve to bib entries. Thirteen bib entries that
aren't cited anywhere — those are leftover from earlier drafts and I
can clean them. No typos, no missing citations. The paper compiles
without question marks."*

### Step 7 (~15 sec) — Close

**Say:** *"Three reports, one section, fifteen findings. Same protocol
works for a white paper, a memo, a brief. The agents don't write your
work — they catch the things you'd want a colleague to catch before
your reader does."*

---

## What the audience takes home

- `cached_reports/section_8_proofreader.md`
- `cached_reports/section_8_domain.md`
- `cached_reports/section_8_bib_validate.md`
- `prompts/*.txt`

They can use the prompts as templates for spawning the same agents on
their own manuscripts.

---

## Backup plan

If the cache fails (terminal output looks wrong, or the files don't
appear in the editor):

1. Open the cached reports directly from `cached_reports/` and walk
   through them anyway. The cache *is* the demo at this point.
2. If even that doesn't work, the screencast in the slides is the
   third fallback.

---

## Time budget

| Step | Target | Cumulative |
|---|---|---|
| 1. Frame the problem | 30s | 0:30 |
| 2. Show the prompts | 30s | 1:00 |
| 3. Spawn (cached) | 30s | 1:30 |
| 4. Proofreader report | 60s | 2:30 |
| 5. Domain report | 45s | 3:15 |
| 6. Bib-validate report | 30s | 3:45 |
| 7. Close | 15s | 4:00 |
