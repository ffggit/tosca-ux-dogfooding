# 08 — Affinity Map: All Feedback Consolidated (Validated)
_Both Designers [D] and Testers [T] feedback merged into thematic clusters, with duplicates and misplacements corrected._

**Total issues:** 188 across 21 clusters ([D] 82 · [T] 106)

---

## Validation report

- **Total issues reviewed:** 188 (across 21 clusters; [D] 82 · [T] 106)
- **Duplicates resolved:** 8 (7 from pre-analysis + 1 found during review)
  - TC-041 — kept in Cluster 11, removed from Cluster 16
  - TC-028 — kept in Cluster 15, removed from Cluster 8
  - DL-026 — kept in Cluster 14, removed from Cluster 11
  - TC-064 — kept in Cluster 3, removed from Cluster 14
  - TC-091 — kept in Cluster 14, removed from Cluster 21
  - TC-108 — kept in Cluster 20, removed from Cluster 18
  - FG-013 — kept in Cluster 5, removed from Cluster 20
  - DL-030 — kept in Cluster 3 (Execution Feedback), removed from Cluster 14 (Playlist) *(found during review — was duplicated in the 07 map)*
- **Misplaced issues corrected:** 10
  - TC-096 — Cluster 7 (Template Authoring) → Cluster 18 (Migration Correctness Bugs)
  - JA-019 — Cluster 14 (Playlist) → Cluster 7 (Template Authoring)
  - JA-020 — Cluster 14 (Playlist) → Cluster 7 (Template Authoring)
  - TC-007 — Cluster 20 (Credentials) → Cluster 12 (Navigation & Editor Ergonomics)
  - TC-006 — Cluster 20 (Credentials) → Cluster 13 (Default Values & Properties)
  - TC-045 — Cluster 16 (Bulk Operations) → Cluster 21 (UI Consistency)
  - TC-050 — Cluster 16 (Bulk Operations) → Cluster 21 (UI Consistency)
  - TC-044 — Cluster 16 (Bulk Operations) → Cluster 9 (Onboarding & Settings)
  - TC-085 — Cluster 21 (UI Polish) → Cluster 12 (Navigation & Editor Ergonomics)
  - TC-074 — Cluster 21 (UI Polish) → Cluster 6 (Module Management)
- **Additional issues found beyond the pre-analysis list:** 1 duplicate — DL-030 appeared in both Cluster 3 and Cluster 14 in the 07 map; resolved to Cluster 3, where subset-vs-all run behaviour belongs with the execution-feedback findings. No further misplacements were found; a full re-review of every cluster confirmed all remaining issues fit their cluster title and summary once the above moves were applied.
- **Notes:** Cluster 9 renamed to "Onboarding, Homepage, Guidance & Notification Settings" to absorb TC-044. Cluster 6 summary widened to include the folder-path finding (TC-074). Cluster 20 shrank to 2 issues but is retained per instructions. All clusters reordered Critical → Major → Minor → Cosmetic, with related items grouped within each severity.

---

## Cluster 1: Launcher / E2G Setup & Agent Start
**Issues:** 9 ([D] 7 · [T] 2) | **Highest severity:** Critical

Installing, downloading, starting, and connecting the E2G agent (Launcher) is the very first thing new users must do, and it fails in many ways. Designers documented silent OS-detection failures, antivirus blocks, and confusing reinstall loops; Testers framed the same pain as a need for a clean install-and-start button and support for multiple simultaneous agents.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-002 | [D] | Critical | OS detection fails silently on macOS — Windows .exe auto-downloads, no Mac Launcher (2 designers) | `04-final.md · L15` |
| OVL-001 | [D] | Major | Launcher install prompt appears with no warning, no system requirements, no explanation (3 designers) | `04-final.md · L14` |
| OVL-003 | [D] | Major | Launcher failure states: antivirus quarantine, raw error codes, silent failure requiring reinstall (2 designers) | `04-final.md · L16` |
| FG-014 | [D] | Major | IT-managed antivirus blocks Launcher with no in-product guidance | `04-final.md · L41` |
| DL-011 | [D] | Major | Every rescan re-shows "first time scanning? download launcher" despite Launcher being installed | `04-final.md · L86` |
| DL-006 | [D] | Major | Sustained extreme slowness from Launcher blocked the core scanning loop | `04-final.md · L82` |
| TC-021 | [T] | Major | E2G/Launcher setup flow unintuitive: need a button to install and start agent without a dummy test run (TOSCA-41023) | `tosca-cloud-improvement-requests.md · L40` |
| TC-106 | [T] | Major | Need to run multiple E2G agents simultaneously (team + personal) from Launcher (TOSCA-37159) | `tosca-cloud-improvement-requests.md · L152` |
| GT-006 | [D] | Minor | Launcher cannot be opened manually; no shortcut, no entry point in UI | `04-final.md · L69` |

**Insight:** Both sources converge on the Launcher as a critical first-run cliff — Designers see broken failure states and silent OS detection, while Testers want it operational without side effects, together making setup the single most urgent onboarding barrier.

---

## Cluster 2: Scanning & XScan Capability
**Issues:** 11 ([D] 9 · [T] 2) | **Highest severity:** Critical

