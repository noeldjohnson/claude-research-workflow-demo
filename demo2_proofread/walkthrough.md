# Demo 2 — Use it to ship work (proofread-and-approve loop)

**Duration:** ~5 minutes live.
**Goal:** show the audience the propose-then-apply pattern. Claude
flags edits, you accept or reject each one, then the approved edits
get applied to the file.

---

## Pre-talk setup

1. Copy `section_9_5_before.tex` into your sandbox (`~/mercatus_demo/`).
2. Make sure `section_9_5_after.tex` is *not* visible during the demo —
   it's there for your reference if Claude goes off the rails, but the
   audience shouldn't see the answer key.
3. Have `prompt.txt` open or in your clipboard so you can paste it.

---

## Live demo script

### Step 1 (~30 sec) — Show the original passage

Open `section_9_5_before.tex` in the editor. Project it.

**Say:** *"This is one subsection from the paper, drafted by Claude in
the first pass. Read it for two seconds and you can hear it. The
em-dashes wrapping prediction-clauses. 'Caveats are in order.' followed
by Roman numerals. 'Supported at conventional significance through two
distinct margins.' It reads like the kind of text a junior research
assistant would write to sound serious."*

### Step 2 (~30 sec) — Hand Claude the prompt

Switch to the Claude terminal. Paste the contents of `prompt.txt`.

**Say:** *"I'm asking Claude to scan the paragraph, list every change it
would propose, and wait. Not 'rewrite it for me' — propose changes.
Big difference."*

Wait for the response (~30–60 seconds).

### Step 3 (~120 sec) — Walk through Claude's proposals

Claude will return a list of ~8–15 proposed edits. They'll cover
roughly the same ground as the actual prose pass we did:

- Replace "The joint reading is clean" with something concrete
- Break the em-dash triplets into clean clauses
- Convert "Caveats are in order. (i)…(ii)…" to short paragraphs
- Pull out the "supported at conventional significance through" colon
- Clean up the semicolons in caveat (iii)

For each, do something visible:
1. Accept the first three explicitly: read the proposal, say "yes, apply
   that", move on.
2. **Reject one** explicitly. Pick one you disagree with — or
   pre-disagree with the one about restructuring the Wittenberg
   sentence. Say *"I want to keep that one. Skip it."* This is the
   important moment of the demo — the audience sees you in control.
3. Accept the rest in a batch: *"Apply the rest."*

### Step 4 (~60 sec) — Show the diff

Claude will apply the approved changes. Show the resulting file
side-by-side with the original.

**Say:** *"Two minutes of work. Voice preserved. No AI tells. And I
rejected one of Claude's proposals — the workflow respects that. This
isn't Claude writing my paper. It's Claude saying 'here are the things
that would catch a referee's eye' and me deciding which ones to fix."*

### Step 5 (~30 sec) — Close

**Say:** *"This same workflow applies to a white paper, a memo, a brief,
testimony — any prose where you care about voice. The propose-then-
approve loop is what makes it safe."*

---

## What the audience takes home

- `section_9_5_before.tex` (the input)
- `section_9_5_after.tex` (an example of what the loop produces)
- `prompt.txt` (the exact prompt that drove the loop)

They can run the same loop on their own draft sections.

---

## Backup plan

If Claude hangs or doesn't return useful proposals:

1. Pre-record this demo too, embed in slides as backup.
2. If forced to fall back live, switch to the static `before` /
   `after` files in the editor and talk through 3–4 changes manually,
   as if Claude had proposed them. The pattern is the demo, not the
   exact list.

---

## Time budget

| Step | Target | Cumulative |
|---|---|---|
| 1. Show the original | 30s | 0:30 |
| 2. Hand Claude the prompt | 30s | 1:00 |
| 3. Walk through proposals | 120s | 3:00 |
| 4. Show the diff | 60s | 4:00 |
| 5. Close | 30s | 4:30 |
| Buffer | 30s | 5:00 |
