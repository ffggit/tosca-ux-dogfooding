# Top 5 Critical Requests — Tosca Cloud Community
Date: 03.07.2026 | For: Executive review

---

## Summary

The five highest-priority improvement requests span two critical pillars of the Tosca Cloud adoption journey: cross-workspace asset sharing (the only sev-5 feature request with a confirmed duplicate, meaning multiple independent teams are blocked) and migration correctness bugs that directly prevent test suites from reaching the cloud. Immediate PM action on these five items would unblock the largest number of teams and remove the most significant barriers to cloud migration adoption.

---

## #1 — Assets sharing of reusables or modules across workspaces

- **Priority:** 🔴 Critical
- **Severity:** 5
- **Occurrence:** 2 (rows 1 and 29 — confirmed near-duplicates)
- **Feature Area:** Asset/Resource Sharing
- **Submitter:** Michael Januschek (row 1); Filip Seles, Daniel Hammerschmidt (row 29)
- **PM Lead:** Anna Swietek
- **Jira:** [TOSCA-31764](https://tricentis.atlassian.net/browse/TOSCA-31764)
- **The ask:** Assets sharing of reusables or modules across workspaces.
- **Why it matters:** Multiple teams — including both the original requester and a second independent group — have flagged that there is currently no way to share reusable test assets or modules between workspaces in Tosca Cloud. This forces teams to either duplicate assets in every workspace or maintain a single workspace, both of which introduce significant maintenance overhead and reduce the value of the cloud's multi-workspace architecture. The fact that this ask is Critical-priority with a confirmed independent duplicate places it as the single highest-demand unresolved feature in the dataset.

---

## #2 — Database Engine Tests (101 Tests) blocked by upload bug

- **Priority:** 🟠 High
- **Severity:** 5
- **Occurrence:** 1
- **Feature Area:** Migration/Upload Correctness
- **Submitter:** Michael Januschek
- **PM Lead:** Neven Kristijan
- **Jira:** [TOSCA-34864](https://tricentis.atlassian.net/browse/TOSCA-34864) (status: Done)
- **The ask:** Database Engine Tests (101 Tests) are currently blocked by upload bug, Builder team are aware of broken referenced module in test.
- **Why it matters:** A confirmed upload bug broke the migration of 101 Database Engine tests in a single batch — a significant portion of a team's test estate rendered inaccessible in the cloud. While the Jira ticket is marked Done, the resolution should be verified with the submitter to confirm that all 101 tests now upload and execute correctly in cloud. A silent close without user confirmation of resolution would leave the risk open.

---

## #3 — Copy/paste parity across the test builder (cluster of 4 requests)

- **Priority:** 🟠 High
- **Severity:** 4
- **Occurrence:** 4 (rows 4, 5, 8, 15 — confirmed near-duplicate cluster)
- **Feature Area:** Copy/Paste & Duplicate
- **Submitter:** Michael Januschek (rows 4, 5, 15), Elvin Senoymak (row 8)
- **PM Lead:** Neven Kristijan (rows 4, 5, 8); Kevin Horvath (row 15)
- **Jira:** [TOSCA-37666](https://tricentis.atlassian.net/browse/TOSCA-37666) (rows 4, 5, 8)
- **The ask:** Copy pasting stuff from one step to another or for values or whole test steps or structures. Copy and pasting of blocks, through a test creation (also using keyboard shortcuts). Copy/edit/delete/create behavior should be everywhere the same — add missing functionality to all items in the cloud like we have in tosca so you can any time right click and copy or duplicate or delete.
- **Why it matters:** This is the highest-occurrence confirmed near-duplicate cluster in the entire dataset: four independent requests from at least two different users describe the same core gap. Copy-paste is a fundamental workflow action in test design; its absence forces testers to manually recreate test steps and module configurations. Users explicitly compare the cloud unfavourably to Tosca Commander, and the lack of consistent right-click context menu actions (copy, duplicate, delete) degrades both speed and confidence when authoring tests. The four requests should be consolidated into a single tracking ticket.

---

## #4 — Credential handling and reusable connections in Tosca Cloud (cluster of 3 requests)

- **Priority:** 🟠 High
- **Severity:** 4
- **Occurrence:** 3 (rows 3, 28, 72 — confirmed near-duplicate cluster)
- **Feature Area:** Credentials & Connections
- **Submitter:** Michael Januschek (row 3), Andrei Korzun (row 28), Daniel Hammerschmidt (row 72)
- **PM Lead:** Mario Steiner (rows 3, 28); Christopher Colosimo (row 72)
- **Jira:** [TOSCA-28668](https://tricentis.atlassian.net/browse/TOSCA-28668) (rows 3, 28); [TOSCA-20667](https://tricentis.atlassian.net/browse/TOSCA-20667) (row 72)
- **The ask:** Credential handling and configurations/environments. Customer would love to create connections which are often used and reuse them on testcase, playlist or reusable test step block level. We are missing the connection manager in cloud.
- **Why it matters:** Three separate users from different teams have flagged a related gap: Tosca Cloud lacks a connection manager and the ability to define, store, and reuse credentials or environment configurations across test artefacts. In migration scenarios (row 28), only top-level TCPs are carried over and inherited configurations are silently dropped — a correctness bug that can cause migrated tests to run against unintended environments. The absence of a connection manager (row 72) means every test that relies on a connection must handle it ad hoc. Mario Steiner and Christopher Colosimo should coordinate to ensure the three related tickets are consolidated and resolved together.

---

## #5 — AI test case and execution summary generation

- **Priority:** 🟠 High
- **Severity:** 4
- **Occurrence:** 1 per request (4 individual AI requests, all from the same area)
- **Feature Area:** AI Features
- **Submitter:** Shir Cohen (row 20), Michael Januschek (rows 21, 22, 23)
- **PM Lead:** Paulina Steidel
- **Jira:** No ticket for any of the four AI requests
- **The ask:** (1) Take a product Epic/Story with detailed requirements and acceptance criteria, and create test cases according to them. (2) Auto generating of testcases and module creation by AI with introduction which modules and which steps with which values. Highly needed for competing with other testing tools as they are script based and are able to be generated. (3) AI features in general by creating summary of testcase by steps to easily generate summaries to document or report to people. (4) AI feature like summary of execution run by actions, easily report what is the problem and what could be changed as a report from the AI.
- **Why it matters:** Four distinct but thematically coherent AI feature requests have been submitted with no existing Jira tickets and no status. Together they represent a clear competitive-positioning concern: the community explicitly notes that script-based tools from competing vendors can auto-generate tests, making AI-assisted test creation a table-stakes expectation rather than a luxury feature. The four asks span the full test lifecycle — generation from requirements, module suggestion, test case documentation, and execution triage — and all currently fall to PM Paulina Steidel with zero tracked follow-up. Creating a single discovery or epic ticket to evaluate the AI feature roadmap against these four asks is the minimum action required.

---

## Recommended Actions

- **#1 — Asset sharing (TOSCA-31764):** Anna Swietek to confirm whether the existing Jira ticket covers both row 1 and row 29 scenarios; if not, update the ticket scope. Escalate to the roadmap given the Critical priority and confirmed community-wide demand.
- **#2 — Database Engine upload bug (TOSCA-34864):** Neven Kristijan to contact Michael Januschek directly to verify that the Done status reflects a user-confirmed fix, not just a code change. Reopen if the 101 tests still cannot be uploaded or executed.
- **#3 — Copy/paste parity (TOSCA-37666):** Neven Kristijan and Kevin Horvath to consolidate rows 4, 5, 8, and 15 into a single ticket. Align on a delivery target given this is the highest-occurrence confirmed cluster in the dataset.
- **#4 — Credentials/connection manager (TOSCA-28668, TOSCA-20667):** Mario Steiner and Christopher Colosimo to meet and determine whether TOSCA-28668 and TOSCA-20667 should be merged or linked. The inherited-TCP migration bug (row 28) is a correctness issue that should be separated from the feature request for a connection manager UI (row 72).
- **#5 — AI features:** Paulina Steidel to create a discovery ticket capturing all four AI asks (rows 20–23), establish a prioritisation discussion, and communicate a timeline back to the community submitters (Shir Cohen, Michael Januschek).
