# Feedbacks Consolidation

_This file compares two independent sources of Tosca Cloud feedback and surfaces where they agree, where they diverge, and what each raises alone. **Source 1 — Designers:** 6 UX designers who did hands-on dogfooding and produced structured issue reports (severity, fix hypotheses, team-effort tags), documenting UX failures observed during task-based sessions. **Source 2 — Testers:** internal testers and community members who submitted a prioritised improvement wish list (1-Critical through 4-Nice To Have) grouped by product category, plus a set of active migration bugs. The two lenses differ by design: Designers capture first-encounter friction and moment-of-failure UX; Testers capture sustained-use feature gaps, Commander parity, and migration correctness._

---

## 1. Common themes — raised by BOTH Designers and Testers

**Launcher / E2G setup flow is unintuitive and under-explained**

Both groups independently flagged the Launcher (E2G agent) install-and-connect flow as a major point of friction. Designers observed the raw failure modes during onboarding; Testers formalised it as a high-priority setup-flow request.
- Designer evidence:
  - OVL-001 (Major): install prompt with no warning, no system requirements, no explanation before Launcher appears mid-flow (3 designers).
  - OVL-002 (Critical): OS detection silently blocks macOS users — Windows .exe auto-downloads, no Mac Launcher (2 designers).
  - OVL-003 (Major): failure states — antivirus quarantine, raw error codes, silent failure needing full reinstall (4 issues, 2 designers).
  - FG/DL unique: IT-managed antivirus blocks Launcher with no in-product guidance; every rescan re-shows "first time? download launcher" despite being installed.
- Tester evidence:
  - 2-High: Launcher/E2G setup flow unintuitive (TOSCA-41023).
  - 2-High: file/attachment handling for cloud agents; multiple E2G agents simultaneously (TOSCA-37159).
- Convergence note: When the two groups converge on Critical/High for the very first thing a new user must do, it marks the Launcher as the single highest-leverage fix in the product.

---

**No autosave / no session-expiry protection**

Both groups worry about losing work. Designers experienced disruptive save dialogs and data-loss anxiety in the editors; Testers escalated autosave to a High-priority usability request.
- Designer evidence:
  - OVL-006 (Major): no autosave in test case editor or playlist editor; disruptive save dialogs, data-loss anxiety (2 designers).
- Tester evidence:
  - 2-High (Usability): autosave or session-expiry warning.
- Convergence note: Independent framing of the same gap as both a UX failure and an explicit feature request confirms it is real and worth prioritising.

---

**Run/execution feedback and results are hard to reach**

Both groups want clearer signals during and after a run — what happened, what failed, and a direct path to the failing element.
- Designer evidence:
  - OVL-004 (Major): no feedback after clicking Run; cursor change only; duplicate runs from multiple clicks (3 designers).
  - OVL-005 (Major): run results not surfaced — generic "failed" status, 3+ clicks to see which tests failed, no pass/fail summary (3 designers).
  - GT unique: Rescan not discoverable from a failed step.
- Tester evidence:
  - 3-Medium: expand/collapse individual steps during execution; explicit signal for missing module/RTSB reference.
  - 3-Medium: direct nav from run result to failing module/RTSB (TOSCA-34497).
  - 4-NTH: run completion indicator; clarify "Test runs" / "Rerun failed" terminology.
- Convergence note: Designers frame it as missing feedback loops; Testers frame it as navigation and terminology — same underlying execution-visibility gap.

---

**Actionable, cause-based error messages**

Both groups report that errors describe symptoms, not causes, and offer no next step.
- Designer evidence:
  - OVL-008 (Major): errors show symptoms not causes — SQL timeout, Test Connection failure, "couldn't find tab" misdirection (3 issues, 2 designers).
  - FG unique: SQL Editor shows "Unknown Connection".
- Tester evidence:
  - 3-Medium (Usability): actionable error messages; agent characteristic tag error; server error redirect to Default.
- Convergence note: Both groups independently call for errors that state a cause and a remedy rather than a raw code.

---

**Cross-workspace asset sharing and workspace membership**