The scanning engine fails silently on complex UI controls, performs poorly, and does not refresh scan state. Designers detail deep capability gaps (floating menus, drag-and-drop, tables) and modelling guidance holes; Testers focus on reducing scan friction and adding a scan entry point in Inventory.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-009 | [D] | Critical | XScan cannot scan floating menus, drag-and-drop, tables, grid buttons; rescan doesn't refresh (2 designers) | `04-final.md · L22` |
| DL-004 | [D] | Critical | Scan did not launch; blank page with no error — task blocked entirely | `04-final.md · L81` |
| AMN-005 | [D] | Major | Cannot clear changes in XScan without saving or closing | `04-final.md · L101` |
| AMN-014 | [D] | Major | No uniqueness warning before scanning; identification errors appear only at run time | `04-final.md · L106` |
| DL-008 | [D] | Major | Scan and rescan extremely slow — cumulative time loss | `04-final.md · L84` |
| DL-010 | [D] | Major | Controls under popups can't be selected directly; manual workaround with Xscan filter slider | `04-final.md · L85` |
| DL-007 | [D] | Major | No guidance on how to model a module (per action? with/without verification steps?) | `04-final.md · L83` |
| DL-012 | [D] | Major | data-test id attribute values must be in a very specific format or they fail silently; required external help | `04-final.md · L87` |
| GT-015 | [D] | Major | Rescan function not discoverable from test case editor or from a failed run | `04-final.md · L73` |
| TC-005 | [T] | Minor | Add a scan button directly in Inventory | `tosca-cloud-improvement-requests.md · L15` |
| TC-084 | [T] | Cosmetic | Reduce click count when scanning a new module from the test case builder (currently 4 steps) | `tosca-cloud-improvement-requests.md · L124` |

**Insight:** The two lenses are complementary — Designers expose that scanning silently fails on real-world controls (a trust-breaking capability gap), while Testers assume scanning works and just want it faster and closer at hand, revealing a maturity gap between the two audiences' experiences.

---

## Cluster 3: Test Execution Feedback & Run Results
**Issues:** 13 ([D] 7 · [T] 6) | **Highest severity:** Major

Triggering a run gives no immediate acknowledgment, results are not surfaced in context, and navigating from a result to the failing item is hard. Both sources report the same core loop: unclear run state, buried failures, and confusing run/rerun terminology.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-004 | [D] | Major | No feedback after clicking Run: cursor-change only; multiple clicks silently created duplicate runs (3 designers) | `04-final.md · L17` |
| OVL-005 | [D] | Major | Run results not surfaced: generic "failed" status, 3+ clicks to find which tests failed (3 designers) | `04-final.md · L18` |
| DL-021 | [D] | Major | Cancelling a run extremely slow on failed scenarios | `04-final.md · L94` |
| DL-030 | [D] | Major | Selecting subset of tests in playlist still ran all of them — no explanation | `04-final.md · L98` |
| GT-021 | [D] | Minor | No live progress bar during execution; On Prem Commander shows clearer indicator | `04-final.md · L77` |
| JA-024 | [D] | Minor | After execution, run still showed as 'pending' in playlist | `04-final.md · L61` |
| DL-022 | [D] | Minor | "Cancel run" CTA + "Stop it immediately" checkbox feels redundant; unclear why both exist | `04-final.md · L95` |
| TC-055 | [T] | Minor | No direct navigation from run result to the specific failing module or RTSB (TOSCA-34497) | `tosca-cloud-improvement-requests.md · L92` |
| TC-022 | [T] | Minor | Cannot expand/collapse individual test steps during execution | `tosca-cloud-improvement-requests.md · L41` |
| TC-026 | [T] | Minor | No explicit signal when a module or RTSB reference is missing during execution | `tosca-cloud-improvement-requests.md · L45` |
| TC-051 | [T] | Minor | Test Runs and Playlist Run History pages should be aligned or consolidated | `tosca-cloud-improvement-requests.md · L88` |
| TC-064 | [T] | Cosmetic | "Test runs" and "Rerun failed test" terminology confusing; both operate on playlists | `tosca-cloud-improvement-requests.md · L101` |
| TC-086 | [T] | Cosmetic | Run completion indicator (red dot disappearing) not visually prominent enough | `tosca-cloud-improvement-requests.md · L126` |

**Insight:** Strong dual signal — both audiences independently flag the absence of run acknowledgment and the difficulty of tracing a failure to its source, confirming the execution feedback loop as a high-confidence, product-wide weakness.

---

## Cluster 4: Autosave & Data Loss Prevention
**Issues:** 3 ([D] 1 · [T] 2) | **Highest severity:** Major

Users lose work because editors lack autosave, save dialogs are disruptive, and there is no session-expiry warning. Designers report the anxiety and interruption; Testers add the session-timeout risk and a stale save-button state.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-006 | [D] | Major | No autosave in test case editor or playlist editor; data-loss anxiety and frequent disruptive save dialogs (2 designers) | `04-final.md · L19` |
| TC-042 | [T] | Major | No autosave mode or session-expiry warning to prevent data loss | `tosca-cloud-improvement-requests.md · L79` |
| TC-087 | [T] | Cosmetic | Save button remains enabled even when there are no pending changes | `tosca-cloud-improvement-requests.md · L127` |

**Insight:** Both sources independently identify autosave as missing — a small, well-scoped fix with disproportionately high impact on user trust and confidence.

---

## Cluster 5: Error Messages & Diagnostics
**Issues:** 6 ([D] 3 · [T] 3) | **Highest severity:** Major

