# Merged Issues — Semantic Deduplication

_Analysis date: 2026-07-02_
_Input: 126 issues across 6 designers_

---

## Section 1 — Flagged duplicates

**Group 1** [High confidence]
Canonical description: Launcher installs or downloads without prior warning, no system requirements shown, no explanation of what it does.
Matches: F-10, A-02, D-09
Rationale: All three describe the same moment — the user is prompted to install the Launcher (or a browser extension) mid-flow with no prior context, warning, or explanation of what will be installed or why. F-10 and A-02 are near-identical; D-09 adds the browser extension variant of the same pattern.

---

**Group 2** [High confidence]
Canonical description: Launcher/product is Windows-only but macOS users receive no warning and hit a complete blocker.
Matches: F-05, A-03, A-04
Rationale: All three describe macOS users being silently blocked because the product assumes Windows, with no in-product warning or OS detection. A-03 and A-04 name this explicitly; F-05 documents the broader pattern of silent Mac blockers across the DI setup flow.

---

**Group 3** [High confidence]
Canonical description: After clicking Run (playlist/test execution), no immediate feedback is given — no loading indicator, no confirmation the action was received.
Matches: J-24, G-09, G-06
Rationale: All three describe the same dead moment after hitting Run: the UI gives no signal that execution has started. J-24 notes only a cursor change; G-09 and G-06 confirm no loading indicator or post-action feedback exists.

---

**Group 4** [High confidence]
Canonical description: Test failure details are buried — require 3+ clicks to reach from the results screen.
Matches: G-07, G-11, J-17
Rationale: G-07 and G-11 both explicitly state "3 clicks minimum" to view failure details from the result screen. J-17 describes the same problem from a discoverability angle (red icon not obvious). All three target the same navigation gap to failure information.

---

**Group 5** [High confidence]
Canonical description: No autosave in the editor; a disruptive save prompt appears when navigating away, risking data loss.
Matches: G-20, D-28
Rationale: Both explicitly call out missing autosave in the editor and the friction of a blocking save dialog when leaving the screen. Same feature area (Builder/Playlist editor), same root problem.

---

**Group 6** [High confidence]
Canonical description: No option to name or configure a module before scanning begins.
Matches: G-19, D-16
Rationale: G-19 and D-16 describe the identical missing affordance: users cannot assign a module name prior to starting a scan, forcing renaming after the fact or confusion about where the scan output lands.

---

**Group 7** [High confidence]
Canonical description: XScan/scanner is extremely slow during scanning operations.
Matches: D-02, D-08, D-06
Rationale: D-02, D-08, and D-06 all report severe performance problems during the scan workflow — D-02 and D-08 name the scan itself; D-06 names the Launcher slowness that is part of the same execution chain. These are the same systemic performance problem reported from slightly different angles by the same designer; included as a group because they would consolidate into one ticket.

---

**Group 8** [High confidence]
Canonical description: Launcher fails silently with no actionable error message when something goes wrong during installation or startup.
Matches: F-08, F-09, F-11, D-05
Rationale: All four describe the Launcher (or a component it depends on) failing without surfacing a meaningful error. F-08 (antivirus quarantine → "Component executable not found"), F-09 (extension helper blocked, file named but no steps), F-11 (silent failure on extension connect), and D-05 (Launcher installed but failed silently) are the same pattern: failure with no recovery path.

---

**Group 9** [High confidence]
Canonical description: Running a test produces no reliable result summary or visual confirmation that execution completed.
Matches: G-22, J-28, G-10
Rationale: G-22 describes the only signal being a color change on the execution bar. G-10 notes no visual cue after action. J-28 shows "pending" status after a run has already completed. All three are the same gap: the UI does not clearly confirm test completion or show a result state.

---

**Group 10** [High confidence]
Canonical description: No in-product guidance for the DI setup flow; users are blocked by prerequisites (DB, agent path, Windows requirement) with no help surfaced in the UI.
Matches: F-01, F-03, F-05, J-03, J-20
Rationale: F-01 (no guidance on DB prerequisite), F-03 (no guidance on SQLite path), F-05 (entire flow assumes Windows without guidance), J-03 (user assumed DB connection needed — no help), and J-20 (empty result with no in-product help, user abandons) all point to the same systemic absence of contextual guidance in the DI setup and template flow. Confidence is high; the root cause is the same missing help layer.

---

