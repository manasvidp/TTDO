# The Decision Office: v5 release report

**Files**
- `original/The_Decision_Office_4.html` is the untouched original (SHA-256 `749c91e7…efcb24`).
- `The_Decision_Office_v5.html` is the revised site, with the approved changes from the Phase 1 audit.

## What changed

### Facts and sources (C1–C4, C10, C15)
- **LEGO timeline.** Each figure is now labelled with its measure and status:
  - 2000: DKK 831m loss, from the annual report.
  - 2003: preliminary operating loss of about DKK 1.4bn, described in January 2004 as the worst in LEGO's 72-year history.
  - 2004: net loss of DKK 1.93bn as first reported.
  - 2005: DKK 505m as reported in 2006.
  - A note now says these figures use different measures and that later accounts restated them. The card's headline line was reworded to match.
  - *Correction to the audit:* the original "worst in history" claim for 2003 was supported, because it referred to the operating loss. The real problem was the unlabelled mix of measures.
- **A380.**
  - Removed "Boeing forecasts 740". I couldn't date that figure to 2000; trade press ties it to a later forecast.
  - Boeing's position is now stated as reported in December 2000 coverage.
  - Removed the unsourced "Middle East about 4%" claim. Replaced it with a fact I could confirm: Emirates took 123 of the 251 A380s delivered.
  - Added the program's total deliveries (251).
- **Costco.**
  - Renewal rates now specify "US and Canada" in every row.
  - The unnamed "75%" source is now described as a figure we couldn't reproduce.
  - Added the fiscal 2005 fee and net income figures from the 10-K and annual report.
- **Slow decisions scenario.** The context and the evidence card now agree: four decisions were reopened.
- **Sources and grades.** Every investigation lists its sources with a grade and a source type. The Airbus statement now links to Airbus's own press release instead of a repost.

### Method (C5–C9, H1–H3, H12)
- **Standards panel.** The method section now shows:
  - written criteria for grades A–D;
  - a rule that evidence only counts if it tells the explanations apart;
  - a likelihood scale with percentage ranges;
  - a separate confidence scale (high, moderate, low);
  - one claim vocabulary: Fact, Reported, Our reading, Unknown.
- **Weighted scoring.** In the lab, each card's effect is its direction × its grade weight (A 1, B 0.75, C 0.5, D 0.25). Leaders closer than 0.5 are shown as level instead of picking an arbitrary winner.
- **Scenario fixes.**
  - *Shrinking margin:* the untested "cost to serve" explanation replaces the customer-mix hypothesis.
  - *Rising churn:* the non-diagnostic usage card is replaced with a guided-setup pilot comparison. The "leavers paid less" card is replaced with a before/after price-rise comparison.
  - *Competing opportunities:* reframed as claims behind each option. "Building both" is now a testable claim instead of a constraint. The self-serve evidence now includes conversion data.
  - *Slow decisions:* the verdict now says ownership and metrics are level.
- **Likelihood and confidence everywhere.** Each conclusion shows both, and confidence varies across examples (high, moderate, low).
- **Sample brief.** Adds an options × criteria matrix and a cost-of-waiting line. A downloadable sample Evidence Ledger (CSV) is in the brief's margin.
- **Investigations.** Each one now has a "Was it a good decision?" verdict, separate from the outcome. Each states that its competing explanations can contribute together. Costco is anchored to a 2005 decision point.
- **Story heading.** "Then the evidence decides" became "Then the evidence narrows the choice".

### Editorial and information architecture (H5, H6)
- **One numbering system.** The story chapters and timeline now use the method's stages (01 Define … 05 Decide). Section labels are no longer numbered.
- **Eyebrow** is now "Independent decision investigation", matching the footer.
- **Founder heading** no longer repeats the hero line.
- **Deliverables glossary** added under the offers.
- **Footer navigation** now matches the header and adds Privacy.