Errors describe symptoms rather than causes, offer no recovery path, and sometimes surface raw codes or fail silently. Designers document the worst cases (silent extension failure, "Unknown Connection"); Testers ask for actionable next steps and better handling of server errors.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-008 | [D] | Major | Errors show symptoms not causes: SQL timeout, Test Connection failure, "couldn't find tab" (2 designers) | `04-final.md · L21` |
| FG-013 | [D] | Major | SQL Editor shows "Unknown Connection" with no explanation; Run SQL disabled with no tooltip | `04-final.md · L40` |
| FG-012 | [D] | Major | Browser extension fails silently; user lands back on Builder with no error or notification | `04-final.md · L39` |
| TC-058 | [T] | Minor | Error messages must include actionable next steps | `tosca-cloud-improvement-requests.md · L95` |
| TC-049 | [T] | Minor | On server error (502), user redirected to Default workspace instead of last-used | `tosca-cloud-improvement-requests.md · L86` |
| TC-057 | [T] | Minor | No error shown when user types an agent characteristic tag but does not press Enter | `tosca-cloud-improvement-requests.md · L94` |

**Insight:** The combination shows a systemic diagnostics gap: Designers catch silent/opaque failures at the extremes while Testers describe the everyday erosion of trust, together arguing for a product-wide error-messaging standard.

---

## Cluster 6: Module Management — Search, Naming & Save Location
**Issues:** 11 ([D] 5 · [T] 6) | **Highest severity:** Major

Finding, naming, and saving modules breaks at multiple points: search is polluted by standard modules, names auto-generate before you can set them, and both save location and current asset path are hard to locate. Both sources report search and location confusion; Testers add tree-retention, reference-visibility, and folder-path gaps.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-015 | [D] | Major | User assets tab not default; standard modules pollute search results; distinction unclear (2 designers) | `04-final.md · L28` |
| OVL-016 | [D] | Major | Module names auto-generated with no option to name before scanning; save location easy to overlook (2 designers) | `04-final.md · L29` |
| GT-010 | [D] | Major | Module search requires knowing module names; no guidance for entry-level users | `04-final.md · L72` |
| AMN-015 | [D] | Major | Inventory cumbersome without preview of what's inside objects | `04-final.md · L107` |
| TC-074 | [T] | Major | Builder doesn't show asset folder path; users can't locate current module/RTSB | `tosca-cloud-improvement-requests.md · L114` |
| AMN-016 | [D] | Minor | No way to see where a module is used from Inventory | `04-final.md · L108` |
| TC-014 | [T] | Minor | Module search doesn't reset when switching between Standard objects and User assets tabs | `tosca-cloud-improvement-requests.md · L27` |
| TC-063 | [T] | Cosmetic | New module not auto-added to current test case after creation | `tosca-cloud-improvement-requests.md · L100` |
| TC-069 | [T] | Cosmetic | When viewing a specific module, full module list on the left is not retained | `tosca-cloud-improvement-requests.md · L106` |
| TC-070 | [T] | Cosmetic | Newly created module location not highlighted in module tree after saving | `tosca-cloud-improvement-requests.md · L107` |
| TC-071 | [T] | Cosmetic | Module/RTSB references not shown before deletion | `tosca-cloud-improvement-requests.md · L108` |

**Insight:** Both audiences hit the standard-vs-user asset confusion and the invisibility of module location/path/usage, making module management a broad, evenly-weighted pain area rather than an edge case.

---

## Cluster 7: Test Case & Template Authoring
**Issues:** 15 ([D] 13 · [T] 2) | **Highest severity:** Major

Template creation is hard to find, instantiation is broken, and terminology conflates source data with generated instances; XL syntax lives outside the product. Designers dominate here with a deep trace of the entire template lifecycle, including instances that can't be deleted or run from the template page; Testers add review workflows.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-013 | [D] | Major | Template instantiation: reports success but produces nothing; Instantiate button disappears; Save and Instantiate gated separately (3 designers) | `04-final.md · L26` |
| OVL-014 | [D] | Major | "Test Sheets" means both source data and generated instances; no link preview (terminology collision) | `04-final.md · L27` |
| JA-002 | [D] | Major | "Create template" only exists when viewing individual test case; not in context menu or Create dropdown | `04-final.md · L46` |
| JA-003 | [D] | Major | Template editor looks identical to test case editor; unclear where you are after conversion | `04-final.md · L47` |
| JA-008 | [D] | Major | XL placeholder syntax not discoverable in-product; syntax errors silently block instantiation | `04-final.md · L49` |
| JA-009 | [D] | Major | Special characters in test sheet attribute names break instantiation with no upfront warning | `04-final.md · L50` |
| JA-007 | [D] | Major | Tab click in Test case templates doesn't return to top level; view just refreshes | `04-final.md · L48` |
| JA-014 | [D] | Minor | Concept of a template never explained at point of creation | `04-final.md · L53` |
| JA-017 | [D] | Minor | Cannot delete "No results" instance entry | `04-final.md · L54` |
| JA-018 | [D] | Minor | Clicking a generated instance doesn't show its content; found only via "Open in new window" | `04-final.md · L55` |
| JA-019 | [D] | Minor | Template instances cannot be deleted from template page; must navigate elsewhere | `04-final.md · L56` |
| JA-020 | [D] | Minor | Cannot run generated test cases from template page; only from test case page | `04-final.md · L57` |
| JA-021 | [D] | Minor | Cannot copy attribute name in Test Data; must switch tabs repeatedly to fill sheet | `04-final.md · L58` |
| TC-015 | [T] | Minor | Review workflow for test changes with comments (like GitHub PRs) | `tosca-cloud-improvement-requests.md · L28` |
| TC-031 | [T] | Minor | Precondition description field (text only) with clickable links to related test cases | `tosca-cloud-improvement-requests.md · L59` |