Both groups hit workspace boundaries as a barrier to reuse.
- Designer evidence:
  - OVL-007 (Major): module save — no workspace selector during scan (2 designers).
  - OVL-012 (Major): workspace post-creation broken — creator not added as member, access denied (3 designers).
- Tester evidence:
  - 1-Critical: asset sharing across workspaces (TOSCA-31764) — the single Critical on the tester list.
- Convergence note: This is the tester side's top-rated request and aligns with designers' workspace-membership breakage — a shared structural pain around workspace scoping.

---

**Module search / discovery is confusing**

Both groups struggle to find modules, and both note search behaviour that does not reset or default sensibly.
- Designer evidence:
  - OVL-015 (Major): search tab confusion — User assets not default, standard modules pollute results.
  - GT unique: module search requires knowing module names.
- Tester evidence:
  - 3-Medium: module search doesn't reset between tabs.
  - 4-NTH: auto-select new module; highlight new module location; module list retention.
- Convergence note: Same defect (search scope/reset) observed as a task blocker by designers and logged as a refinement by testers.

---

**Confirmation feedback after key actions**

Both groups note actions that complete without acknowledgment, and both connect this to save/state ambiguity.
- Designer evidence:
  - OVL-011 (Major): no confirmation feedback after checkbox, download, ARA recording, sheet linking, Run click, playlist save (6 issues, 4 designers — the widest designer overlap).
- Tester evidence:
  - 4-NTH: Save button enabled/disabled state; run completion indicator.
- Convergence note: Designers rate this Major and broad; testers rate individual instances NTH — a severity gap worth reconciling.

---

**Onboarding, homepage and in-context guidance**

Both groups note that new users lack orientation.
- Designer evidence:
  - OVL-010 (Major): missing in-context guidance — DI prerequisites hidden, SQLite path assumption, template flow needs external docs.
  - AMN unique: homepage misleading for new users; Create "+" menu overwhelming.
- Tester evidence:
  - 4-NTH: tutorial videos; homepage IA reconsider; Create split-button confusion.
- Convergence note: Designers rate onboarding Major (it blocks first tasks); testers rate it NTH (they already know the product) — a classic new-vs-experienced-user severity split.

---

## 2. Designer-only findings — not echoed by Testers

**XScan cannot handle complex controls (deep workflow issue)**
- Designers found XScan fails silently on floating menus, dropdowns, tables, drag-and-drop, and grid buttons, and rescan doesn't refresh the view (OVL-009, Critical, 7 issues, 2 designers). AMN adds: no uniqueness warning before scanning; DL: scan performance extremely slow.
- Why it matters: scanning is the foundation of every test; silent failure here poisons everything downstream and cannot be diagnosed by the user.
- Class: deep workflow issue, not onboarding — it recurs throughout sustained use. (Testers mention scan-button placement and click-count, but not scan *capability*.)

---

**Template instantiation and terminology broken (deep workflow issue)**
- OVL-013 (Major): reports success but produces nothing; Instantiate button disappears; Save and Instantiate are separate gated steps. OVL-014 (Major): "Test Sheets" means both source data and generated instances; no link preview. JA unique: "Create template" only discoverable in individual test case view; template editor looks identical to test case editor; XL syntax not in-product; special characters break instantiation silently.
- Why it matters: templates are a power feature; silent failure and terminology collision make the whole feature untrustworthy.
- Class: deep workflow issue. (Testers note TC-template *migration* bugs but not the in-product authoring flow.)

---

**Authentication blocks automation (deep workflow issue)**
- GT (Critical): MFA/YubiKey blocks automation; BrowserArguments ignored when running via Cloud agent. JA: personal agent modal contradicts itself; Launcher closes the user's browser during a run.
- Why it matters: these hard-block real enterprise environments and have no workaround surfaced.
- Class: deep workflow/environment issue.

---

**First-encounter / install-class friction (designer-only detail)**

These are designer-specific observations about the very first steps — install, first scan, first menu encounter. They supplement the §1 Onboarding convergence but were not reported by testers (who are already fluent).
- Launcher install with no warning or requirements (OVL-001); macOS silently blocked (OVL-002); homepage misleading (AMN); Create "+" menu overwhelming (AMN); CSV filename must omit extension with no UI hint (FG); DI executor folder not auto-created (FG).
- Why it matters: these determine whether a new user ever reaches a first successful task.
- Class: first-encounter/onboarding.

