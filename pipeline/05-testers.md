## Overview

This PR documents 108 improvement requests collected from Tosca Cloud users via the Testing Community. The requests cover usability gaps, missing features, active migration bugs, and UX proposals surfaced during internal dogfooding and customer feedback sessions. This document serves as a consolidated reference for PM triage, prioritisation, and roadmap planning.

---

## Summary by Category

### Resource Handling

- **1-Critical** — Asset sharing of reusables or modules across workspaces. ([TOSCA-31764](https://tricentis.atlassian.net/browse/TOSCA-31764))
- **2-High** — File and attachment handling: attach test data files to modules or test cases for cloud agent access without requiring external file shares. *(PM Review needed)*
- **2-High** — Credential handling and reusable connection configurations across test case, playlist, and RTSB levels. ([TOSCA-28668](https://tricentis.atlassian.net/browse/TOSCA-28668))
- **3-Medium** — Buffer Viewer panel to inspect existing buffer names and values in the Tosca Cloud UI. ([TOSCA-37225](https://tricentis.atlassian.net/browse/TOSCA-37225))
- **3-Medium** — Add a button for scanning modules from inventory. ([TOSCA-31481](https://tricentis.atlassian.net/browse/TOSCA-31481))
- **4-Nice To Have** — Lock mechanism for parameters and their values to prevent unintended changes.
- **4-Nice To Have** — Add a Delete button for modules, test cases, and RTSBs when inside the Builder view.

### Testcase creation

- **2-High** — Test creation feels slow: copy-paste is missing, drag-and-drop differs from Commander, and copying technical properties across modules is cumbersome. ([TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666))
- **2-High** — Copy-pasting of test steps, values, or whole structures between test cases. ([TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666))
- **2-High** — Default module values should auto-populate test step values on instantiation. ([TOSCA-32789](https://tricentis.atlassian.net/browse/TOSCA-32789))
- **2-High** — Ability to hide "do nothing" steps and show only populated test step values, as in Commander. ([TOSCA-9589](https://tricentis.atlassian.net/browse/TOSCA-9589))
- **3-Medium** — Drag-and-drop UX: modules and RTSBs cannot be dragged across different windows into test cases. ([TOSCA-35021](https://tricentis.atlassian.net/browse/TOSCA-35021)) *(UX Review needed)*
- **3-Medium** — Double-click to expand test steps, modules, and other items instead of relying solely on the expand arrow. *(UX Review needed)*
- **3-Medium** — Module search in test case creation does not reset when switching between standard objects and user assets.
- **3-Medium** — Review workflow for test changes with comments, similar to GitHub pull requests.
- **3-Medium** — Action mode and data type dropdowns need better contrast highlighting and value autocomplete when typing.
- **3-Medium** — Add ValueRange support for RTSB parameters and allow migration of ValueRange values from on-prem. ([TOSCA-36832](https://tricentis.atlassian.net/browse/TOSCA-36832))
- **4-Nice To Have** — Color coding for populated vs. unpopulated test step values in the SpecialExecutionTask builder, mirroring Tosca Commander icons.

### Test Tasks assignments

- **2-High** — Copy and pasting of blocks during test creation, including keyboard shortcuts. ([TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666))
- **3-Medium** — Proper assignment of test tasks with parameterised reusable blocks and resources.

### Execution and debugging

- **2-High** — E2G/Launcher setup flow is unintuitive: components should be installable and the agent startable from a button after launcher install, without triggering a dummy test run. ([TOSCA-41023](https://tricentis.atlassian.net/browse/TOSCA-41023))
- **3-Medium** — Ability to expand and collapse individual test steps during execution, not only the entire test case.
- **3-Medium** — Improved API engine debugging: expose sent/received payloads in the Cloud UI as the Commander feature flag does. ([TOSCA-36148](https://tricentis.atlassian.net/browse/TOSCA-36148))
- **3-Medium** — Extended and filterable logs by engine type or error type. ([TOSCA-41499](https://tricentis.atlassian.net/browse/TOSCA-41499))
- **3-Medium** — UI toggle to Base64-decode API message payloads in a test run. ([TOSCA-38511](https://tricentis.atlassian.net/browse/TOSCA-38511))
- **3-Medium** — Explicit execution signal when a module or RTSB reference is missing.

### Reporting/Dashboards

- **2-High** — Custom reports with aggregation of pass/fail/not-executed counts, filterable by workspace or specific items, with reusable templates.
- **2-High** — Cross-workspace custom dashboards that combine data from multiple workspaces into a single engineering-style report.
- **2-High** — Requirements and execution logs exposed as a report view.

### Requirements

- **3-Medium** — Requirements linked to test cases, with reporting capability for daily business use.

### Test cases design

- **3-Medium** — Precondition description field (text only) on test cases, with clickable links to related test cases.

### Test Planning

- **3-Medium** — Test planning view with status tracking and assignment to team members.

### AI

- **2-High** — AI-driven test case generation from product Epics/Stories with acceptance criteria. *(Planned H2 2026)*
- **2-High** — AI auto-generation of test cases and modules from a natural language description of steps and values. *(Planned H2 2026)*
- **2-High** — AI summary of test case steps for documentation and reporting purposes. *(Planned H2 2026)*
- **2-High** — AI summary of execution run results, identifying problems and suggesting corrective actions. *(Planned H2 2026)*

### Usability

- **2-High** — TQL-style bulk query and change capability for steps, values, test cases, and items; reference search for CPs, buffers, and PLs.
- **2-High** — Parameter name highlighting/guided editing to indicate correctness and avoid misconfiguration.
- **2-High** — Consistent copy/edit/delete/create behaviour (including right-click menus) across all Tosca Cloud objects.
- **2-High** — Saved search queries / virtual folder concept equivalent to Tosca Commander's saved TQL queries. ([TOSCA-40967](https://tricentis.atlassian.net/browse/TOSCA-40967))
- **2-High** — Full keyboard shortcut support across the product workflow.
- **2-High** — Autosave mode or session-expiry warning to prevent data loss.
- **2-High** — Visibility of which test cases are used in which playlists to track usage at scale.
- **3-Medium** — Configurable mail notification settings per feature or service. ([TOSCA-519](https://tricentis.atlassian.net/browse/TOSCA-519), [TOSCA-41509](https://tricentis.atlassian.net/browse/TOSCA-41509))
- **3-Medium** — Inconsistent right-click link behaviour across navigation bar, connections, and playlists should be unified.
- **3-Medium** — Reduce number of newly opened browser tabs; use pop-up or dockable panels instead.
- **3-Medium** — Context menu Delete only deletes one item when multiple test steps are selected; fix or remove the option.
- **3-Medium** — Inventory access path via "Build" navigation is unintuitive. *(UX Review needed)*
- **3-Medium** — On server error (e.g. 502), restore user to last-used workspace instead of redirecting to Default.
- **3-Medium** — Align creation flow for business parameters, CPs, and buffers to a consistent UI pattern.
- **3-Medium** — Test Runs and Playlist Run History pages should be aligned or consolidated. *(UX Review needed)*
- **3-Medium** — Standard object options and Action modes lack hover/tooltip explanations; add (?) help links.
- **3-Medium** — Add folder support in the Playlist tree to match the Test Cases tree. *(UX Review needed)*
- **3-Medium** — Improve window/tab titles to clearly describe the open component.
- **3-Medium** — Direct navigation from a test run result to the specific failing module or RTSB. ([TOSCA-34497](https://tricentis.atlassian.net/browse/TOSCA-34497))
- **3-Medium** — Add agent characteristics tutorial video. *(UX Review needed)*
- **3-Medium** — Show error/warning when user types an agent characteristic tag but does not press Enter to create it. *(UX Review needed)*
- **3-Medium** — Error messages must include actionable next steps so users can diagnose the root cause. *(UX Review needed)*
- **3-Medium** — Tree-to-panel relationship (selection and detail display) is confusing for users. *(UX Review needed)*
- **3-Medium** — Add a test case to multiple playlists at once. ([TOSCA-36736](https://tricentis.atlassian.net/browse/TOSCA-36736))
- **4-Nice To Have** — Add short tutorial videos or links to documentation for complex first-time scenarios such as business parameters.
- **4-Nice To Have** — Allow contributors to delete tests; introduce three user roles: read-only, read-write, and admin. ([TOSCA-36335](https://tricentis.atlassian.net/browse/TOSCA-36335))
- **4-Nice To Have** — Auto-select or auto-add a newly created module to the current test case.
- **4-Nice To Have** — Clarify "Test runs" and "Rerun failed test" terminology, as both actually operate on playlists.
- **4-Nice To Have** — Update the API tutorial video, which shows an outdated Tosca Cloud UI.
- **4-Nice To Have** — Visual indicator (alert icon or reduced opacity) for unused test case parameters.
- **4-Nice To Have** — Sort test case parameters alphabetically rather than by creation order.
- **4-Nice To Have** — Add asset type description to Builder breadcrumb header. *(UX Review needed)*
- **4-Nice To Have** — When viewing a specific module, retain or show access to the full module list on the left.
- **4-Nice To Have** — Highlight or reveal location of a newly created module in the module tree after saving.
- **4-Nice To Have** — Show all module/RTSB references before allowing deletion.
- **None assigned** — Minimise window openings and clicks by enabling in-page navigation.

### UX Proposals

- **2-High** — Remove duplicate page titles that waste screen space (e.g., "Inventor / Inventory"). ([TOSCA-31794](https://tricentis.atlassian.net/browse/TOSCA-31794))
- **2-High** — Show asset folder path in the Builder so users can see where the current module/RTSB is located in inventory.
- **3-Medium** — Consider moving the toolbar from the left side of the screen to the top. *(UX Review needed)*
- **3-Medium** — Left sidebar requires scrolling to the bottom to find the close control when fully expanded. ([TOSCA-28019](https://tricentis.atlassian.net/browse/TOSCA-28019), [UXDESIGN-2458](https://tricentis.atlassian.net/browse/UXDESIGN-2458)) *(UX Review needed)*
- **3-Medium** — Expanding the left toolbar overlays and hides the main page content. ([TOSCA-28019](https://tricentis.atlassian.net/browse/TOSCA-28019), [UXDESIGN-2458](https://tricentis.atlassian.net/browse/UXDESIGN-2458)) *(UX Review needed)*
- **3-Medium** — Builder section pages lack clear page titles; users must rely on icons to identify their location.
- **4-Nice To Have** — Update the "Home" icon. ([TOSCA-30522](https://tricentis.atlassian.net/browse/TOSCA-30522)) *(UX Review needed)*
- **4-Nice To Have** — Reconsider home page content and information architecture; tutorials feel out of place. *(UX Review needed)*
- **4-Nice To Have** — "Request for upgrade" and "Default" workspace buttons have mismatched background colours.
- **4-Nice To Have** — Inconsistent icon background colours (blue vs grey) across buttons such as "Re-usable Test Steps" and "+New Folder".
- **4-Nice To Have** — "Create" button split-button appears to offer two options but both perform the same action. *(UX Review needed)*
- **4-Nice To Have** — Reduce click count when scanning a new module from the test case builder (currently 4 steps per scan).
- **4-Nice To Have** — Deletion flow from the tree is not intuitive. *(UX Review needed)*
- **4-Nice To Have** — Run completion indicator (red dot disappearing) is not visually prominent enough; add a notification.
- **4-Nice To Have** — Disable the Save button when there are no pending changes.
- **4-Nice To Have** — Stop-run icon is grey and hard to notice during an active run; change to red. *(UX Review needed)*
- **4-Nice To Have** — Change personal agent icon to a person figure and team agent icon to three people. *(UX Review needed)*
- **4-Nice To Have** — Checkbox for selecting a test case on hover is not clearly visible. *(UX Review needed)*
- **4-Nice To Have** — Add a plus (+) icon for creating a new folder in the Playlist view, consistent with the Test Cases view. *(UX Review needed)*
- **4-Nice To Have** — "Builder" header and "Builder" navigation option coexist and cause confusion.
- **4-Nice To Have** — Consider making certain key text bold for better readability.
- **4-Nice To Have** — Launcher download page shows version number inconsistently across two locations; also surface version inside the Launcher itself.
- **4-Nice To Have** — Make test case duplication flow more intuitive for users.

### Test Migration to Tosca Cloud - Active bugs

- **2-High** — TC Templates are uploaded as simple test cases instead of templates. ([TOSCA-38764](https://tricentis.atlassian.net/browse/TOSCA-38764))
- **2-High** — RTSB Library Conditions are ignored in the Cloud; logic is not executed. ([TOSCA-28935](https://tricentis.atlassian.net/browse/TOSCA-28935))
- **2-High** — Database Engine tests (101 tests) blocked by upload bug with broken referenced modules. ([TOSCA-34864](https://tricentis.atlassian.net/browse/TOSCA-34864))
- **2-High** — Only a random subset of playlists is triggered during nightly CI; API calls time out for others. ([TOSCA-32704](https://tricentis.atlassian.net/browse/TOSCA-32704))
- **2-High** — Inherited configuration TCPs: only top-level TCPs are migrated when configurations are assigned to TC or EL. ([TOSCA-28668](https://tricentis.atlassian.net/browse/TOSCA-28668))
- **3-Medium** — Overridden TCPs on test steps cause incorrect upload from Commander. ([TOSCA-35672](https://tricentis.atlassian.net/browse/TOSCA-35672))
- **3-Medium** — Upload fails for tests that explicitly set a connection identical to the one already referenced by the module. ([TOSCA-35672](https://tricentis.atlassian.net/browse/TOSCA-35672))
- **3-Medium** — Verification against Null is not working in the Cloud.
- **4-Nice To Have** — Module with a module-attribute referencing another module blocks editing of all other attributes in that module. ([TOSCA-35673](https://tricentis.atlassian.net/browse/TOSCA-35673))

### Test Migration to Tosca Cloud - Feature requests

- **2-High** — No asset sharing across workspaces yet. ([TOSCA-31764](https://tricentis.atlassian.net/browse/TOSCA-31764))
- **2-High** — Need to run multiple E2G agents from the Launcher simultaneously (team and personal). ([TOSCA-37159](https://tricentis.atlassian.net/browse/TOSCA-37159))
- **3-Medium** — Automatic module merge feature is missing in the Cloud.
- **3-Medium** — Connection Manager is missing in the Cloud. ([TOSCA-20667](https://tricentis.atlassian.net/browse/TOSCA-20667))

---

## Priority Breakdown

| Priority | Count |
|---|---|
| 1-Critical | 1 |
| 2-High | 38 |
| 3-Medium | 44 |
| 4-Nice To Have | 24 |
| Not assigned | 1 |
| **Total** | **108** |

---

## Items Needing PM Review

| Category | Priority | Description | Review Type |
|---|---|---|---|
| Resource Handling | 2-High | File and attachment handling for cloud agents | PM Review needed |
| Testcase creation | 3-Medium | Drag-and-drop UX across different windows | UX Review needed |
| Testcase creation | 3-Medium | Double-click to expand test steps and modules | UX Review needed |
| Usability | 3-Medium | Inventory access path via "Build" is unintuitive | UX Review needed |
| Usability | 3-Medium | Test Runs and Playlist Run History pages should be aligned or consolidated | UX Review needed |
| Usability | 3-Medium | Folder support in Playlist tree | UX Review needed |
| Usability | 3-Medium | Add agent characteristics tutorial video | UX Review needed |
| Usability | 3-Medium | Show error when agent characteristic tag is typed but not confirmed with Enter | UX Review needed |
| Usability | 3-Medium | Error messages must include actionable next steps | UX Review needed |
| Usability | 3-Medium | Tree-to-panel relationship is confusing | UX Review needed |
| Usability | 4-Nice To Have | Add asset type description to Builder breadcrumb header | UX Review needed |
| UX Proposals | 4-Nice To Have | Update the "Home" icon | UX Review needed |
| UX Proposals | 4-Nice To Have | Reconsider home page content and IA | UX Review needed |
| UX Proposals | 3-Medium | Consider moving toolbar from left side to top | UX Review needed |
| UX Proposals | 3-Medium | Left sidebar requires scrolling to bottom to close when fully expanded | UX Review needed |
| UX Proposals | 3-Medium | Expanding left toolbar hides main page content | UX Review needed |
| UX Proposals | 4-Nice To Have | "Create" button split-button appears to offer two options but both do the same thing | UX Review needed |
| UX Proposals | 4-Nice To Have | Deletion flow from the tree is not intuitive | UX Review needed |
| UX Proposals | 4-Nice To Have | Stop-run icon not visually prominent during an active run | UX Review needed |
| UX Proposals | 4-Nice To Have | Personal agent icon should be a person; team agent icon should be three people | UX Review needed |
| UX Proposals | 4-Nice To Have | Checkbox for selecting a test case on hover is not clearly visible | UX Review needed |
| UX Proposals | 4-Nice To Have | Add plus (+) icon for new folder in Playlist view | UX Review needed |

---

## Key Themes

- **Missing Commander parity** — A large share of requests ask for features that already exist in Tosca Commander (copy-paste, drag-and-drop, buffer viewer, "do nothing" step hiding, TQL queries, virtual folders, module scanning shortcuts) and have not yet been brought to the Cloud, causing friction for users migrating from the desktop client.
- **Inconsistent UI patterns** — Users repeatedly encounter inconsistencies across the product: right-click menus, creation flows for different asset types, tab/window behaviour, icon styles, and button states all behave differently depending on which page the user is on, driving confusion and extra clicks.
- **Weak debugging and observability** — Insufficient log detail, no payload visibility for API engine tests, no explicit signal when a referenced module or RTSB is missing, and unclear error messages make it difficult for users to diagnose test failures without resorting to workarounds.
- **Reporting and cross-workspace visibility** — Dashboards currently provide little actionable value; users need custom, filterable, template-based reports that can aggregate results across workspaces and surface requirement coverage, a gap that is blocking daily business reporting.
- **Migration blockers** — Several active bugs (TC Templates uploaded as plain test cases, RTSB Library Conditions ignored, inherited TCP migration gaps, nightly CI API timeouts) are preventing teams from completing their migration from Tosca Commander to Tosca Cloud, and the absence of asset sharing and a connection manager compounds the problem.