### Accessibility (C11–C14)
- Focus rings use a contrast-safe colour on each surface: #2E616B on light backgrounds (5.2:1 or better), #7EACB5 on dark (5.1:1).
- The skip link appears on focus.
- Muted text, the "Illustrative" labels, grade stamps and tag colours meet 4.5:1 on ivory.
- The "first instinct" control is now toggle buttons (`aria-pressed`) in a labelled group, not a fake tablist.
- Required fields carry `aria-required` and `aria-describedby`.
- The chatty live region on the timeline was removed.
- The promise section has a real heading.

### Robustness, performance and document head (H9–H11, refinements)
- **Document head:** proper `<head>`, `lang="en-GB"`, meta description, Open Graph tags, theme colour and favicon.
- **three.js** loads with a Subresource Integrity hash.
- **Fallback text** now distinguishes "the library didn't load" from "WebGL is off".
- **Second 3D scene** (invitation) is created only when it nears the viewport. Both scenes stop their animation loops when off-screen or in a background tab.
- **Mobile:** the value proposition now comes before the 3D stage, and the stage is shorter (44vh). Overlapping hypothesis pins are hidden on phones (the same text is in the story). Before/after cards are stacked from measured heights, so they no longer overlap.
- **Investigation timelines** fade at the edge to show they scroll.
- **Dead CSS** removed (about 60 rules from earlier versions), plus duplicates.

### Legal and privacy (C16, partial)
- **Privacy notice dialog.** It describes what the page actually does: the form stays in the browser, no cookies or trackers are set, and fonts and the 3D library load from third parties.
- **No-affiliation line** for LEGO, Airbus and Costco.

## What was tested
I ran the test harness (Playwright, Chromium) against v5 at 1440, 1280, 768, 390 and 320px:
- **Errors:** zero JavaScript errors and zero failed requests.
- **Overflow:** none at any width.
- **Before/after cards:** no overlaps at any width (previously 1 overlap at 390px and 2 at 320px).
- **Controls:** every control was exercised and works:
  - scenario chips, instinct buttons, reveal next / reveal all / reset;
  - brief accordions, the three investigation dialogs (open, Escape, focus return, call to action), and the privacy dialog;
  - sound toggle, form validation, the request draft, copy and edit, and the timeline buttons.
- **Lab outcomes:** checked for all five scenarios.
- **Reduced motion:** no errors.
- **3D library blocked:** the correct fallback message shows and everything else still works.
- **Document:** HTML tag balance verified, and all head metadata is present.

**Not tested:**
- Real iOS or Android devices.
- Screen readers (VoiceOver, NVDA).
- Real-GPU performance (the headless browser uses software WebGL).
- Opening the cited source pages. The sandbox blocks those sites, so I verified facts through web search, which is weaker than reading the primary documents.

## Still unresolved: needs you
1. **Audience (D1).** Kept as founder-led companies, as now.
2. **Contact channel (D2).** The form still ends with "copy and paste into LinkedIn". No email address or booking link was added, because none was provided.
3. **Fees (D3).** Not shown.
4. **Founder bio (D4).** Unchanged apart from the heading. Practical experience and a photo are still needed. Nothing was invented.
5. **Privacy commitments.** The privacy dialog promises that enquiry details are used only to reply, are not shared or used for marketing, and are deleted on request. Confirm these are true before publishing. Add registered company details if the business is incorporated.
6. **™ marks.** "Decision Review™", "Decision Audit™" and "Decision Autopsy™" are unchanged. Check for conflicts before relying on them.
7. **Verify against primary documents before publishing:**
   - Costco fiscal 2025 operating income (~$10.4bn, from a secondary source).
   - LEGO 2001 and 2005 lines (now tagged "Reported").
   - The 2005 NYT article. It is cited by title only, with no link.
8. **Second 3D context.** Still two WebGL contexts once the invitation is reached. Making it one would need a larger refactor.

## Readiness
Credibility and accessibility have improved substantially, and the site is functionally sound. It is **not yet ready to publish** until items 2, 5 and 7 are settled. Items 1, 3, 4 and 6 are business decisions that don't block a soft launch.
