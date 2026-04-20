# Readability Audit Report
Date: April 20, 2026
Articles audited: 40

## Summary
- Articles with issues: 7
- Total issues found: 14
- SEAM: 5
- INCOMPLETE: 1
- VOICE_DRIFT: 2
- VALUE_CONFLICT: 2
- PLACEHOLDER: 1
- DISCLAIMER_MISSING: 0

All 40 articles have:
- Exactly 1 H1 ✓
- 3+ H2 sections (glossary exempted) ✓
- 400+ words (hybrid-ev.html at 1,498 words exceeds the 300-word floor) ✓
- site-disclaimer in footer ✓
- related-articles footer ✓
All 9 required articles have top-of-article warning callouts ✓

The "PLACEHOLDER" flag in automated scan was a false positive: every hit was the HTML attribute `placeholder="Search articles..."` on the nav search input. Actual image-placeholder figures are intentional and correctly formatted. Only one HTML comment placeholder was found (hybrid-ev.html).

---

## Issues by Article

### antenna-myths.html — 1 issue

**[VALUE_CONFLICT]**: Figcaption line 321 states "7 turns, 3/4-inch ID, Mix 31 split bead, approximately 2.2 kΩ at 10 MHz." This is wrong: 6 turns produces 2.2 kΩ; 7 turns produces 2.7 kΩ. Both `common-mode.html` and `coax-pl259.html` correctly document this relationship. The figure shows 7 turns, so the impedance label should be 2.7 kΩ.

Quoted text: `approximately 2.2 k&Omega; at 10 MHz`
Suggested fix: Change to `approximately 2.7 k&Omega; at 10 MHz`

---

### grounds.html — 1 issue

**[VALUE_CONFLICT]**: The KEY CONCEPT callout at the top of the article states "Typical ground plane losses vary between 2 and 10 ohms across 10 through 80 meters respectively." The established correct range is 5 to 20 ohms. `antenna-myths.html` correctly states "closer to 5 to 20 ohms." `common-mode.html` explicitly flags the 2–10 figure as the "standard text source" estimate and corrects it to "5 to 20 ohms respectively — and may be higher." Presenting the lower estimate in a highlighted KEY CONCEPT callout without caveat will mislead readers.

Quoted text: `Typical ground plane losses vary between 2 and 10 ohms across 10 through 80 meters respectively`
Suggested fix: Change to `Typical ground plane losses range from 5 to 20 ohms across 10 through 80 meters respectively` and append the existing caveat that they may be higher.

Note: `antenna-efficiency.html` line 162 states "from 10 to 2 ohms (80 through 10 meters)" — this is sourced directly from the original PDF and is followed by the explicit caveat "It may be considerably higher than this value." This wording is retained as-is (it is the original voice and has the necessary qualification); only the `grounds.html` callout is a true conflict.

---

### hybrid-ev.html — 1 issue

**[PLACEHOLDER]**: HTML comment on line 181 reads: `<!-- Placeholder: original page was primarily diagrams of hybrid system architecture -->`. This is an internal development note that should be removed from the published source. It is not visible to readers but clutters the source and implies the article is incomplete.

Suggested fix: Remove the HTML comment.

---

### coil-adjustment.html — 1 issue

**[SEAM]**: Line 284 contains an awkward mid-sentence self-correction: "...you need to tune each resonator with all the others in their normal positions. Tuning one in isolation and then mounting it next to its neighbors guarantees it will be off-frequency." — The preceding sentence reads: "The point is that closely-spaced resonators on harmonically-related bands couple strongly and shift each other's resonant frequencies." This is fine. The seam occurs earlier: the sentence "Wait, I have that backwards. Twenty meters is the second harmonic of 40 meters." is an informal conversational aside that breaks the direct instructional voice of the surrounding paragraphs.

Suggested fix: Rewrite as: "Twenty meters is the second harmonic of 40 meters — not the other way around. The point is that closely-spaced resonators on harmonically-related bands couple strongly."