---

**Editor interaction parity and back navigation**
- No undo/redo in module editor (DL); playlist add is drag-only while test builder uses "+" (DL); partial playlist selection still runs all tests (DL); no back navigation from module page or test case editor (OVL-017, Minor).
- Why it matters: small, repeated friction that erodes trust and speed.
- Class: deep workflow issue — these recur on every authoring session.

---

## 3. Tester-only requests — not reflected in Designer feedback

**Migration correctness — active bugs**
- TC Templates uploaded as plain test cases (TOSCA-38764, High); RTSB Library Conditions ignored (TOSCA-28935, High); Database Engine tests blocked (TOSCA-34864, High); nightly CI playlist subset issue (TOSCA-32704, High); inherited TCP migration gap (TOSCA-28668, High); overridden TCPs on upload (TOSCA-35672, Medium); connection reference upload failure (Medium); Null verification broken (Medium); module-attribute chain blocks editing (TOSCA-35673, NTH).
- Type: bugs (migration correctness). Designers never migrated existing Commander assets, so this whole class is invisible to them.
- Priority: mostly 2-High.

---

**Commander parity in authoring**
- Copy-paste of blocks including keyboard shortcuts (TOSCA-37666, High); default module values auto-populate (TOSCA-32789, High); hide "do nothing" steps (TOSCA-9589, High); DnD across windows (TOSCA-35021, Medium); ValueRange for RTSB (TOSCA-36832, Medium); full keyboard shortcuts (High).
- Type: missing parity with Commander — testers have a mental model designers lack.
- Priority: 2-High and 3-Medium.

---

**Reporting, dashboards and requirements**
- Custom reports with aggregation (High); cross-workspace dashboards (High); requirements + execution logs as report view (High); requirements linked to test cases with reporting (Medium); test planning view with status and assignment (Medium); precondition description field with links (Medium).
- Type: missing features for test management at scale.
- Priority: 2-High / 3-Medium.

---

**AI-assisted authoring (Planned H2 2026)**
- Test case generation from Epics/Stories; auto-generation from natural language; summary of test steps; summary of run results.
- Type: missing (roadmapped) features.
- Priority: 2-High.

---

**Power-user usability and bulk operations**
- TQL-style bulk query (High); saved search queries / virtual folders (TOSCA-40967, High); parameter name highlighting (High); consistent CRUD behaviour across objects (High); Delete only deletes one in multi-select (Medium); visibility of which test cases are in which playlists (High); add test case to multiple playlists (TOSCA-36736, Medium); folder support in Playlist tree (Medium).
- Type: missing features / consistency gaps surfaced only through sustained use.
- Priority: 2-High / 3-Medium.

---

**Debugging depth**
- API engine payload visibility (TOSCA-36148, Medium); filterable logs (TOSCA-41499, Medium); Base64 decode toggle (TOSCA-38511, Medium); Buffer Viewer panel (Medium).
- Type: missing features for deep debugging.
- Priority: 3-Medium.

---

**Module management and search (tester-only depth)**
- Automatic module merge missing (Medium); module list retention across sessions; auto-select and highlight newly created module.
- Type: module-management parity and convenience gaps visible only through sustained use.
- Priority: 3-Medium / 4-NTH.

---

**UI polish, toolbar layout and visual consistency**
- Toolbar position left→top; toolbar overlay; left sidebar close control hard to reach; remove duplicate page titles (TOSCA-31794, High); show asset folder path in Builder (High); many NTH cosmetics (home icon, button colours, bold text, version-number consistency, breadcrumb asset type).
- Type: mix of structural usability gaps and cosmetic polish.
- Priority: from 2-High down to 4-NTH.

---

**Credentials, connections and resource handling**
- Credential handling and reusable connections (TOSCA-28668, High); Connection Manager missing (TOSCA-20667, Medium); lock mechanism for parameters (NTH); Delete button in Builder view (NTH).
- Type: missing features / parity.
- Priority: 2-High to 4-NTH.

---

