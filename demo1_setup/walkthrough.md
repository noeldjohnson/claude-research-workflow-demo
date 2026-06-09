# Demo 1 — Set up your project as a thinking partner

**Duration:** ~6 minutes live.
**Goal:** show the audience how to turn an empty directory into a Claude
project that already understands its goals, style, and quality bar.

---

## Pre-talk setup (do this once, day before)

1. Create the sandbox directory outside any existing project:
   ```bash
   mkdir -p ~/mercatus_demo
   cd ~/mercatus_demo
   ```
2. Open this directory in your editor (VS Code or similar).
3. Confirm `claude` is installed and you can run it from this directory:
   ```bash
   claude --version
   ```
4. Have this `walkthrough.md` open on a second monitor or printed.
5. Have `CLAUDE.md`, `policy-tone-check.md`, and `sample_memo.txt`
   open in tabs or in your clipboard so you can paste them quickly.

---

## Live demo script

### Step 1 (~30 sec) — Show the empty directory

In the projected terminal:

```bash
cd ~/mercatus_demo
ls -la
```

Audience sees: `.`, `..`, nothing else. Empty directory.

**Say:** *"This is what Monday morning looks like at a research project.
Empty folder. I'm about to teach Claude what this project is."*

### Step 2 (~90 sec) — Write the CLAUDE.md

Open a new file `CLAUDE.md` in your editor. Paste the contents from
`demo_assets/demo1_setup/CLAUDE.md`.

While pasting, narrate:

> *"CLAUDE.md is a plain English instruction file. No code. I'm telling
> Claude what the project is, who the audience is, what the style rules
> are, what the quality bar is, and what to avoid. About 50 lines, total.
> This file is the single biggest leverage point in the workflow."*

Save the file.

### Step 3 (~60 sec) — Show the file structure with the skill

```bash
mkdir -p .claude/skills
```

Open `.claude/skills/policy-tone-check.md`. Paste from
`demo_assets/demo1_setup/policy-tone-check.md`.

**Say:** *"This is a custom skill. It's still just Markdown — no code. I'm
defining a checklist Claude can run on any paragraph I drop into it. It
checks for overclaiming, jargon, long sentences, unsupported claims, and
vague concessions. The skill is the second leverage point — turning
common review tasks into one-line commands."*

Save the file.

### Step 4 (~30 sec) — Start Claude in this directory

```bash
claude
```

**Say:** *"Claude is now reading the CLAUDE.md and the skill file. It
knows this project."*

### Step 5 (~120 sec) — Invoke the skill on the sample memo

Open `sample_memo.txt` in the editor. Show the paragraph to the room.

**Say:** *"This is a draft paragraph from a fictional white paper on
occupational licensing. Looks like a real Mercatus paragraph. Let's see
what the skill catches."*

In the Claude session, type or paste:

```
/policy-tone-check

Implementation of comprehensive occupational licensing reform will
undoubtedly result in significant economic gains across virtually all
sectors of the American economy, as numerous studies have demonstrated
conclusively that licensing requirements function as barriers to entry
that suppress competition, reduce consumer welfare, and dramatically
constrain labor market mobility. By leveraging cross-sector stakeholder
engagement and synergising federal, state, and local efforts,
policymakers can unlock substantial productivity gains while
simultaneously enhancing equity outcomes, particularly for marginalised
communities who are disproportionately impacted by current licensing
regimes. Although there may be transition costs, these are likely
minimal in comparison to the long-term benefits.
```

Wait for the response (~20–40 seconds).

The skill should return a numbered list flagging:
- "undoubtedly", "significant", "dramatically", "substantially" as overclaims
- "leveraging", "synergising", "stakeholder engagement" as jargon
- The 50-word first sentence as too long
- "numerous studies have demonstrated conclusively" as unsupported
- "Although there may be transition costs, these are likely minimal" as a
  vague concession

Walk through 2–3 findings and the suggested rewrites. **Don't read the
whole report** — let the room see the structure and trust that the rest is
similar.

### Step 6 (~30 sec) — Close

**Say:** *"Two files. Plain English. About ten minutes of work. Now Claude
knows my project's goals, style, and quality bar — and I can run this
review on every paragraph I draft. This is the Monday-morning setup."*

---

## What the audience takes home

Copy `~/mercatus_demo/CLAUDE.md` and `~/mercatus_demo/.claude/skills/*`
into their own project. Edit the style rules and quality bar to match
their work. Done.

---

## Backup plan

If Claude hangs or the API is unreachable:

1. Switch to the backup screencast (in slides).
2. Talk through the *findings* as if Claude had returned them. The
   audience hasn't seen the actual API call, so they can't tell the
   difference between live output and slide content.
3. Keep moving. Don't try to debug live.

---

## Time budget

| Step | Target | Cumulative |
|---|---|---|
| 1. Empty dir | 30s | 0:30 |
| 2. Write CLAUDE.md | 90s | 2:00 |
| 3. Write the skill | 60s | 3:00 |
| 4. Start Claude | 30s | 3:30 |
| 5. Run skill on memo | 120s | 5:30 |
| 6. Close | 30s | 6:00 |
