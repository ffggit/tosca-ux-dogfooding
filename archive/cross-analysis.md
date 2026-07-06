# Cross-Designer UX Analysis — Tosca Cloud Dogfooding

_Analysis date: 2026-07-02_
_Input: 126 raw issues, 6 designers, 20 dedup groups_
_Critic review applied — iteration 1_

---

## 1. Overall Distribution

### Issues by severity

| Severity | Count | % of total |
|---|---|---|
| Critical | 8 | 6% |
| Major | 70 | 56% |
| Minor | 46 | 36% |
| Cosmetic | 2 | 2% |

> Major issues dominate at 56%. The concentration of Major-severity issues suggests systemic gaps rather than polish problems — the product has fundamental workflow blockers, not just cosmetic debt.

### Top 5 issue types by occurrence

| Rank | Issue type | Raw occurrences |
|---|---|---|
| 1 | Efficiency (friction, extra steps) | 48 |
| 2 | Help & guidance (missing) | 31 |
| 3 | Feedback (missing/misleading) | 29 |
| 4 | Consistency (behavioural/visual) | 23 |
| 5 | Language & clarity | 11 |

_Note: issue_type is multi-valued per issue; counts reflect tag occurrences across all 126 issues._

> Efficiency is the most pervasive issue type by a significant margin — nearly one-third of all issue-type tags. This signals that the product imposes unnecessary steps, workarounds, and repeated actions on users throughout core workflows. Feedback and Help & guidance together appear in 58 of 126 issues (46%): users cannot tell what happened, what went wrong, or what to do next. Both clusters represent primary UX debt and compound each other — inefficient workflows with no confirmation feedback are especially costly.

### Issues per designer

| Designer | Issues logged |
|---|---|
| Diogo Lopes | 30 |
| Jekaterina Aleksejeva | 28 |
| Giovanni Tocco | 23 |
| Ana-Maria Neaga | 22 |
| Franc González | 17 |
| Angelika Zych | 6 |
| **Total** | **126** |

---

## 2. Top 5 Cross-Designer Patterns

### Pattern 1 — No feedback after user action

**Designers affected:** Franc, Angelika, Jekaterina, Diogo (4 of 6)
**Deduplicated issue count:** 1 root pattern; reported across 6 individual issues (F-04, A-05, A-06, J-04, J-18, D-27)
**Severity peak:** Major

Across four designers, the product consistently fails to acknowledge that a user-initiated action completed. Users click Save, Download, Record, or Link and receive no confirmation — no snackbar, no loading state, no state change. This pattern spans the Launcher, ARA recording, test sheet linking, and playlist save. The root cause is a missing feedback layer at the interaction level: the product appears to treat confirmations as optional rather than mandatory. The user impact is compounded uncertainty — users retry actions, cause duplicate operations, or abandon the flow entirely.

---

### Pattern 2 — Launcher silent failure

**Designers affected:** Franc, Angelika, Diogo (3 of 6)
**Deduplicated issue count:** 1 root pattern; 4 source issues (F-08, F-09, F-11, D-05)
**Severity peak:** Major

When the Launcher or a component it depends on fails — due to antivirus quarantine, a missing extension helper, or a failed extension connection — the UI either shows a generic error ("Component executable not found") or shows nothing at all. No recovery steps, no diagnosis, no fallback. Three designers hit this independently across different failure modes, which signals that the Launcher's error surface is uniformly poor regardless of the specific failure cause. The user impact is a complete workflow block with no self-service recovery path.

---

### Pattern 3 — XScan cannot handle complex controls

**Designers affected:** Giovanni, Ana-Maria (2 of 6, but 7 source issues)
**Deduplicated issue count:** 1 root pattern; 7 source issues in Group 11 (AM-04, AM-06, AM-07, AM-12, G-03, G-05, G-08)
**Severity peak:** Critical

Two designers independently discovered that XScan cannot reliably capture non-trivial UI controls: floating menus, dropdowns (captures the container DIV rather than individual options), drag-and-drop interactions, and tables. When XScan fails at these controls, it either silently captures the wrong element or produces no guidance on what to do. Ana-Maria rated three instances Critical (AM-04, AM-07, AM-12). The root cause is a technical limitation in the scan engine combined with a complete absence of in-product guidance for edge cases. For automation-heavy workflows, this is a fundamental capability gap.

