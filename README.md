# Mercatus seminar — demo assets

**Talk:** Mapping the Market for Ideas in Europe, 1450–1650 — and the
AI-assisted workflow that built it.
**Date:** 2026-06-09, Mercatus Center.
**Speaker:** Noel D. Johnson, George Mason University.

This folder holds the source material for the three live demos in
Part IV of the talk. It exists for two audiences:

1. **Anyone who wants to follow along** during the talk — open the
   files in your editor and reproduce each demo in your own sandbox.
2. **Anyone who wants to replicate the workflow after the talk** —
   the three folders are self-contained recipes for the three
   patterns Noel demonstrates.

You don't need this paper or this project to follow along. You don't
even need to know R or LaTeX. You need:
- A laptop with Claude Code installed
  ([install](https://docs.claude.com/en/docs/claude-code))
- A working directory to use as a sandbox (e.g.\ `~/demo_sandbox/`)
- A text editor (VS Code, Cursor, vim, anything)

---

## What the three demos show

| Demo | Pattern | Time | Source folder |
|---|---|---|---|
| 1 | Set up your project as a thinking partner | ~6 min | `demo1_setup/` |
| 2 | Propose-then-approve loop for prose edits | ~5 min | `demo2_proofread/` |
| 3 | Multi-agent review as a gating mechanism | ~4 min | `demo3_multi_agent_review/` |

Each folder has a `walkthrough.md` with step-by-step instructions
(intended both as Noel's script for the live demo and as a replication
recipe for anyone reading later).

---

## Recommended order

If you're replicating this on your own machine, do them in order.
Demo 1 sets up the conceptual scaffolding (the `CLAUDE.md` file, the
custom skill). Demo 2 shows the propose-then-approve loop in action.
Demo 3 shows how the same pattern scales to multiple reviewers
running in parallel.

---

## Quick start (if you want to follow along live)

```bash
# Create a fresh sandbox outside any existing project
mkdir -p ~/demo_sandbox
cd ~/demo_sandbox

# Demo 1: copy these two files in
cp /path/to/demo_assets/demo1_setup/CLAUDE.md           .
mkdir -p .claude/skills
cp /path/to/demo_assets/demo1_setup/policy-tone-check.md .claude/skills/

# Now start Claude Code
claude
```

Then trigger the skill with `/policy-tone-check` followed by the
sample paragraph (also in `demo1_setup/sample_memo.txt`).

For Demo 2, copy `demo2_proofread/section_9_5_before.tex` into the
sandbox and paste the contents of `demo2_proofread/prompt.txt` into
the Claude session.

For Demo 3, the cached reports under
`demo3_multi_agent_review/cached_reports/` are real outputs from
running the proofreader, domain-reviewer, and `/validate-bib` skill
against §8 of the paper.

---

## Folder structure

```
demo_assets/
├── README.md                              ← this file
├── demo1_setup/
│   ├── CLAUDE.md                          ← project instructions
│   ├── policy-tone-check.md               ← custom skill
│   ├── sample_memo.txt                    ← paragraph to scan
│   └── walkthrough.md                     ← step-by-step script
├── demo2_proofread/
│   ├── section_9_5_before.tex             ← input (AI-tells-heavy)
│   ├── section_9_5_after.tex              ← reference (what the loop produces)
│   ├── prompt.txt                         ← prompt to Claude
│   └── walkthrough.md
└── demo3_multi_agent_review/
    ├── prompts/
    │   ├── proofreader.txt                ← spawn the proofreader
    │   ├── domain_reviewer.txt            ← spawn the domain-reviewer
    │   └── bib_validate.txt               ← run /validate-bib
    ├── cached_reports/                    ← pre-run reports for the demo
    │   ├── section_8_proofreader.md
    │   ├── section_8_domain.md
    │   └── section_8_bib_validate.md
    └── walkthrough.md
```

---

## The bigger story

Each demo isolates one piece of a workflow:

- **CLAUDE.md** is the project's *memory* — what Claude needs to know
  about your goals, audience, and quality bar so it can be useful from
  the first message.
- **Custom skills** are short Markdown files defining repeatable
  review tasks (tone, fact-check, citation hygiene). They turn
  "ask Claude to do X" into a one-line command.
- **The propose-then-approve loop** is the safe pattern for letting
  Claude edit your prose without losing voice. Claude proposes,
  you decide.
- **Multi-agent review** is gating, not magic. The agents catch
  things you'd want a careful colleague to catch before your reader
  does — and they run in parallel, so the gating step doesn't slow
  your draft cycle.

The paper this talk is built around (Johnson & Taylor 2026, *Mapping
the Market for Ideas in Europe, 1450–1650*) was built with all four
patterns in steady use. The demos are scaled-down versions of the
actual project workflow.

In case anybody wants more, the actual workflow I cloned from github and then customized as my "research workflow" comes from: https://psantanna.com/claude-code-my-workflow/workflow-guide.html

---

## Questions, comments, follow-up

Reach Noel at \<njohnsoL@gmu.edu\>.

The demo materials in this folder live in a public companion repo:
https://github.com/noeldjohnson/claude-research-workflow-demo