**Insight:** Designers reveal the template feature is nearly unusable end-to-end — discovery, instantiation, and management of generated instances all break — while Testers add process needs like review workflows, together showing templates are far below authoring-ready.

---

## Cluster 8: Cross-workspace Asset Sharing & Workspace Management
**Issues:** 7 ([D] 4 · [T] 3) | **Highest severity:** Critical

Assets cannot be shared across workspaces, workspace creation is broken, and membership/access is unclear. Designers detail the broken post-creation flow and access confusion; Testers rank cross-workspace sharing as their single Critical item and request contributor roles.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-001 | [T] | Critical | Asset sharing of reusables or modules across workspaces (TOSCA-31764) — single Critical on tester list | `tosca-cloud-improvement-requests.md · L11` |
| OVL-012 | [D] | Major | Workspace post-creation broken: creator not auto-added, "Go to workspace" gives access denied, redirected to full list (3 designers) | `04-final.md · L25` |
| OVL-007 | [D] | Major | Scanned modules land in wrong workspace; no selector during scan (2 designers) | `04-final.md · L20` |
| TC-105 | [T] | Major | No asset sharing across workspaces yet (TOSCA-31764) [migration context] | `tosca-cloud-improvement-requests.md · L151` |
| GT-003 | [D] | Minor | "Go to workspace" button after creation is tertiary action; not visually prominent | `04-final.md · L67` |
| AZ-001 | [D] | Minor | "All users have access" message unclear about what type of access is granted | `04-final.md · L64` |
| TC-062 | [T] | Cosmetic | Allow contributors to delete tests; introduce read-only / read-write / admin roles (TOSCA-36335) | `tosca-cloud-improvement-requests.md · L99` |

**Insight:** Cross-workspace sharing is the highest-severity item on the tester list and is reinforced by designer evidence of a broken workspace lifecycle — a clear top-priority theme validated from both sides.

---

## Cluster 9: Onboarding, Homepage, Guidance & Notification Settings
**Issues:** 11 ([D] 6 · [T] 5) | **Highest severity:** Major

New users lack orientation, the homepage misleads, prerequisite knowledge is not surfaced at entry points, and notification settings are not configurable. Designers document the empty/misleading homepage and hidden prerequisites; Testers ask for tutorial videos, rethought home-page information architecture, and per-feature mail notification settings.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| OVL-010 | [D] | Major | Missing in-context guidance for DI, SQLite path, template flow — hidden prerequisites (4 issues) | `04-final.md · L23` |
| AMN-002 | [D] | Major | Homepage highly misleading for new users; empty dashboards draw all attention; no shortcuts or FTE tailoring | `04-final.md · L99` |
| AMN-003 | [D] | Major | Create "+" menu overwhelming; too many options with no guidance on where to start | `04-final.md · L100` |
| FG-015 | [D] | Minor | Agents page gives no indication which test types the cloud agent supports | `04-final.md · L42` |
| FG-016 | [D] | Minor | Test run dropdown shows no option to target a specific agent | `04-final.md · L43` |
| GT-005 | [D] | Minor | Sample test cases hard to find; terminology differs for On Prem users | `04-final.md · L68` |
| TC-056 | [T] | Minor | Add agent characteristics tutorial video | `tosca-cloud-improvement-requests.md · L93` |
| TC-044 | [T] | Minor | Configurable mail notification settings per feature/service (TOSCA-519, TOSCA-41509) | `tosca-cloud-improvement-requests.md · L81` |
| TC-061 | [T] | Cosmetic | Add short tutorial videos or documentation links for complex first-time scenarios | `tosca-cloud-improvement-requests.md · L98` |
| TC-065 | [T] | Cosmetic | Update the API tutorial video showing an outdated UI | `tosca-cloud-improvement-requests.md · L102` |
| TC-080 | [T] | Cosmetic | Reconsider home page content and information architecture; tutorials feel out of place | `tosca-cloud-improvement-requests.md · L120` |

**Insight:** Designers identify the structural cause (misleading homepage, hidden prerequisites) while Testers point to the missing remedies (tutorials, better IA, notification control), together making a complete case for a redesigned onboarding and settings entry point.

---

## Cluster 10: Authentication & Automation Blockers
**Issues:** 5 ([D] 5 · [T] 0) | **Highest severity:** Critical

MFA blocks automation entirely, BrowserArguments are ignored in playlists, and the Launcher can disrupt the user's own browser. This cluster is entirely from Designers, capturing hard automation blockers encountered during real dogfooding.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| GT-001 | [D] | Critical | MFA with YubiKey makes login impossible to automate; no service account or token-based option | `04-final.md · L65` |
| GT-002 | [D] | Major | Even without MFA, Okta login flow caused errors; had to skip login entirely | `04-final.md · L66` |
| GT-023 | [D] | Major | BrowserArguments at test case level ignored when run via Cloud agent playlist | `04-final.md · L78` |
| JA-012 | [D] | Major | Personal agent modal says "Don't close it!" but most prominent button is a large red "Close agent" | `04-final.md · L51` |
| JA-013 | [D] | Major | Launcher closed the user's own Chrome browser window during a test run | `04-final.md · L52` |