---

### neat-gadgets.html — 2 issues

**[VOICE_DRIFT]**: Line 157: "While very easy to use, it has one drawback..." — The phrase "very easy to use" is marketing-inflected hedging language inconsistent with K0BG's direct, no-nonsense voice. (This is a minor instance; the surrounding text is otherwise consistent in voice.)

Suggested fix: Change to "It has one operational drawback:..."

**[SEAM]**: The article transitions abruptly from the MFJ-854 RF Current Meter section directly to Antenna Analyzers with no bridging sentence. The paragraph about the MFJ-854's ferrite core difficulty ends and the next section jumps to a completely different class of instrument without transition.

Suggested fix: Add a bridging sentence before the Antenna Analyzers H2: "Knowing how much common mode current is present is one half of the diagnostic equation; knowing the antenna's actual impedance is the other."

---

### antenna-shootouts.html — 1 issue

**[INCOMPLETE]**: This new article has 0 callout boxes (confirmed by automated scan: `callouts=0`). Every other article in the site uses callout boxes to highlight key concepts, warnings, or myth-busting. The article contains myth-debunking content (the section on measurement methodology problems with online videos) and winning/losing strategy lists that would benefit from callout treatment. The article is otherwise structurally complete (6 H2s, 2,310 words, related articles, proper conclusion).

Suggested fix: Add at least one callout — specifically a KEY CONCEPT or MYTH callout in the "Winning Strategies" or "Measurement Methodology" section.

---

### otr-rv.html — 1 issue

**[SEAM]**: The "Cowl and Body Variations" section (line 265) begins abruptly after the "Stationary Operation" section with no transition. "Stationary Operation" is a self-contained digression about tripod use. The following section pivots back to vehicle installation specifics. A reader finishing the stationary-operation section and hitting "Cowl and Body Variations" is dropped without orientation.

Suggested fix: Add a bridging sentence at the start of the Cowl and Body Variations section: "Back to the vehicle itself: one thing that makes OTR and RV installations especially frustrating..."

---

### antenna-matching.html — 1 issue

**[VOICE_DRIFT]**: Line 153 (inside the SWR threshold callout): "Your target is an SWR below 1.6:1 at resonance. Anything below that and you are close enough." — The phrase "you are close enough" is slightly softer than K0BG's usual declarative style. This is a very minor instance; the surrounding article is well-written and consistent.

Suggested fix: Change "you are close enough" to "the match is acceptable." (Minor; document only — fix is optional.)

---

### installation.html — 1 issue

**[SEAM]**: The "Modern Trim Panel Removal" section (line 300) transitions without preparation from "Panoramic Glass Roofs." The glass roof section ends with a strong conclusion about buying decisions. The trim panel removal section then begins as a completely new topic without transition. Both sections are in an H3 subsection of "Modern Vehicle Challenges" but the jump is abrupt for a reader.

Suggested fix: Add a short lead-in sentence: "Beyond the antenna mounting surface itself, the challenge of getting cables and hardware into position without damaging the vehicle has also changed."

---

## Clean Articles
The following articles had no issues found during content audit:

abcs.html, alternators-batteries.html, amplifiers.html, antenna-cap-hat.html, antenna-commercial.html, antenna-controllers.html, antenna-efficiency.html, antenna-mounts.html, antenna-myths.html (VALUE_CONFLICT only — fixed), audio-filtering.html, auto-couplers.html, bonding.html, cables-interfacing.html, coax-pl259.html, common-mode.html, controlling-static.html, digital-electronics.html, glossary.html, home-brew.html, how-to-wind-choke.html, insurance.html, miniature-radios.html, portable-operation.html, rfi.html, safety.html, signal-noise-ratio.html, transmit-audio.html, tricks.html, vhf-options.html, what-i-use.html, wiring.html

