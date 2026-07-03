# Tosca Cloud Improvement Requests — Consolidation Report
Date: 03.07.2026 | Source: Testing Community Confluence Database | Total requests: 108

---

## Executive Summary

108 improvement requests were collected from the Tosca Cloud internal testing community, submitted primarily by Michael Januschek, Shir Cohen, Filip Seles, Elvin Senoymak, and a further eight contributors. The dominant themes are **Visual/Icons/Layout** (19 requests), **Migration/Upload Correctness** (13 requests), and **Parameter/Value Editing** (9 requests), together accounting for 38% of all feedback. The severity distribution skews mid-range: 42 requests at severity 3, 31 at severity 4, and only 3 at severity 5 — but the three sev-5 items (asset sharing across workspaces, database upload bug) are marked Critical and have confirmed near-duplicates. The corpus is overwhelmingly non-technical (91 feature requests and UX improvements versus 17 technical/bug reports), indicating that the community's greatest friction is with missing functionality and interaction design gaps rather than outright defects.

---

## Requests by Theme

> Ordering: sections ranked by (max severity in area × total request count), descending. Within each section, rows are ordered by severity descending then priority descending.
> Priority badges: 🔴 Critical | 🟠 High | 🟡 Medium | 🟢 Nice-to-have | ⚪ Unset

---

### Asset/Resource Sharing — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🔴 Critical | Assets sharing of reusables or modules across workspaces | Assets sharing of reusables or modules across workspaces. | Michael Januschek | Anna Swietek | [TOSCA-31764](https://tricentis.atlassian.net/browse/TOSCA-31764) | — | 5 | 2 |

⚠️ Near-duplicate of row 29 (No asset sharing yet) — consider merging.

---

### Copy/Paste & Duplicate — 4 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Creation of Tests still feels slow; copy paste missing, drag and drop lacking | Copy paste missing, not easy to drag and drop like in Commander. Copy of Technical properties to other modules, drag and drop module attributes. | Michael Januschek | Neven Kristijan | [TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666) | — | 4 | 4 |
| 🟠 High | Copy pasting stuff from one step to another or for values or whole test steps or structures | Copy pasting stuff from one step to another or for values or whole test steps or structures. | Michael Januschek | Neven Kristijan | [TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666) | — | 4 | 4 |
| 🟠 High | Copy and pasting of blocks, through a test creation (also using keyboard shortcuts) | Copy and pasting of blocks, through a test creation (also using keyboard shortcuts). | Elvin Senoymak | Neven Kristijan | [TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666) | — | 4 | 4 |
| 🟠 High | Copy/edit/delete/create behavior should be everywhere the same | Copy/edit/delete/create behavior should be everywhere the same, pls add missing functionality to all items in the cloud like we have in tosca so you can any time right click and copy or duplicate or delete. | Michael Januschek | Kevin Horvath | — | — | 4 | 4 |

⚠️ All four rows are near-duplicates of the same copy/paste parity ask (rows 4, 5, 8, 15) — consider merging into a single ticket.

---