**Insight:** A designer-only blind spot for the tester feedback: these are hard automation blockers (MFA, browser hijacking) that surfaced only through hands-on designer dogfooding and would otherwise go unreported.

---

## Cluster 11: Copy-paste, Keyboard & Interaction Parity with Commander
**Issues:** 10 ([D] 3 · [T] 7) | **Highest severity:** Major

Users expect copy-paste, keyboard shortcuts, and drag-and-drop to work as in Commander, but all three are broken or missing. Testers dominate with explicit parity requests (copy-paste, shortcuts); Designers add missing undo/redo.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-008 | [T] | Major | Test creation slow: copy-paste missing, DnD differs from Commander (TOSCA-37666) | `tosca-cloud-improvement-requests.md · L21` |
| TC-009 | [T] | Major | Copy-pasting of test steps, values, or whole structures between test cases missing (TOSCA-37666) | `tosca-cloud-improvement-requests.md · L22` |
| TC-019 | [T] | Major | Copy-paste of blocks during test creation including keyboard shortcuts (TOSCA-37666) | `tosca-cloud-improvement-requests.md · L35` |
| TC-041 | [T] | Major | Full keyboard shortcut support across the product missing | `tosca-cloud-improvement-requests.md · L78` |
| DL-013 | [D] | Major | No undo/redo in module editor; reverting means manual re-clicking with risk to unsaved work | `04-final.md · L88` |
| TC-012 | [T] | Minor | Modules and RTSBs cannot be dragged across different windows into test cases (TOSCA-35021) | `tosca-cloud-improvement-requests.md · L25` |
| TC-013 | [T] | Minor | Double-click to expand test steps and items missing; must use expand arrow only | `tosca-cloud-improvement-requests.md · L26` |
| TC-047 | [T] | Minor | Context menu Delete only deletes one item when multiple test steps are selected | `tosca-cloud-improvement-requests.md · L84` |
| JA-022 | [D] | Minor | Click-to-rename playlist title does nothing; requires separate edit button | `04-final.md · L59` |
| JA-023 | [D] | Minor | Generated instances appear out of order (non-numeric/non-chronological) | `04-final.md · L60` |

**Insight:** Testers frame this as Commander-parity feature gaps while Designers frame it as basic interaction inconsistency — same root cause, and the combined volume marks it as a top authoring-productivity theme.

---

## Cluster 12: Navigation & Editor Ergonomics
**Issues:** 19 ([D] 9 · [T] 10) | **Highest severity:** Major

Dead-end navigation, missing back buttons, missing delete affordances, confusing panel layouts, and tabs that don't return to root. Evenly split between sources: Designers detail missing back/zero-state ergonomics; Testers detail tab proliferation, unclear titles/breadcrumbs, and non-intuitive delete flows.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-007 | [T] | Major | Delete button for modules/test cases/RTSBs when inside Builder view | `tosca-cloud-improvement-requests.md · L17` |
| OVL-017 | [D] | Minor | No back navigation from module detail page or test case editor (2 designers) | `04-final.md · L30` |
| DL-017 | [D] | Minor | "Create new module" only on non-default Clear Assets tab; repeated extra navigation | `04-final.md · L90` |
| DL-018 | [D] | Minor | Run CTA always reads "Run" even when a subset is selected; expected "Run selection" | `04-final.md · L91` |
| DL-025 | [D] | Minor | No visible "new test case" action within the builder itself; only hidden option | `04-final.md · L96` |
| AMN-017 | [D] | Minor | Active row concept breaks with multi-select: context menu acts only on active row | `04-final.md · L109` |
| AMN-018 | [D] | Minor | "View last run" button hard to find; very detached from the error in the name | `04-final.md · L110` |
| AMN-019 | [D] | Minor | Viewing runs of a test case detached from the test case; no dedicated tab | `04-final.md · L111` |
| AMN-020 | [D] | Minor | Properties tab lacks proper zero state on no selection and on selection with no properties | `04-final.md · L112` |
| AMN-008 | [D] | Minor | Triggering scan from Create new dialog gives no navigation feedback | `04-final.md · L102` |
| TC-046 | [T] | Minor | Too many browser tabs opened; should use pop-up or dockable panels | `tosca-cloud-improvement-requests.md · L83` |
| TC-048 | [T] | Minor | Inventory access path via "Build" navigation is unintuitive | `tosca-cloud-improvement-requests.md · L85` |
| TC-054 | [T] | Minor | Window/tab titles don't clearly describe the open component | `tosca-cloud-improvement-requests.md · L91` |
| TC-059 | [T] | Minor | Tree-to-panel selection and detail display relationship is confusing | `tosca-cloud-improvement-requests.md · L96` |
| TC-078 | [T] | Minor | Builder section pages lack clear page titles; users rely on icons | `tosca-cloud-improvement-requests.md · L118` |
| TC-085 | [T] | Cosmetic | Tree deletion flow is not intuitive | `tosca-cloud-improvement-requests.md · L125` |
| TC-072 | [T] | Cosmetic | Enable in-page navigation to minimise window openings and clicks | `tosca-cloud-improvement-requests.md · L109` |
| TC-068 | [T] | Cosmetic | Add asset type description to Builder breadcrumb header | `tosca-cloud-improvement-requests.md · L105` |
| TC-092 | [T] | Cosmetic | "Builder" header and "Builder" navigation option coexist and cause confusion | `tosca-cloud-improvement-requests.md · L132` |