---

### Pattern 4 — No post-run feedback or result summary

**Designers affected:** Jekaterina, Giovanni (2 of 6, both Groups 3 and 9)
**Deduplicated issue count:** 2 overlapping patterns; 6 source issues (J-24, G-09, G-06, G-22, J-28, G-10)
**Severity peak:** Major

After clicking Run, the UI offers no loading indicator and no confirmation the action was received (Group 3). Once execution completes, the only signal is a color change on the execution bar — no result summary, no clear pass/fail (Group 9). J-28 documents the result view showing "pending" after the run has already finished. These two patterns are adjacent: the product has no clear start signal and no clear end signal for test execution. Users cannot tell whether the product is working or has silently failed.

---

### Pattern 5 — Missing in-product guidance for setup prerequisites

**Designers affected:** Franc, Jekaterina (2 of 6, 5 source issues in Group 10)
**Deduplicated issue count:** 1 root pattern; 5 source issues (F-01, F-03, F-05, J-03, J-20)
**Severity peak:** Major

The Data Integrity setup flow and template instantiation flow share a common failure: the product presents a complex prerequisite-dependent workflow with no contextual help. Users encounter requirements — a working database, a SQLite file on the agent machine, a Windows-only Launcher — only when they hit the blocker, not before. Jekaterina's J-20 shows the downstream consequence: when instantiation silently fails, the user has no in-product path to diagnose it and abandons to external documentation. The root cause is a missing progressive-disclosure help layer throughout the setup experience.

---

## 3. Most Affected Product Areas

| Rank | Feature area | Raw issue count | Designers affected | Dominant issue type |
|---|---|---|---|---|
| 1 | XScan / Scanner / Module editor | 20 | Giovanni, Diogo, Ana-Maria (3/6) | Efficiency, Help & guidance |
| 2 | Launcher (install, execution, error handling) | 16 | Franc, Angelika, Jekaterina, Giovanni, Diogo (5/6) | Feedback, Help & guidance |
| 3 | Test case templates & instantiation | 16 | Jekaterina (primary), Franc (partial) | Feedback, Consistency |
| 4 | Playlist (editor, run, results) | 16 | Franc, Jekaterina, Giovanni, Diogo (4/6) | Feedback, Consistency |
| 5 | Data Integrity setup | 10 | Franc, Jekaterina (2/6) | Help & guidance, Feedback |

_Counting notes: XScan/Module editor includes all issues with XScan, Scanner/XScan, Module editor, or XScan+ARA in feature_area (G-03, G-05, G-08, G-21; D-01, D-02, D-07, D-08, D-10, D-11, D-12, D-13, D-14, D-17; AM-04, AM-05, AM-06, AM-07, AM-12, AM-14). Launcher count includes issues where feature_area contains "Launcher" plus Angelika's A-02, A-03, A-04 which describe Launcher install problems under Settings/Inventory labels._

> XScan / Scanner / Module editor is the highest raw-issue area. The Launcher is the broadest area by designer reach — it is the only area touched by 5 of 6 designers — and remains a systemic failure surface. Test case templates and Playlist areas are tied at 16 issues each, indicating that the end-to-end test authoring and execution workflow carries consistent UX debt across multiple personas.

---

## 4. Severity Concentration — Critical Issues

| Issue ID | Designer | Description | Cross-designer? |
|---|---|---|---|
| A-04 | Angelika Zych | Launcher is Windows-only; macOS user receives no warning, completely blocked | Yes — Group 2 (F-05, A-03, A-04) |
| J-05 | Jekaterina Aleksejeva | Instantiation reports "successful" but instances list shows "no results" — false success | Yes — Group 16 (J-05, J-19, J-22) |
| J-20 | Jekaterina Aleksejeva | No in-product help to diagnose empty instantiation result; user abandons to docs | Yes — Group 10 (F-01, F-03, F-05, J-03, J-20) |
| G-01 | Giovanni Tocco | No service account or token-based auth; entire automation setup blocked | No — unique to Giovanni |
| D-04 | Diogo Lopes | Scan fails to blank page; task completely blocked | No — unique to Diogo |
| AM-04 | Ana-Maria Neaga | Cannot scan floating menus, dropdowns, or navigation without external guides | Yes — Group 11 (7 issues) |
| AM-07 | Ana-Maria Neaga | Impossible to scan drag-and-drop without documentation | Yes — Group 11 |
| AM-12 | Ana-Maria Neaga | Very difficult to scan tables and automate table scenarios | Yes — Group 11 |