**Group 11** [High confidence]
Canonical description: Scanning complex controls (dropdowns, floating menus, drag-and-drop, tables) is undiscoverable or impossible without external documentation.
Matches: AM-04, AM-06, AM-07, AM-12, G-03, G-05, G-08
Rationale: AM-04 (floating menus/dropdowns impossible without guides), AM-06 (re-scanning confusing, XScan doesn't refresh), AM-07 (drag-and-drop impossible without docs), AM-12 (tables very difficult), G-03 (XScan fails silently on Chrome incognito), G-05 (captures DIV instead of individual options), G-08 (cannot target individual buttons in grid rows) all describe the same class of problem: XScan cannot reliably capture non-trivial UI controls, and users have no in-product guidance when it fails.

---

**Group 12** [Medium confidence]
Canonical description: Scanned modules are saved to an unexpected location or workspace with no selector available during the scan flow.
Matches: G-04, D-03
Rationale: G-04 reports scanned modules landing in the wrong workspace because there's no workspace selector in the scan flow. D-03 reports the creator not being auto-added to their own workspace (a related workspace-routing problem). The root mismatch is the same — workspace assignment is invisible and wrong by default — though the trigger differs slightly.

---

**Group 13** [Medium confidence]
Canonical description: Error messages name a symptom or internal detail rather than the actual cause, leaving users unable to diagnose the problem.
Matches: F-02, F-06, AM-22
Rationale: F-02 ("SQL command execution timed out" — symptom not cause), F-06 (Test Connection gives no indication it's server-side, timeout misread as failure), AM-22 ("couldn't find tab" when the real issue was buttons) all share the same UX failure: the error message misleads the user about what went wrong. Confidence is medium because the specific contexts differ but the root communication failure is identical.

---

**Group 14** [Medium confidence]
Canonical description: No feedback or confirmation is given after a key action (save, link, record step) — user cannot tell if the action succeeded.
Matches: F-04, A-05, A-06, J-04, J-18, D-27
Rationale: F-04 (caching checkbox — no feedback on existence/failure), A-05 (no download confirmation), A-06 (no confirmation a step was recorded), J-04 (linking test sheet — no confirmation), J-18 (no snackbar after creating instances), D-27 (no loading state on save) all describe the same pattern: a user-initiated action completes with no acknowledgment. Confidence is medium rather than high because the actions are distinct, but the missing-feedback pattern is the same systemic gap across the product.

---

**Group 15** [Medium confidence]
Canonical description: The "Create new module" or equivalent entry point is hidden, only reachable from a non-default tab or obscure location.
Matches: J-01, D-17, D-25
Rationale: J-01 (create template only reachable from single test case view), D-17 ("Create new module" only on non-default tab), and D-25 (no visible "create new test case" in builder) describe the same discoverability failure: primary creation actions are buried in non-obvious locations.

---

**Group 16** [Medium confidence]
Canonical description: Instantiation or template action reports success but produces no visible result, leaving users confused.
Matches: J-05, J-19, J-22
Rationale: J-05 (instantiation says "successful" but instances list shows "no results"), J-19 (template tab refreshes instead of navigating, causing rage clicks), and J-22 (Instantiate button disappears after save) describe the same template instantiation flow as broken — the system indicates or implies success but doesn't deliver a navigable outcome.

---

**Group 17** [Medium confidence]
Canonical description: No way to navigate back to the parent list from a detail page (module, test case).
Matches: AM-10, AM-21
Rationale: Both describe the same navigation dead-end: once inside a detail view (module page or test case), there is no back affordance to return to the list. Same problem, two contexts.

---

**Group 18** [Medium confidence]
Canonical description: Playlist results view and test run status are confusing or inconsistent — status labels don't reflect actual state.
Matches: J-28, D-29, D-30
Rationale: J-28 (shows "pending" after completed run), D-29 ("Test run" label is confusing), D-30 (partial selection runs all test cases — scope unclear in UI) all point to the same playlist results/status labeling being misleading about what actually ran or what state the run is in.

---

**Group 19** [Low confidence]
Canonical description: Workspace management surfaces are inconsistent or behave unexpectedly after key actions.
Matches: G-14, G-15, G-16, AM-01
Rationale: Giovanni's three workspace consistency issues (G-14, G-15, G-16) are described at a high level of abstraction in the source data; AM-01 (redirect to all workspaces list after creating a workspace rather than to the new workspace) may describe one of the same problems. Confidence is low because G-14/15/16 descriptions are sparse.

---

**Group 20** [Low confidence]
Canonical description: The Launcher repeatedly shows the same dialog or prompt on re-entry, which feels redundant and slows the workflow.
Matches: D-11, J-26
Rationale: D-11 (Launcher dialog appears on every re-scan) and J-26 (modal with prominent "Close agent" button during testing — poor modal design) both involve Launcher modal friction, but the specific problem differs. Confidence is low.

---

## Section 2 — Unique issues (no cross-designer match)

**Franc González:** F-07, F-12, F-13, F-15, F-16, F-17

**Angelika Zych:** A-01

**Jekaterina Aleksejeva:** J-02, J-06, J-07, J-08, J-09, J-10, J-11, J-12, J-13, J-14, J-15, J-16, J-21, J-23, J-25, J-27

**Giovanni Tocco:** G-01, G-02, G-12, G-13, G-17, G-18, G-21, G-23

**Diogo Lopes:** D-01, D-07, D-10, D-12, D-13, D-14, D-15, D-18, D-19, D-20, D-21, D-22, D-23, D-24, D-26

**Ana-Maria Neaga:** AM-02, AM-03, AM-05, AM-08, AM-09, AM-11, AM-13, AM-14, AM-15, AM-16, AM-17, AM-18, AM-19, AM-20

---

_Notes:_
- Some issues appear in multiple groups (e.g. F-05 in Group 2 and Group 10; AM-06 in Group 11).
- Issues listed as unique are either genuinely singular findings or lack sufficient description in the source data to cross-match with confidence.
- Giovanni's G-14, G-15, G-16, G-17, G-18, G-23 descriptions in the source file are placeholder-level; they may resolve into existing groups once full descriptions are available.