**Insight:** The largest evenly-split cluster: both audiences repeatedly get lost, lack in-place actions, or spawn extra windows/tabs, confirming navigation ergonomics as a broad, structural (not cosmetic) problem despite mostly minor severities.

---

## Cluster 13: Default Values, Properties & Commander Data Parity
**Issues:** 10 ([D] 2 · [T] 8) | **Highest severity:** Major

Module default values don't auto-populate, "do nothing" steps clutter the view, parameters lack locking, and properties/values need to behave like Commander. Designers flag the manual-entry risk; Testers request auto-population, hiding, locking, and visual encoding that Commander already provides.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-010 | [T] | Major | Default module values should auto-populate test step values on instantiation (TOSCA-32789) | `tosca-cloud-improvement-requests.md · L23` |
| TC-011 | [T] | Major | Ability to hide "do nothing" steps and show only populated values, as in Commander (TOSCA-9589) | `tosca-cloud-improvement-requests.md · L24` |
| DL-014 | [D] | Minor | Module default values had to be entered manually; risk of missed values | `04-final.md · L89` |
| DL-020 | [D] | Minor | Test validation values had to be entered manually rather than auto-populated | `04-final.md · L93` |
| TC-016 | [T] | Minor | Action mode and data type dropdowns need better contrast and autocomplete | `tosca-cloud-improvement-requests.md · L29` |
| TC-017 | [T] | Minor | Add ValueRange support for RTSB parameters (TOSCA-36832) | `tosca-cloud-improvement-requests.md · L30` |
| TC-006 | [T] | Cosmetic | Lock mechanism for parameters to prevent unintended changes | `tosca-cloud-improvement-requests.md · L16` |
| TC-018 | [T] | Cosmetic | Color coding for populated vs. unpopulated step values in SpecialExecutionTask builder | `tosca-cloud-improvement-requests.md · L31` |
| TC-066 | [T] | Cosmetic | Visual indicator for unused test case parameters | `tosca-cloud-improvement-requests.md · L103` |
| TC-067 | [T] | Cosmetic | Sort test case parameters alphabetically not by creation order | `tosca-cloud-improvement-requests.md · L104` |

**Insight:** Designers stumbled into the exact manual-entry pain that Testers explicitly request auto-population to solve — direct corroboration that default-value and parameter handling below Commander parity actively slows authoring.

---

## Cluster 14: Playlist & Test Organisation
**Issues:** 6 ([D] 1 · [T] 5) | **Highest severity:** Major

Playlists lack folder support and consistent add/manage behaviour at scale. Designers report the drag-only add and subset-run bugs; Testers request folders, a folder-creation affordance, multi-playlist assignment, and visibility of which tests live where.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| DL-026 | [D] | Major | Tests added to playlist via drag-only; inconsistent with "+" in test builder | `04-final.md · L97` |
| TC-043 | [T] | Major | No visibility of which test cases are in which playlists at scale | `tosca-cloud-improvement-requests.md · L80` |
| TC-020 | [T] | Minor | Proper assignment of test tasks with parameterised reusable blocks | `tosca-cloud-improvement-requests.md · L36` |
| TC-053 | [T] | Minor | Playlist tree has no folder support; doesn't match Test Cases tree | `tosca-cloud-improvement-requests.md · L90` |
| TC-060 | [T] | Minor | Cannot add a test case to multiple playlists at once (TOSCA-36736) | `tosca-cloud-improvement-requests.md · L97` |
| TC-091 | [T] | Cosmetic | No plus (+) icon for creating a new folder in Playlist view | `tosca-cloud-improvement-requests.md · L131` |

**Insight:** Designers hit playlist bugs during small-scale use while Testers describe organisational collapse at scale — together showing the playlist model doesn't grow with real team-sized test suites.

---

## Cluster 15: Reporting, Dashboards & Requirements
**Issues:** 5 ([D] 0 · [T] 5) | **Highest severity:** Major

Custom reports, cross-workspace dashboards, requirements linking, and test planning are all missing features. This cluster is entirely from Testers, reflecting their day-to-day reporting and traceability needs.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-027 | [T] | Major | Custom reports with pass/fail/not-executed counts, filterable by workspace, with templates | `tosca-cloud-improvement-requests.md · L49` |
| TC-028 | [T] | Major | Cross-workspace dashboards combining data from multiple workspaces | `tosca-cloud-improvement-requests.md · L50` |
| TC-029 | [T] | Major | Requirements and execution logs as a report view | `tosca-cloud-improvement-requests.md · L51` |
| TC-030 | [T] | Minor | Requirements linked to test cases with reporting for daily business use | `tosca-cloud-improvement-requests.md · L55` |
| TC-032 | [T] | Minor | Test planning view with status tracking and assignment to team members | `tosca-cloud-improvement-requests.md · L63` |

