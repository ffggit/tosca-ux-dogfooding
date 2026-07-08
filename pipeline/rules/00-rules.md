# UX Issue Consolidation Ruleset v2 — Problem/Description-Centric

Governs consolidating the 328 raw issues in `10-allissues.md` into `OVL-###` rows. Replaces the fix-centric test with a **problem-identity** test. Files 06/08 over-merged by lumping issues that only shared a feature area, a theme/sentiment, or a coarse severity. Calibrated to prevent that while catching genuine duplicates.

## 1. Prime Directive
A merge asserts that two issues are **the same problem described twice** — the same user-experienced failure/gap at the same point in the product. Not clustering by topic; declaring "these rows are one problem."
- Judge on the problem itself, not the fix. Ground every decision in the **Description** (supported by **Screen/page/component** + **Flow/step**). Ask: what is going wrong for the user, and where? Merge only when the answer is the same for both.
- **Ignore the "Fix hypothesis" column when deciding.** Same suggested fix can be different problems; different fix can be the same problem. Do not use fix text as a merge or anti-merge signal.
- When in doubt, keep separate. Wrong merge destroys a distinct problem's signal; missed merge only leaves a duplicate. Bias toward DO NOT MERGE.

## 2. Definitions
- **Root cause / problem:** the specific thing going wrong from the user's POV, as stated in the Description. The unit of merge.
- **Locus:** where it happens = Screen/page/component + Flow/step. Same feature but different screen/step = different locus.
- **Capability:** a named function that does not exist (copy-paste, undo, Buffer Viewer, auto-save, cross-workspace asset sharing). A missing capability is a problem in its own right.
- **Symptom:** an observable surface effect (slowness, "failed" with no reason). Same symptom can arise from different root causes — symptom-match is not problem-match.
- **Lifecycle stage:** install/setup, onboarding/first-run, authoring/build, scanning, execution/run, results/debugging, migration/upload, admin/workspace. Same stage is prerequisite; different stage is a hard blocker.
- **Theme / sentiment:** broad attitude/category ("bad UX," "on-prem parity," "too slow," "not intuitive," "missing features"). Never a merge basis.

## 3. Merge Criteria (M-rules) — need ≥1 M-rule AND all X-rules clean
- **M1 — Same problem, same locus, different words.** Core positive test.
- **M2 — Same specific defect/behaviour across sources.** Shared Jira may corroborate, but the Description is the basis — never merge on Jira ID alone.
- **M3 — Same named missing capability** (same specific gap, not merely same feature area).
- **M4 — Same instance of a general failure** (same identical error/behaviour, same action, same flow).
To fire an M-rule, write ONE concrete sentence naming the shared problem + locus. If you cannot, no M-rule fires.

## 4. Anti-Merge Hard Blockers (X-rules) — any one → DO NOT MERGE
- **X1** shared feature/area insufficient. **X2** shared theme/sentiment insufficient. **X3** different root cause/problem. **X4** different UI element/screen/flow-step. **X5** symptom vs cause. **X6** specific instance vs general capability. **X7** different lifecycle stage. **X8** vague MUST NOT absorb specific. **X9** severity is not a merge basis. **X10** OS/platform-specific ≠ general.
- (No fix-hypothesis X-rule — fixes are out of scope; do not reason about them.)

## 5. Decision Procedure — ordered gates (stop at first that resolves)
- **Gate 0 — Restate each problem** as `<what's going wrong> at <locus: screen + flow-step> in <lifecycle stage>` using only Description/Screen/Flow. If you cannot state it from the Description, treat as vague (X8).
- **Gate 1 — Same lifecycle stage?** No → DO NOT MERGE (X7).
- **Gate 2 — Same locus?** No → DO NOT MERGE (X4).
- **Gate 3 — Same root cause/problem** (not just area/theme)? No → DO NOT MERGE (X1/X2/X3).
- **Gate 4 — Same granularity?** Instance-vs-capability or specific-vs-vague → DO NOT MERGE (X6/X8).
- **Gate 5 — Any remaining X-rule (X5, X10, X9)?** Fire → DO NOT MERGE.
- **Gate 6 — Does an M-rule fire, statable in one sentence?** Yes → MERGE. Cannot state cleanly → BORDERLINE.
- **Default: BORDERLINE → DO NOT MERGE.** Never let fix/feature/severity similarity push a BORDERLINE into MERGE.

## 6. Granularity Guidance
- One OVL = one described problem at one locus. Members spanning different screens/steps/stages → too broad, split.
- Smuggled-theme test: if the only sentence covering all members is a theme, it's a theme, not a problem. Split.
- Cross-source merges allowed but require problem + locus evidence in the Descriptions (not shared Feature/sentiment).
- Same-source near-duplicates are the safest merges.
- Deliberately-split families stay split.
- Singletons are valid and expected (most rows).

## 7. Borderline Handling
Default DO NOT MERGE. Record member IDs, the gate that stalled, the specific ambiguity. Flag for the challenger. Do not resolve a borderline via shared fix/feature/severity.

## 8. Evidence & Documentation (every OVL)
- Specific problem-based title (what goes wrong + where; not a theme, not a fix).
- All member IDs.
- One-sentence shared described problem (the Gate 0 restatement).
- Shared locus (screen/component + flow-step).
- Lifecycle stage.
- M-rule cited + explicit confirmation X-rules are clean.
- Verbatim-preserved member data — each member's original Description/columns unchanged. Never overwrite/paraphrase source text.
- Singletons documented with a single member, note "singleton — no duplicate found"; no M-rule required.

## 9. Worked Examples (real IDs from 10-allissues.md)
SHOULD merge:
1. GS-011 + GS-040 + GS-054 + GS-055 + GS-057 + GS-060 — scan/Create-Module fails/does not launch/errors at Inventory > Create Module — Start Scan (M1/M2).
2. IN-008 + GS-050 + GS-048(undo part) — named "undo / recover deleted" capability in Builder; GS-048's Vision-AI portion must NOT be dragged in (M3).
3. IN-021 + IN-001 — cannot jump from a failed run step to the exact module/step in Builder, Test runs → Builder (M1).
4. TC-042 + GT-014 + DL-028 + IN-009 — named "auto-save / prevent data loss" capability in Builder authoring (M3).
5. FG-014 + GS-009 — merge ONLY if both read as same scan-session-locks-machine locus; else borderline (locus-hinged cross-source example).

SHOULD NOT merge:
1. GS-012 ("UX/UI is bad") vs GS-011 (scan fails) — X2+X8.
2. GT-018 (no end-of-run summary) vs GT-020 (no run-started feedback) — X4/X7.
3. TC-096 (templates upload as test cases — migration) vs GS-007 (attributes don't flow on re-instantiation — runtime) — X7+X3.
4. On-prem parity sentiment rows (GS-005/020/026/036/047) vs specific gaps (IN-011 Buffer Viewer, IN-007 shortcuts) — X2+X8.
5. FG-009 (Chrome extension install UPDATE_DISABLED on VM) vs GT-011 (XScan fails on Chrome incognito) — X10+X3.