## 4. Summary comparison table

| Theme | Designers | Testers | Overlap? | Priority signal |
|---|---|---|---|---|
| Launcher / E2G setup flow | OVL-001/002/003, FG, DL | TOSCA-41023, TOSCA-37159 | Yes | Critical |
| Cross-workspace asset sharing & membership | OVL-007, OVL-012 | TOSCA-31764 (1-Critical) | Yes | Critical |
| Autosave / session-expiry | OVL-006 | Autosave request | Yes | High |
| Run/execution feedback & results | OVL-004, OVL-005 | TOSCA-34497, step expand | Yes | Major/High |
| Actionable error messages | OVL-008, FG | Usability errors | Yes | Major/Medium |
| Module search / discovery | OVL-015, GT | search reset, auto-select | Yes | Major/Medium |
| Confirmation feedback | OVL-011 (4 designers) | Save state, run indicator | Yes | Major/NTH |
| Onboarding / homepage / guidance | OVL-010, AMN | tutorials, homepage IA | Yes | Major/NTH |
| XScan complex-control scanning | OVL-009 (Critical) | — | No | Critical |
| Template instantiation & terms | OVL-013, OVL-014, JA | — (migration only) | No | Major |
| Auth blocks automation (MFA) | GT (Critical) | — | No | Critical |
| Editor interaction parity & back nav | DL, OVL-017 | Delete-one, keyboard | Partial | Major/Minor |
| Migration correctness bugs | — | TOSCA-38764/28935/34864 | No | High |
| Commander authoring parity | — (DL playlist add) | TOSCA-37666/32789/9589 | Partial | High |
| Reporting / dashboards (incl. cross-ws) | — | Custom reports, dashboards | No | High |
| Requirements & test planning | — | linked reqs, planning view | No | Medium |
| AI-assisted authoring | — | Epics→TC, NL generation | No | High (Planned) |
| Bulk query / saved searches | — | TQL, TOSCA-40967 | No | High |
| Debugging depth (logs, payloads) | — | TOSCA-36148/41499/38511 | No | Medium |
| Module management (tester depth) | — | module merge, retention | No | Medium/NTH |
| Credentials / connections | FG (Unknown Connection) | TOSCA-28668, TOSCA-20667 | Partial | High |
| UI polish / toolbar / titles | AMN (Create menu) | TOSCA-31794, toolbar pos | Partial | High/NTH |

---

## 5. Key divergences

- **First-encounter failures vs. sustained-use gaps.** Designers concentrate on the moment of first contact — install, scan, first run, first template — where silent failures block any progress at all. Testers, already fluent, concentrate on what slows them down over weeks: bulk operations, reporting, parity with Commander. The two groups are looking at opposite ends of the same user journey, which is why designer "Major" onboarding items map to tester "NTH".

- **Migration is entirely a tester concern.** The whole "Test Migration" bug and feature set (templates uploaded as plain test cases, RTSB conditions ignored, DB engine blocked, TCP gaps) is invisible to designers because they built assets fresh rather than importing existing Commander projects. This is the largest single body of feedback with no designer counterpart, and it is correctness (bugs), not preference.

- **Capability failure vs. workflow feature requests.** Designers report that core engines silently fail (XScan can't read complex controls, templates instantiate to nothing, MFA blocks automation) — trust-destroying defects. Testers rarely mention these; instead they assume the engines work and ask for management-layer features (dashboards, requirements, planning, AI). One group questions whether the foundation holds; the other is already building on top of it.

- **Severity framing is structurally different.** Designers assign UX severity from observed task failure (does the user get stuck?). Testers assign business priority from a wish-list perspective (how much would this help?). The same issue — e.g. confirmation feedback or onboarding — lands as Major for designers and NTH for testers, so raw priority labels are not directly comparable across sources without this translation.

- **Where they do converge, it is unusually strong signal.** The overlaps (Launcher, cross-workspace sharing, autosave, run visibility, error messages, module search) are the items surfaced independently through two very different methodologies. Cross-workspace asset sharing is the clearest example: designers' top workspace-breakage cluster and testers' single Critical request are the same underlying scoping problem — making it the most defensible top priority in the combined dataset.