**Insight:** A tester-only blind spot: reporting, requirements traceability, and planning are business-critical for practitioners but invisible in designer dogfooding, which stops at authoring and execution.

---

## Cluster 16: Bulk Operations & Power-user Tools
**Issues:** 5 ([D] 1 · [T] 4) | **Highest severity:** Major

Power users need TQL-style queries, saved searches, consistent CRUD, and bulk management tools not yet in Tosca Cloud. Testers drive this cluster; a single designer search-limitation finding corroborates the query gap.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-037 | [T] | Major | TQL-style bulk query and change capability | `tosca-cloud-improvement-requests.md · L74` |
| TC-038 | [T] | Major | Parameter name highlighting/guided editing to prevent misconfiguration | `tosca-cloud-improvement-requests.md · L75` |
| TC-039 | [T] | Major | Consistent copy/edit/delete/create behaviour across all Tosca Cloud objects | `tosca-cloud-improvement-requests.md · L76` |
| TC-040 | [T] | Major | Saved search queries / virtual folders equivalent to Commander TQL queries (TOSCA-40967) | `tosca-cloud-improvement-requests.md · L77` |
| FG-007 | [D] | Minor | Search returns no results when querying by "Last modified by"; only Name field works | `04-final.md · L38` |

**Insight:** Testers articulate a whole power-user tier (TQL, saved searches, consistent CRUD) that Designers only glimpse via a single broken-search finding — a maturity gap where experienced Commander users outrun the current Cloud feature set.

---

## Cluster 17: Debugging Depth
**Issues:** 4 ([D] 0 · [T] 4) | **Highest severity:** Minor

Advanced debugging features (API payloads, filterable logs, Buffer Viewer, Base64 decode) are missing from the Cloud UI. Entirely tester-sourced, reflecting deep hands-on troubleshooting needs.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-023 | [T] | Minor | API engine debugging: expose sent/received payloads in Cloud UI (TOSCA-36148) | `tosca-cloud-improvement-requests.md · L42` |
| TC-024 | [T] | Minor | Extended and filterable logs by engine type or error type (TOSCA-41499) | `tosca-cloud-improvement-requests.md · L43` |
| TC-025 | [T] | Minor | UI toggle to Base64-decode API message payloads in a run (TOSCA-38511) | `tosca-cloud-improvement-requests.md · L44` |
| TC-004 | [T] | Minor | Buffer Viewer panel to inspect buffer names and values (TOSCA-37225) | `tosca-cloud-improvement-requests.md · L14` |

**Insight:** A purely tester-driven blind spot: debugging depth only matters once you are maintaining real automation, so it never surfaces in designer evaluation but is essential for production adoption.

---

## Cluster 18: Migration Correctness Bugs
**Issues:** 10 ([D] 0 · [T] 10) | **Highest severity:** Major

A class of bugs visible only to teams migrating from Commander: templates uploaded wrong, conditions ignored, CI triggering broken. Entirely tester-sourced from real migration attempts.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-096 | [T] | Major | TC Templates uploaded as plain test cases instead of templates (TOSCA-38764) | `tosca-cloud-improvement-requests.md · L139` |
| TC-097 | [T] | Major | RTSB Library Conditions ignored in Cloud (TOSCA-28935) | `tosca-cloud-improvement-requests.md · L140` |
| TC-098 | [T] | Major | Database Engine tests blocked by upload bug (TOSCA-34864) | `tosca-cloud-improvement-requests.md · L141` |
| TC-099 | [T] | Major | Only a random subset of playlists triggered in nightly CI; API calls time out (TOSCA-32704) | `tosca-cloud-improvement-requests.md · L142` |
| TC-100 | [T] | Major | Inherited TCP migration: only top-level TCPs migrated (TOSCA-28668) | `tosca-cloud-improvement-requests.md · L143` |
| TC-101 | [T] | Minor | Overridden TCPs on test steps cause incorrect upload (TOSCA-35672) | `tosca-cloud-improvement-requests.md · L144` |
| TC-102 | [T] | Minor | Upload fails for tests setting a connection identical to module's reference | `tosca-cloud-improvement-requests.md · L145` |
| TC-103 | [T] | Minor | Verification against Null not working in Cloud | `tosca-cloud-improvement-requests.md · L146` |
| TC-107 | [T] | Minor | Automatic module merge feature missing in Cloud | `tosca-cloud-improvement-requests.md · L153` |
| TC-104 | [T] | Cosmetic | Module with module-attribute referencing another module blocks editing all other attributes (TOSCA-35673) | `tosca-cloud-improvement-requests.md · L147` |

**Insight:** Entirely invisible to designers, these correctness bugs are the true gatekeepers of Commander-to-Cloud migration — a high-stakes tester-only category where a single silent data mismatch can block an entire team's adoption.

---

## Cluster 19: AI-assisted Authoring (Planned H2 2026)
**Issues:** 4 ([D] 0 · [T] 4) | **Highest severity:** Major

Testers request AI-driven test generation, step summarisation, and run-result analysis — all roadmapped for H2 2026. Entirely forward-looking tester feature requests.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-033 | [T] | Major | AI test case generation from Epics/Stories with acceptance criteria | `tosca-cloud-improvement-requests.md · L67` |
| TC-034 | [T] | Major | AI auto-generation of test cases and modules from natural language | `tosca-cloud-improvement-requests.md · L68` |
| TC-035 | [T] | Major | AI summary of test case steps for documentation and reporting | `tosca-cloud-improvement-requests.md · L69` |
| TC-036 | [T] | Major | AI summary of execution run results with corrective action suggestions | `tosca-cloud-improvement-requests.md · L70` |