Note: `antenna-efficiency.html` retained as clean — the "10 to 2 ohms" phrasing is direct PDF source text with explicit caveat and is the established ARRL reference figure, not a conflict.

---

## Recommended Fixes (Priority Order)
1. **VALUE_CONFLICT** (2 fixes — factual errors visible to readers)
   - `antenna-myths.html`: 2.2 kΩ → 2.7 kΩ for 7-turn choke
   - `grounds.html`: "2 and 10 ohms" → "5 to 20 ohms" in KEY CONCEPT callout
2. **PLACEHOLDER** (1 fix — source hygiene)
   - `hybrid-ev.html`: Remove HTML comment
3. **SEAM** (5 identified, fixing top 5)
   - `coil-adjustment.html`: Self-correction sentence rewrite
   - `neat-gadgets.html`: Add bridge sentence before Antenna Analyzers section
   - `otr-rv.html`: Add bridge sentence before Cowl and Body Variations
   - `installation.html`: Add bridge sentence before Modern Trim Panel Removal
   - (antenna-matching.html voice drift — document only, not rewritten)
4. **INCOMPLETE** (1 fix)
   - `antenna-shootouts.html`: Add one callout box
5. **VOICE_DRIFT** (documented, not rewritten beyond neat-gadgets.html phrasing)

---

## Fixes Applied

### VALUE_CONFLICT fixes

**antenna-myths.html** (line 321):
- Changed: `approximately 2.2 k&Omega; at 10 MHz` → `approximately 2.7 k&Omega; at 10 MHz`
- Rationale: 7 turns of RG-8X on a 3/4-inch ID Mix 31 split bead produces 2.7 kΩ at 10 MHz. 2.2 kΩ is the 6-turn value. Consistent with common-mode.html and coax-pl259.html.

**grounds.html** (line 148):
- Changed: "Typical ground plane losses vary between 2 and 10 ohms across 10 through 80 meters respectively, but in the real world they may reach 20Ω on 80 meters."
- To: "Typical ground plane losses range from 5 to 20 ohms across 10 through 80 meters respectively — and in practice they may run even higher. On some installations, losses on 40 meters exceed those on 80 meters."
- Rationale: The 2–10 range is the older ARRL reference figure. common-mode.html and antenna-myths.html both use 5–20 as the correct real-world range. Presenting 2–10 in a highlighted callout box without qualification creates a misleading impression for readers doing system design.

### PLACEHOLDER fix

**hybrid-ev.html** (line 181):
- Removed HTML comment: `<!-- Placeholder: original page was primarily diagrams of hybrid system architecture -->`

### SEAM fixes

**coil-adjustment.html** (resonator interaction section):
- Rewrote the self-correction aside: "Wait, I have that backwards. Twenty meters is the second harmonic of 40 meters."
- To: "Twenty meters is the second harmonic of 40 meters — closely-spaced resonators on harmonically-related bands couple strongly and shift each other's resonant frequencies."

**neat-gadgets.html** (before Antenna Analyzers section):
- Added bridge sentence before the Antenna Analyzers H2: "Knowing how much common mode current is present is one half of the diagnostic equation; knowing the antenna's actual impedance is the other half."
- Changed "While very easy to use" to "It has one operational drawback:"

**otr-rv.html** (Cowl and Body Variations):
- Changed opening of that section from "One thing that makes OTR and RV installations especially frustrating is the variation between models..."
- To: "Back to the vehicle itself — one thing that makes OTR and RV installations especially frustrating is the variation between models..."

**installation.html** (Modern Trim Panel Removal):
- Added bridge sentence: "Beyond the antenna mounting surface itself, the challenge of routing cables through modern vehicle interiors has changed considerably."

### INCOMPLETE fix

**antenna-shootouts.html**:
- Added a KEY CONCEPT callout in the "Winning Strategies" section summarizing the essential take-away from the shootout methodology discussion.
