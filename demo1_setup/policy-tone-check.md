---
name: policy-tone-check
description: Scan a paragraph of policy-research prose for tone issues common in think-tank writing — overclaiming, jargon, long sentences, unsupported assertions, and vague concessions. Returns a numbered list of findings, each with the offending text and a concrete rewrite.
---

# /policy-tone-check

Use this skill when you've just drafted a paragraph or short passage for a
policy white paper, memo, brief, or testimony and want it scanned for
common tone problems before circulation.

## What to check

1. **Overclaiming.** Words and constructions that assert more than the
   evidence supports:
   - *will, undoubtedly, definitely, conclusively, comprehensively, all,
     every, completely, dramatically, substantially, fundamentally*
   - *demonstrated that, proved that, shown conclusively*
   - Universal claims ("across virtually all sectors", "for every
     American", "in all cases")

2. **Jargon.** Think-tank-speak that signals effort but doesn't carry
   meaning:
   - *leverage, synergise, stakeholder engagement, impactful,
     transformative, robust, holistic, comprehensive, paradigm,
     bandwidth, unpack, sunset, deep dive*
   - "Impact" used as a verb
   - Passive policy phrasings: *disproportionately impacted,
     marginalised communities* — flag only if used without specifying
     who and how

3. **Sentence length.** Flag any sentence over 25 words. For sentences
   over 35 words, propose a split.

4. **Unsupported assertions.** Flag claims of the form "studies have
   shown that…" without a specific citation or named study, and claims
   with magnitudes ("substantial gains", "dramatic improvements") without
   numbers.

5. **Vague concessions.** Flag sentences like "although there may be
   transition costs, these are likely minimal" — name *which* transition
   costs and on what evidence.

## Output format

Return a numbered Markdown list, one entry per finding, with:

- **Category** (one of: overclaim, jargon, long sentence, unsupported,
  vague concession)
- **Original text** in a blockquote
- **Suggested rewrite** in a separate blockquote
- One-line **reason** for the change

End with a one-line **tone summary**: "X overclaims, Y jargon hits,
Z long sentences, W unsupported, V vague concessions."

Do not rewrite the whole paragraph. The skill produces a list, not a
finished draft. The user decides which fixes to apply.