**Insight:** A coherent, forward-looking tester ask already aligned to the H2 2026 roadmap — notably absent from designer feedback, which focuses on fixing today's flows rather than future capabilities.

---

## Cluster 20: Credentials, Connections & Resource Handling
**Issues:** 2 ([D] 0 · [T] 2) | **Highest severity:** Major

Credential and connection management at test, playlist, and RTSB level is missing, and Connection Manager is not in Cloud. Testers request the reusable connection/credential model and the missing Connection Manager.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-003 | [T] | Major | Credential handling and reusable connection configurations across levels (TOSCA-28668) | `tosca-cloud-improvement-requests.md · L13` |
| TC-108 | [T] | Minor | Connection Manager missing in Cloud (TOSCA-20667) | `tosca-cloud-improvement-requests.md · L154` |

**Insight:** Testers describe a coherent missing capability — reusable connections/credentials plus the Connection Manager itself — whose usability symptom (the designer's "Unknown Connection" dead-end) now lives with the other error-messaging findings in Cluster 5.

---

## Cluster 21: UI Consistency & Visual Polish
**Issues:** 22 ([D] 6 · [T] 16) | **Highest severity:** Major

Inconsistent button styles, icon colours, duplicate titles, right-click behaviour, and creation flows scattered across the product. Both sources catalogue polish issues; Testers contribute the larger volume plus one Major structural one (duplicate titles) and consistency requests for right-click and creation flows.

| ID | Source | Severity | Summary | Raw source |
|---|---|---|---|---|
| TC-073 | [T] | Major | Duplicate page titles waste screen space (e.g., "Inventor / Inventory") (TOSCA-31794) | `tosca-cloud-improvement-requests.md · L113` |
| AMN-009 | [D] | Minor | Buttons inconsistent with the rest of the app | `04-final.md · L103` |
| GT-007 | [D] | Minor | "Create folder" button visually lost among disabled buttons; active vs disabled state indistinct | `04-final.md · L70` |
| GT-008 | [D] | Minor | Test case name editor field visually detached from blue CTA area | `04-final.md · L71` |
| TC-045 | [T] | Minor | Inconsistent right-click link behaviour across nav, connections, playlists | `tosca-cloud-improvement-requests.md · L82` |
| TC-050 | [T] | Minor | Align creation flow for business parameters, CPs, and buffers to consistent UI pattern | `tosca-cloud-improvement-requests.md · L87` |
| TC-075 | [T] | Minor | Toolbar position: consider moving from left to top | `tosca-cloud-improvement-requests.md · L115` |
| TC-076 | [T] | Minor | Left sidebar close control requires scrolling to the bottom (TOSCA-28019) | `tosca-cloud-improvement-requests.md · L116` |
| TC-077 | [T] | Minor | Expanding left toolbar overlays and hides main page content | `tosca-cloud-improvement-requests.md · L117` |
| AMN-011 | [D] | Cosmetic | Checkboxes inconsistent with each other | `04-final.md · L104` |
| JA-026 | [D] | Cosmetic | Delete dialog says "Delete multiple artifacts?" but toast says "Folders deleted" — inconsistent wording | `04-final.md · L62` |
| JA-027 | [D] | Cosmetic | Playlist data grid column order wrong: should be drag handle then checkbox | `04-final.md · L63` |
| TC-079 | [T] | Cosmetic | Update "Home" icon (TOSCA-30522) | `tosca-cloud-improvement-requests.md · L119` |
| TC-081 | [T] | Cosmetic | Workspace buttons have mismatched background colours | `tosca-cloud-improvement-requests.md · L121` |
| TC-082 | [T] | Cosmetic | Inconsistent icon background colours (blue vs grey) across buttons | `tosca-cloud-improvement-requests.md · L122` |
| TC-083 | [T] | Cosmetic | "Create" split-button appears to offer two options but both do the same thing | `tosca-cloud-improvement-requests.md · L123` |
| TC-088 | [T] | Cosmetic | Stop-run icon is grey and hard to notice; should be red | `tosca-cloud-improvement-requests.md · L128` |
| TC-089 | [T] | Cosmetic | Personal/team agent icons should visually distinguish individual vs group | `tosca-cloud-improvement-requests.md · L129` |
| TC-090 | [T] | Cosmetic | Checkbox for selecting a test case on hover is not clearly visible | `tosca-cloud-improvement-requests.md · L130` |
| TC-093 | [T] | Cosmetic | Consider making certain key text bold for readability | `tosca-cloud-improvement-requests.md · L133` |
| TC-094 | [T] | Cosmetic | Launcher download page shows version number inconsistently | `tosca-cloud-improvement-requests.md · L134` |
| TC-095 | [T] | Cosmetic | Test case duplication flow not intuitive | `tosca-cloud-improvement-requests.md · L135` |

**Insight:** The highest-volume cluster: both audiences independently catalogue the same inconsistent buttons, icons, titles, and interaction patterns, and the shared pattern (rather than any single issue) is the real signal — a systematic design-system gap worth a dedicated consistency pass.

---
