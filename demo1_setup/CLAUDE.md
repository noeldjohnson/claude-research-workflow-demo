# CLAUDE.md — Mercatus White Paper: Occupational Licensing Reform

**Project goal:** Draft a 30-page Mercatus white paper on the economic
effects of occupational licensing reform in the United States.

**Authors:** [Your name].

**Audience:** Mid-career policy researchers and fellows at think tanks,
federal agencies, and state legislative offices. Mixed quantitative
literacy. Skeptical of overclaiming. Will read on a tablet or print
the PDF.

**Output format:** Markdown drafts under `sections/`. Final PDF is
assembled via the Mercatus two-column white paper template.

---

## Style rules

1. **No overclaiming.** Use *could* not *will*, *may* not *would* unless
   the claim is backed by a specific cited result.
2. **No jargon.** Replace *leverage*, *synergise*, *stakeholder
   engagement*, *impactful*, *transformative*, *robust*, *comprehensive*
   with concrete verbs and specifics.
3. **Sentences under 25 words** wherever possible. Long sentences need a
   reason.
4. **One concrete number per paragraph.** If a paragraph makes a claim,
   at least one figure, percentage, or named study should anchor it.
5. **Plain English.** Imagine the reader is a senator's chief of staff
   who needs to understand the argument in one read.
6. **Concessions are explicit.** Don't bury limitations in vague hedges
   like "although there may be transition costs". Name them.

## Quality threshold

- 80 / 100 on the proofreader rubric = ready to circulate internally
- 90 / 100 = ready for external review
- Anything below 80 blocks commit

## Workflow

- Write a plan under `plans/` before drafting a new section. Get the
  plan approved before drafting.
- After drafting a section, run `/policy-tone-check` on it. Address all
  HIGH findings and a majority of MEDIUM findings before moving on.
- Tables and charts derived from R scripts under `scripts/`, not
  hand-written. The R script is the single source of truth.
- Bibliography is in `bibliography.bib`. Run `/validate-bib` before
  any commit to confirm all `\cite{}` keys resolve.

## Things to avoid

- Treating Claude's output as final without reading it
- Letting prose drift into the AI register (em-dash parentheticals,
  rhetorical "this is supported by" constructions, sentence-fragment
  enumerations like "(i)…(ii)…(iii)…")
- Citing an empirical result without checking the source
- Drafting beyond a plan that hasn't been approved