### Migration/Upload Correctness — 13 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Database Engine Tests (101 Tests) blocked by upload bug | Database Engine Tests (101 Tests) are currently blocked by upload bug, Builder team are aware of broken referenced module in test. | Michael Januschek | Neven Kristijan | [TOSCA-34864](https://tricentis.atlassian.net/browse/TOSCA-34864) | Done | 5 | 1 |
| 🟠 High | No asset sharing yet | No asset sharing yet. | Filip Seles, Daniel Hammerschmidt | Anna Swietek | [TOSCA-31764](https://tricentis.atlassian.net/browse/TOSCA-31764) | — | 5 | 2 |
| 🟠 High | TC Templates are uploaded as simple TestCases | TC Templates are uploaded as simple TestCases. | Gabriel Grabka | Ondřej Zoubek | [TOSCA-38764](https://tricentis.atlassian.net/browse/TOSCA-38764) | Approved | 4 | 1 |
| 🟠 High | Tosca RTSB Library Conditions not working in Cloud | Tosca RTSB Library Conditions not working in Cloud, logic is just ignored. | Gabriel Grabka | Neven Kristijan | [TOSCA-28935](https://tricentis.atlassian.net/browse/TOSCA-28935) | Approved | 4 | 1 |
| 🟠 High | Only a few random playlists triggered during nightly CI run | Only a few random playlists get triggered during the nightly CI run, for the others API call times out. | Yuliya Razhkova | Mario Steiner | [TOSCA-32704](https://tricentis.atlassian.net/browse/TOSCA-32704) | Approved | 4 | 1 |
| 🟠 High | Inherited configurations — only top level TCPs migrated | In case of inherited configurations (assigned to TC or EL) the only top level TCPs have been migrated. | Andrei Korzun | Mario Steiner | [TOSCA-28668](https://tricentis.atlassian.net/browse/TOSCA-28668) | Approved | 4 | 3 |
| 🟠 High | Run multiple E2G Agents from Launcher | We need to be able to run multiple E2G Agents from Launcher (Team and personal alike). | Daniel Hammerschmidt | Edouard De Lansalut | [TOSCA-37159](https://tricentis.atlassian.net/browse/TOSCA-37159) | — | 4 | 2 |
| 🟡 Medium | Upload to Tosca Cloud fails for tests with explicit duplicate connection | Upload to Tosca Cloud fails for specific tests which explicitly sets a connection that is identical to the one already referenced by the module. | Ashok Kumar Sundaram | Neven Kristijan | [TOSCA-35672](https://tricentis.atlassian.net/browse/TOSCA-35672) | — | 4 | 1 |
| 🟡 Medium | Verification against Null not working | Verification against Null not working. | Gabriel Grabka | Neven Kristijan | — | — | 4 | 1 |
| 🟡 Medium | Migration of Commercialization tests blocked by overridden TCPs on TestSteps | There is an issue with migration Commercialization tests to cloud as overridden TCP's on TestSteps leads to testcases not being uploaded correctly from commander. | Olena Teslja | Ondřej Zoubek | [TOSCA-35672](https://tricentis.atlassian.net/browse/TOSCA-35672) | Approved | 3 | 1 |
| 🟡 Medium | Missing automatic module merge feature | We are missing automatic module merge feature. | Filip Seles | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Missing connection manager in cloud | We are missing the connection manager in cloud. | Daniel Hammerschmidt | Christopher Colosimo | [TOSCA-20667](https://tricentis.atlassian.net/browse/TOSCA-20667) | — | 3 | 3 |
| 🟢 Nice-to-have | Module with cross-referencing attribute cannot be edited | We can't edit a module where one module attribute is referencing another module. But all other module attributes that are not referencing a module should still be editable. | Daniel Hammerschmidt | Neven Kristijan | [TOSCA-35673](https://tricentis.atlassian.net/browse/TOSCA-35673) | — | 2 | 1 |

⚠️ Row 29 (No asset sharing yet) is a near-duplicate of row 1 — consider merging.
⚠️ Row 30 (Run multiple E2G Agents) is a near-duplicate of row 9 — consider merging.
⚠️ Row 28 and row 72 (connection manager / credentials) cluster with row 3 in the Credentials & Connections duplicate group.

---

### Credentials & Connections — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Credential handling and configurations/environments | Credential handling and configurations/environments. Customer would love to create connections which are often used and reuse them on testcase, playlist or reusable test step block level. | Michael Januschek | Mario Steiner | [TOSCA-28668](https://tricentis.atlassian.net/browse/TOSCA-28668) | Approved | 4 | 3 |

⚠️ Near-duplicate of rows 28 (inherited TCP configurations) and 72 (missing connection manager) — consider merging.

---

### Visual/Icons/Layout — 19 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Unnecessary duplicate top titles wasting page space | There are unnecessary duplicate top titles, which take up a significant amount of page space for no benefit (for example: 'Inventor', 'Inventory'). | Shir Cohen | Kevin Horvath | [TOSCA-31794](https://tricentis.atlassian.net/browse/TOSCA-31794) | — | 4 | 1 |
| 🟡 Medium | Double click UX experience: expand test steps, modules with double click | Double click UX experience: we would like to use double click to expand the test steps, modules, etc. | Elvin Senoymak | Neven Kristijan Mario Steiner | — | — | 3 | 1 |
| 🟡 Medium | Dropdown highlighting in builder is extremely low contrast | Test case builder - Action mode / Data type dropdowns: highlighting in the dropdown of the matching element is currently extremely light and not contrast. | Yuliya Razhkova | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | There is no information for each standard object option | There is no information for each standard object option. Recommended to add a link or a mouse-hover explanation for every option. | Shir Cohen | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Consider moving the toolbar from the left side to the top | Consider moving the toolbar from the left side of the screen to the top. | Shir Cohen | Kevin Horvath | — | — | 3 | 1 |
| 🟡 Medium | Left side bar requires scroll to bottom to close | Left side bar - You have to scroll all the way to the bottom of the menu in order to close it when you expand the whole menu. | Shir Cohen | Martin Filip, Peter Muka | [TOSCA-28019](https://tricentis.atlassian.net/browse/TOSCA-28019) | — | 3 | 1 |
| 🟡 Medium | Expanding the left toolbar hides main page details | Expanding the left toolbar will hide the main page details. | Shir Cohen | Martin Filip, Peter Muka | [TOSCA-28019](https://tricentis.atlassian.net/browse/TOSCA-28019) | — | 3 | 1 |
| 🟡 Medium | No page title shown when navigating to Re-usable Tests or Tests | When navigating to Re-usable Tests or Tests, there is no title that shows the current location. Most pages under Builder section lack a clear title. | Shir Cohen | Neven Kristijan | — | — | 3 | 1 |
| 🟢 Nice-to-have | Test case builder color coding missing for populated step values | Test case builder steps based on a SpecialExecutionTask — color coding is missing for currently populated test step values. | Yuliya Razhkova | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Add Asset type description to Builder breadcrumbs header | Add Asset type description to the Builder breadcrumbs header upon editing an asset. | Ran Ferdinaro | Anna Swietek | — | — | 2 | 1 |
| 🟢 Nice-to-have | Update the "Home" icon | Update the "Home" icon. | Shir Cohen | Martin Filip | [TOSCA-30522](https://tricentis.atlassian.net/browse/TOSCA-30522) | — | 2 | 1 |
| 🟢 Nice-to-have | Redefine home page content — currently not intuitive | Consider redefining the home page content, as it is currently not very intuitive what will you find there. | Shir Cohen | Martin Filip, Peter Muka | — | — | 2 | 1 |
| 🟢 Nice-to-have | Mismatched background colors on "Request for upgrade" and "Default" buttons | "Request for upgrade" and "Default" workspace buttons are not at the same background colors. | Shir Cohen | Martin Filip | — | Rejected | 2 | 1 |
| 🟢 Nice-to-have | Inconsistent icon background colors (blue and grey) on toolbar | Some icons use inconsistent background colors (blue and grey), such as the 'Re-usable Test Steps' and '+New Folder' buttons. | Shir Cohen | Anna Swietek | — | — | 2 | 1 |
| 🟢 Nice-to-have | Red run indicator disappears without prominent notification on completion | When running a test locally, the red indicator disappears once the run is completed. This isn't visually prominent enough. | Shir Cohen | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Save button should be disabled when there is nothing to save | The 'Save' button should be disabled when there is nothing to save. | Shir Cohen | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Stop run icon not intuitive / not highlighted enough | The icon for stopping a run is not intuitive and isn't highlighted enough while a run is in progress. Suggest changing from grey to red. | Shir Cohen | Mario Steiner | — | — | 2 | 1 |
| 🟢 Nice-to-have | Personal agent icon and team agent icon recommendations | Personal agent icon — recommendation to change it to a person, and team to three people. | Shir Cohen | Mario Steiner | — | — | 2 | 1 |
| 🟢 Nice-to-have | Test case selection UI not intuitive — checkbox affordance unclear | The UI for selecting a test case is not intuitive. When you hover over a test, the checkbox appears empty and doesn't clearly indicate it can be selected. | Shir Cohen | Mario Steiner | — | — | 2 | 1 |
| 🟢 Nice-to-have | Having a Builder header as well as a builder option is confusing | Having a Builder header, as well as builder option, is confusing. | Shir Cohen | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Please consider making the text bold | Please consider making the text bold. | Shir Cohen | Anna Swietek | — | — | 2 | 1 |

---

### Parameter/Value Editing — 9 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Default values of modules should be used in TestCase creation | Default values of modules should be used in TestCase creation to instantiate already the test step values. | Michael Januschek | Neven Kristijan | [TOSCA-32789](https://tricentis.atlassian.net/browse/TOSCA-32789) | — | 4 | 1 |
| 🟠 High | Highlighting Parameter names for correctness indication not yet in cloud | Highlighting Parameter names to get indication for correctness in cloud is not yet exist. | Filip Seles | Neven Kristijan | — | — | 4 | 1 |
| 🟡 Medium | Test case builder — Action mode dropdown autocomplete and highlighting | Test case builder — Action mode / Data type dropdowns: start typing value name — highlighting is currently extremely light and not contrast, value autocomplete would be nice too. | Yuliya Razhkova | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Creating business parameters works differently from CPs and buffers | Creating business parameters works differently from creating CPs and buffers, which makes it unintuitive for first-time users. | Shir Cohen | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Add possibility to set ValueRange for RTSB parameters | Add possibility to set ValueRange for RTSB parameters. Also it should be possible to migrate ValueRange values from Tosca on-prem. | Andrei Korzun | Neven Kristijan | [TOSCA-36832](https://tricentis.atlassian.net/browse/TOSCA-36832) | — | 3 | 1 |
| 🟢 Nice-to-have | Lock mechanism for parameters and their values | Lock mechanism for parameters and their values to keep stuff as it is till its really needed to be changed. | Filip Seles | Anna Swietek | — | Closed | 2 | 1 |
| 🟢 Nice-to-have | Color coding missing for populated test step values | Test case builder steps based on a SpecialExecutionTask — color coding is missing for currently populated test step values. | Yuliya Razhkova | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Add alert / lower opacity to non-used Test Case params | Add alert svg / Lower Opacity to non used Test Case params. | Ran Ferdinaro | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Test Case Params should be ordered alphabetically | Test Case Params should be ordered Alphabetically and not by order of creation. | Ran Ferdinaro | Mario Steiner, Neven Kristijan | — | — | 2 | 1 |

---

### General UX — 8 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Visibility of populated test step values and hide "do nothing" steps | Visibility of populated test step values and hide do nothing steps would be also nice to have as this is making the readability of the testcase better. | Michael Januschek | Neven Kristijan | [TOSCA-9589](https://tricentis.atlassian.net/browse/TOSCA-9589) | — | 4 | 1 |
| 🟠 High | E2G/Launcher setup is weird — need a direct button to install and start agent | Setup of E2G/launcher is weird with first install launcher and then install all the other by trigger execution. There should be a button after you install the launcher to be able to install the components and start the agent immediately. | Michael Januschek | Edouard De Lansalut | [TOSCA-41023](https://tricentis.atlassian.net/browse/TOSCA-41023) | — | 4 | 2 |
| 🟡 Medium | Navigation to Inventory requires click on "Build" — not intuitive | In order to get to inventory, you need to click on "Build". This is not that intuitive. | Shir Cohen | Anna Swietek | — | — | 3 | 1 |
| 🟡 Medium | User should be able to go directly to module/RTSB detail from test run result page | User should be able to directly go to the module or RTSB detail from a test run result page. Currently, they have to open the test case and find the specific module RTSB. | Elvin Senoymak | Mario Steiner | [TOSCA-34497](https://tricentis.atlassian.net/browse/TOSCA-34497) | Approved | 3 | 1 |
| 🟢 Nice-to-have | When creating a first test and new module, auto-add module to test | When you create your first test and create a new module, it would be useful to automatically add that module to the test, or to have it already selected for the user. | Shir Cohen | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | The UI 'Create' button dropdown misleads — both actions same function | The UI 'Create' button gives the impression that there are two different options, but both actions perform the same function. | Shir Cohen | Anna Swietek | — | — | 2 | 1 |
| 🟢 Nice-to-have | Launcher version info inconsistent across two download locations | Launcher version — there are two places where you can download the Launcher. In one place, the version number is shown, but in the other place it isn't. | Shir Cohen | Edouard De Lansalut | — | — | 2 | 1 |
| 🟢 Nice-to-have | Make the duplication of a test case more intuitive | It would be nice to make the duplication of a test case more intuitive to the user. | Shir Cohen | Anna Swietek | — | — | 2 | 1 |

⚠️ Row 9 (E2G/Launcher setup) is a near-duplicate of row 30 — consider merging.

---

### Reporting & Dashboards — 4 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Dashboards lack custom report capabilities | Dashboards don't have any benefits yet, pls add possibilities to create custom report so you can create a daily report for filtered list or specific items. | Michael Januschek | Ondrej Mayer | — | — | 4 | 1 |
| 🟠 High | Custom dashboard combining data from different workspaces | Custom dashboard from different workspaces so you can combine specific lists into one big report. | Michael Januschek | Ondrej Mayer | — | — | 4 | 1 |
| 🟠 High | Visibility of requirements and logs as a Report | Visibility of requirements and logs as a Report. | Michael Januschek | Ondrej Mayer | — | — | 4 | 1 |
| 🟡 Medium | Requirements connected to TestCases reportable in daily business | Requirements which are connected to Testcases or some Report to be able to use Reporting in a daily business or send out reports to someone. | Michael Januschek | Neven Kristijan | — | — | 3 | 1 |

---

### Tree/Folder Organization — 7 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Show asset folder path in Builder (not only in Inventory) | Showing asset folder path in builder — in inventory it is possible to organize assets in folder and sub-folders, but when opening same asset in builder I don't see path to its own location. | Filip Seles | — | — | — | 4 | 1 |
| 🟡 Medium | Playlists and test cases don't have a similar UI — no folder support in playlists | Playlists and test cases don't have a similar user interface. Right now, you can't create folders in the playlist tree, while in test cases you can. | Shir Cohen | Mario Steiner | — | — | 3 | 1 |
| 🟡 Medium | Relationship between tree and right-side content is not clear | The relationship between the tree and the content displayed on the right side is not clear. | Shir Cohen | Kevin Horvath | — | — | 3 | 1 |
| 🟢 Nice-to-have | Module not visible in tree after creation | When creating a new module manually and saving it, Tosca does not show its position in the module tree. | Shir Cohen | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Module list not visible while on a specific module | When you are on a specific module, you cannot see the module list on the left. | Shir Cohen | Neven Kristijan | — | — | 2 | 1 |
| 🟢 Nice-to-have | Playlist view missing plus (+) icon for creating a new folder | In the Playlist view, there is no plus (+) icon for creating a new folder, unlike in the Test Cases view. | Shir Cohen | Mario Steiner | — | — | 2 | 1 |
| 🟢 Nice-to-have | Deletion flow from the tree is not intuitive | The deletion flow from the tree is not intuitive. | Shir Cohen | Anna Swietek | — | — | 2 | 1 |

---

### Tabs/Windows/Navigation — 5 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Add test step UX: module search not resetting value when switching tabs | Table handling in TestCase creation for module search is not resetting the value from the search when switching from standard objects to user assets. | Michael Januschek | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Inconsistent right-click "open in new tab" behaviour across components | Inconsistent opening of links with right click in new tab, some components have a custom menu and some have the standard behavior of links. | Michael Januschek | Kevin Horvath | — | — | 3 | 1 |
| 🟡 Medium | Tosca opens too many new tabs — needs pop-up/dockable panel solution | Tosca in general opens many new tabs for new user actions. Use pop-up windows/dockable windows or panels that will lower the amount of new created tabs. | Shir Cohen | Kevin Horvath | — | — | 3 | 2 |
| 🟡 Medium | Window titles should better describe the component in each tab | Use different window titles to describe better the component so we will know what exists in each tab, when we have so many tabs opened. | Shir Cohen | Kevin Horvath | — | — | 3 | 1 |
| ⚪ Unset | Create a solution minimizing window openings and navigation clicks | Create a solution that minimizes window openings, enables navigation within the same page, and requires the fewest possible clicks to reach new screens. | Shir Cohen | Kevin Horvath | — | — | 3 | 2 |

⚠️ Rows 50 and 108 are near-duplicates (excess tab/window openings) — consider merging.

---

### Help/Docs/Guidance — 5 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Add agent tutorial video for characteristics | Add agent tutorial video of how to use characteristics. | Shir Cohen | Mario Steiner | — | — | 3 | 1 |
| 🟡 Medium | Agent Characteristic — show error if tag not created after typing | Agent Characteristic — when the user types text but doesn't create a tag (because Enter wasn't pressed), please show an error message so the user knows the tag was not created. | Shir Cohen | Mario Steiner | — | — | 3 | 1 |
| 🟡 Medium | Every error message should include actionable next steps | Please ensure that every error message includes clear instructions on what the user should do next. | Shir Cohen | Anna Swietek | — | — | 3 | 1 |
| 🟢 Nice-to-have | Add short videos / links to docs for reusable test steps and business params | Consider adding short videos to explain better how to create complicated test scenarios for the first time. | Shir Cohen | Neven Kristijan | [Docs link](https://docs.tricentis.com/tosca-cloud/en-us/content/create_tests/design_reusable_teststeps.htm) | — | 2 | 1 |
| 🟢 Nice-to-have | API tutorial video uses old Tosca Cloud UI — needs update | API tutorial video is with an old Tosca cloud UI. Need to update it. | Shir Cohen | Christopher Colosimo | — | — | 2 | 1 |

---

### Playlist & Run Management — 5 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Track which test cases are used in which playlists | Used test cases references to playlist — with increase number of created test cases in workspace it is hard to track which of them are used in playlist and to what playlist they are linked. | Filip Seles | — | — | — | 4 | 2 |
| 🟡 Medium | Add UI Toggle to Base64-Decode API Message Payload in Run | Test runs: Add UI Toggle to Base64-Decode API Message Payload in Run. | Daniel Hammerschmidt | Mario Steiner | [TOSCA-38511](https://tricentis.atlassian.net/browse/TOSCA-38511) | Approved | 3 | 1 |
| 🟡 Medium | Test Runs and Playlist Run History pages should be consolidated | The Test Runs and Playlist Run History pages are a bit confusing. Their UI should be more closely aligned, and ideally consolidated into a single page. | Shir Cohen | Mario Steiner | — | — | 3 | 1 |
| 🟡 Medium | Add a TestCase to multiple Playlists at once | Add a TestCase to multiple Playlists at once to avoid repetitive manual action. | Daniel Hammerschmidt | Mario Steiner | [TOSCA-36736](https://tricentis.atlassian.net/browse/TOSCA-36736) | Approved | 3 | 1 |
| 🟢 Nice-to-have | Confusing wording: "Test runs" vs playlists; "Rerun failed test" vs playlist | The wording 'Test runs' is confusing, because you actually run a playlist, not a single test. Also: "Rerun failed test" is confusing, as it's actually re-run the playlist. | Shir Cohen | Mario Steiner | — | Rejected | 2 | 1 |

⚠️ Row 31 (track test case references) is a near-duplicate of row 106 (Show all module/RTSB references before delete) — related but distinct enough to keep separate.

---

### AI Features — 4 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | AI: Generate test cases from Epic/Story requirements | Take a product Epic/Story with detailed requirements and acceptance criteria, and create test cases according to them. | Shir Cohen | Paulina Steidel | — | — | 4 | 1 |
| 🟠 High | AI: Auto-generate test cases and modules with step/value guidance | Auto generating of test cases and module creation by AI with introduction which modules and which steps with which values. | Michael Januschek | Paulina Steidel | — | — | 4 | 1 |
| 🟠 High | AI: Generate test case summary from steps for documentation/reporting | AI features in general by creating summary of test case by steps to easily generate summaries to document or report to people. | Michael Januschek | Paulina Steidel | — | — | 4 | 1 |
| 🟠 High | AI: Summarise execution run and report what problem occurred | AI feature like summary of execution run by actions, easily report what is the problem and what could be changed as a report from the AI. | Michael Januschek | Paulina Steidel | — | — | 4 | 1 |

---

### Query/Search (TQL) — 2 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | TQL ability to query and bulk-change items in cloud not yet available | TQL ability to query stuff in cloud is not possible yet. Need something to be able to bulk change steps/values/testcases/items. Would also be nice to know which module attributes are unused, and search for references of specific CP/Buffer/PL. | Michael Januschek | Anna Swietek | — | — | 4 | 1 |
| 🟠 High | Save queries / virtual folders to find items by criteria in workspace | Saving Queries to find specific items in the whole workspace or cloud would be nice, like the virtual folder in Tosca Commander to find items which have a specific criteria. | Michael Januschek | Anna Swietek | [TOSCA-40967](https://tricentis.atlassian.net/browse/TOSCA-40967) | — | 4 | 1 |

---

### File/Attachment Handling — 2 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | File, attachment, test data handling at module/testcase level for cloud agent download | Handling of Files, Attachments, test data, general resources at tosca objects level. Attach files to modules or testcases to be able to download them on the cloud agent where the tests are running without integrating to a fileshare or blob storage. | Michael Januschek | Kevin Horvath | — | — | 4 | 1 |
| 🟡 Medium | Buffer Viewer to see names and values of set buffers in Cloud UI | Buffer Viewer to see which buffers have already been set — names and values. Currently stored in local TBox.Buffer.json file but nowhere on Tosca Cloud UI. | Yuliya Razhkova | Neven Kristijan | [TOSCA-37225](https://tricentis.atlassian.net/browse/TOSCA-37225) | — | 3 | 1 |

---

### Module Scanning — 2 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Add Button for Scanning modules from inventory | Add Button for Scanning modules from inventory. | Michael Januschek | Anna Swietek | [TOSCA-31481](https://tricentis.atlassian.net/browse/TOSCA-31481) | — | 3 | 2 |
| 🟢 Nice-to-have | Reduce clicks needed to scan a module from the Test case builder | Reduce amount of clicks needed to scan a module from the Test case builder. Currently user needs: Create button → Create module → Select XScan → Click Start scan. | Yuliya Razhkova | Neven Kristijan | — | — | 2 | 2 |

⚠️ Rows 34 and 93 are near-duplicates (reduce clicks to scan a module) — consider merging.

---

### Delete/Edit Behavior — 4 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Right-click Delete only deletes one of two selected test steps | When selecting two different test steps and then right-clicking and choosing Delete, only one test step is deleted. | Shir Cohen | Neven Kristijan | — | — | 3 | 1 |
| 🟢 Nice-to-have | Show all module/RTSB references before delete | Show all module/RTSB references before delete. | Filip Seles | — | — | — | 2 | 2 |
| 🟢 Nice-to-have | Allow contributors to delete tests; add three user roles | Allow contributors to delete tests. Also allow three user roles: read-only, read-write, and admin. | Shir Cohen | Martin Filip | [TOSCA-36335](https://tricentis.atlassian.net/browse/TOSCA-36335) | — | 2 | 1 |
| 🟢 Nice-to-have | Add delete button inside Builder for modules, test cases, and RTSBs | I want option (button) to delete Module (also test cases, and RTSB) when I am inside Builder. | Filip Seles | — | — | — | 2 | 1 |

⚠️ Row 106 (Show all module/RTSB references before delete) is a near-duplicate of row 31 — related; consider merging.

---

### Collaboration/Notifications — 2 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Review of tests with comments, PR-style notifications | Review of tests with comments sent by mail or so would be handy to see that someone has changed something and want a review. Like GitHub or DevOps to have Pull requests with changes. | Michael Januschek | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Configurable mail settings for specific services and features | We would like to control the Mail settings. Please make it adjustable for specific services and features. | Michael Januschek | Martin Filip | [TOSCA-519](https://tricentis.atlassian.net/browse/TOSCA-519), [TOSCA-41509](https://tricentis.atlassian.net/browse/TOSCA-41509) | — | 3 | 1 |

---

### Logging & Debugging — 2 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Debugging needs to be easier — get more logs, see sent/received payloads | Debugging needs to be easier for example api engine, get more logs, enable the cloud to see what was sent and what was received like in commander with the feature flag. | Filip Seles | Mario Steiner | [TOSCA-36148](https://tricentis.atlassian.net/browse/TOSCA-36148) | Closed | 3 | 1 |
| 🟡 Medium | Extended log — filter logs for specific engines or error type | Extended log for specific stuff, filter logs for specific engines or error type. | Elvin Senoymak | Mario Steiner | [TOSCA-41499](https://tricentis.atlassian.net/browse/TOSCA-41499) | Approved | 3 | 1 |

---

### Reference/Usage Tracking — 2 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Explicit execution signal for missing Module/RTSB references | Explicit Execution Signal for Missing Module/RTSB References. | Filip Seles | — | — | — | 3 | 1 |
| 🟢 Nice-to-have | Show all module/RTSB references before delete | Show all module/RTSB references before delete. | Filip Seles | — | — | — | 2 | 2 |

⚠️ Rows 31 and 106 are near-duplicates (reference/usage tracking before delete) — consider merging.

---

### Keyboard Shortcuts — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Full keyboard shortcut support across the product | Keyboard shortcuts for the whole product for workflow, keyboard full support. For example: Pressing Enter on the keyboard does not select the browser. | Elvin Senoymak | Kevin Horvath | — | — | 4 | 1 |

---

### Autosave/Data Loss — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟠 High | Autosave mode or session-expiration warning to prevent data loss | Autosave mode (e.g. a button in the test cases builder which will activate the autosave for the current user session or a special test case state) or at least a warning message for session expiration would be helpful, so data won't get lost. | Filip Seles | Neven Kristijan | — | — | 4 | 1 |

---

### Expand/Collapse — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Ability to expand/collapse a specific test step, not only the entire test case | We would like to have the ability of expanding and collapsing of a specific test step, and not only the entire test case. | Elvin Senoymak | Neven Kristijan | — | — | 3 | 1 |

---

### Drag & Drop — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Drag and drop modules/RTSBs across windows into test cases | Drag and drop UX experience. For example: we can't drag and drop modules and RTSBs in one window into a test cases which exists in a different window. | Elvin Senoymak | Neven Kristijan, Mario Steiner | [TOSCA-35021](https://tricentis.atlassian.net/browse/TOSCA-35021) | — | 3 | 1 |

---

### Test Planning & Assignment — 3 requests

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | Add precondition description with test case links | Having the option to add precondition description (text only, not test steps/cases to execute, with an option to add test cases links). | Michael Januschek | Neven Kristijan | — | — | 3 | 1 |
| 🟡 Medium | Planning of tests with status and distributed to someone | Planning of tests with status and distributed to someone. | Michael Januschek | Anna Swietek | — | — | 3 | 1 |
| 🟡 Medium | Proper Assigning of Test Tasks — Reusable blocks by parameterized | Proper Assigning of Test Tasks. Reusable blocks/resources by parameterized. | Michael Januschek | Anna Swietek | — | — | 3 | 1 |

---

### Workspace Handling — 1 request

| Priority | Title | Key Ask | Submitter | PM Lead | Jira | Status | Sev | Occ |
|----------|-------|---------|-----------|---------|------|--------|-----|-----|
| 🟡 Medium | 502 error always redirects to Default workspace instead of last used | When an unexpected server side error occurs (such as the browser returns a 502 bad gateway error), the system always redirects back to the Default workspace. | Shir Cohen | Martin Filip | — | — | 3 | 1 |