**Summary:** 8 Critical issues total. 6 of 8 are cross-designer (appear in dedup groups). The two unique Criticals — G-01 (no service account auth) and D-04 (scan to blank page) — are high-risk because they are complete task blockers that no other designer encountered, suggesting they may be path-specific or environment-specific failures that could affect any user in that workflow.

---

## 5. Coverage Gaps

Areas flagged by only one designer that likely represent under-explored workflows or feature-specific problems:

### Gap 1 — Authentication / service account setup (Giovanni only)
G-01 and G-02 describe a complete blocker when no service account or token-based auth is available, requiring a multi-step manual workaround. No other designer explored this path. This is a CI/CD-integration scenario that is likely common among developer-persona users but was not reached by the other five designers.

### Gap 2 — Data Integrity module (Franc only, partially Jekaterina)
The full DI setup flow — database prerequisites, SQLite agent path, caching checkbox — was only tested deeply by Franc. Jekaterina encountered the template side. Four designers never reached DI at all, suggesting this is either gated by configuration complexity or was deprioritised. The 10 DI issues logged are likely a fraction of the real surface.

### Gap 3 — ARA (Ara recording) (Angelika and Ana-Maria only, partially)
A-06 and AM-13 are the only ARA-specific issues logged. Angelika found no confirmation after recording a step; Ana-Maria found a broken documentation link. No designer explored the full ARA workflow. Given that ARA is a core capture feature, the low coverage is a significant analysis gap.

### Gap 4 — Builder — SQL Editor (Franc only)
F-13 ("Unknown Connection"; Run SQL disabled with no tooltip) is the only SQL Editor issue in the set. The SQL Editor is a specialised but high-stakes tool for data-driven testers. One Major issue with no cross-designer confirmation is a gap.

### Gap 5 — Inventory object management (Ana-Maria and Diogo primarily)
AM-15, AM-16, D-13, D-14, D-23, and D-24 cover inventory browsing, module reuse, and object disambiguation — areas that were not meaningfully explored by Franc, Angelika, Jekaterina, or Giovanni. These are likely daily-use workflows for experienced users that the dogfooding sessions did not reach.

---

## 6. Data Quality Notes

### Giovanni's sparse issues (G-14, G-15, G-16, G-17, G-18, G-23)
Six of Giovanni's 23 issues have placeholder-level descriptions in the source data. G-14, G-15, and G-16 are described only as "Workspace management consistency issue" with no detail. G-17 and G-18 are "Builder efficiency issue" with no specifics. G-23 is "Execution efficiency issue." These six issues cannot be reliably cross-matched, categorised beyond their assigned labels, or used as evidence in any pattern analysis. They are included in raw counts but excluded from dedup group analysis. Resolution requires Giovanni to expand descriptions.

### Diogo's performance issues (D-02, D-06, D-08)
Three separate Diogo issues report scan/Launcher slowness. The dedup file groups them as the same systemic performance problem. However, without performance metrics or reproduction steps, it is not possible to determine whether these are one root cause (e.g., a Launcher startup bottleneck) or multiple separate regressions. Treated as one pattern for this analysis; should be validated with engineering.

### Ana-Maria's source format (Confluence vs. GitHub)
Ana-Maria's 22 issues were ingested from Confluence rather than GitHub. The descriptions are generally well-structured, but severity and issue_type assignments appear to have been applied retroactively during the merge, not by Ana-Maria herself. Any severity-based comparison between Ana-Maria's issues and GitHub-sourced issues should account for this normalization risk.

### Angelika's low issue count (6 issues)
Angelika logged the fewest issues (6) and her scope was narrow — primarily Launcher install and onboarding. It is unclear whether this reflects a shorter session, a smooth experience beyond that scope, or incomplete reporting. Her issues are high-signal but do not cover enough of the product surface to draw comparative conclusions.
