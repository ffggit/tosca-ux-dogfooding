# Workshop Brief — Tosca Cloud UX Dogfooding

_Prepared for: Joint UX + PM session_
_Date: 2026-07-02_

---

## Context

Six Tricentis UX designers used Tosca Cloud as real users over a series of dogfooding sessions, logging issues as they encountered them. Issues were collected independently, then reviewed as a group to identify patterns that appeared across multiple designers. The 126 issues logged cover the core Tosca Cloud workflows: scanning, test authoring, execution, results, and setup.

---

## Key numbers

| Metric | Value |
|---|---|
| Total issues logged | 126 |
| Designers who participated | 6 |
| Critical issues | 8 |
| Most affected area (by designer reach) | Launcher — touched by 5 of 6 designers |
| Top issue type | Unnecessary steps / extra friction (48 occurrences) |

---

## Top cross-designer patterns

**1. No confirmation after an action**
Designers affected: Franc, Angelika, Jekaterina, Diogo (4 of 6)
When a user clicks Save, Download, Record, or Link, nothing happens on screen — no message, no visual change, no loading indicator. Users don't know if the action worked. Many retry, which can create duplicates or data inconsistencies.

**2. Launcher fails with no explanation**
Designers affected: Franc, Angelika, Diogo (3 of 6)
When the Launcher fails to start — due to antivirus software, a missing browser extension, or a connection problem — the user sees either a generic technical message or nothing at all. There are no steps to fix the problem. The user is stuck with no way forward.

**3. Scanning complex screen elements is broken or undocumented**
Designers affected: Giovanni, Ana-Maria (2 of 6, but 7 reported issues)
XScan cannot reliably handle dropdowns, floating menus, drag-and-drop areas, or tables. When it fails, it either captures the wrong thing silently or gives no guidance on what to do. Users can only unblock themselves by searching external documentation.

**4. No clear signal when a test starts or finishes running**
Designers affected: Jekaterina, Giovanni (2 of 6)
After clicking Run, the screen gives no indication anything has started. After the run completes, the result is shown only as a color change on a progress bar — no summary, no clear pass/fail. In one case the status showed "pending" after the run had already finished.

**5. Setup steps require knowledge the product never shares**
Designers affected: Franc, Jekaterina (2 of 6)
The Data Integrity setup and template flows have hidden requirements — a connected database, a specific file on the agent machine, a Windows-only component. Users only discover these requirements when they hit a wall. There is no guidance in the product to explain what is needed before the user starts.

---

## Critical issues

| Issue ID | Designer | Description | Blocks workflow? | Cross-designer? |
|---|---|---|---|---|
| A-04 | Angelika Zych | Launcher is Windows-only; macOS users get no warning and cannot proceed | Yes | Yes — Group 2 |
| J-05 | Jekaterina Aleksejeva | Instantiation says "successful" but the result list shows nothing | Yes | Yes — Group 16 |
| J-20 | Jekaterina Aleksejeva | No in-product way to diagnose why instantiation produced no results; user gives up and searches external docs | Yes | Yes — Group 10 |
| G-01 | Giovanni Tocco | No service account or token login option; automation setup completely blocked | Yes | No — unique |
| D-04 | Diogo Lopes | Scan produces a blank page; task cannot be completed | Yes | No — unique |
| AM-04 | Ana-Maria Neaga | Cannot scan dropdown menus or floating nav without external guides | Yes | Yes — Group 11 |
| AM-07 | Ana-Maria Neaga | Cannot scan drag-and-drop interactions without documentation | Yes | Yes — Group 11 |
| AM-12 | Ana-Maria Neaga | Scanning tables and creating table-based automations is very difficult | Partial | Yes — Group 11 |

6 of 8 Critical issues were confirmed by more than one designer. The two unique Criticals (G-01, D-04) are complete blockers on specific paths that may affect any user who reaches them.

---

## Recommended focus areas for the workshop

**1. Launcher reliability and error handling**
Priority reason: The Launcher is the entry point to nearly all testing workflows. 5 of 6 designers encountered problems here. When it fails silently, no one can move forward.
Discussion question: What does PM know about the most common Launcher failure scenarios in production, and do we have data on how often users abandon at this step?

**2. Feedback and status messages across all actions**
Priority reason: Missing confirmation after actions (save, run, record, link) was the most widespread pattern, affecting 4 of 6 designers and appearing across every feature area tested.
Discussion question: Are there product constraints (technical or intentional) that explain why so many actions produce no visible response, or is this a gap that has not been prioritized?

**3. XScan handling of complex controls**
Priority reason: 7 issues from 2 designers, 3 rated Critical. This affects the core scanning capability that much of Tosca's value depends on. If XScan cannot handle standard web controls reliably, automation is not viable for many real-world applications.
Discussion question: What controls or interaction types are officially out of scope for XScan, and how is that communicated to users today?

**4. Setup and onboarding for Data Integrity and templates**
Priority reason: Users hit hidden prerequisites with no guidance. This creates a failure mode where users cannot tell whether they have done something wrong or whether the product is broken.
Discussion question: Is there a planned onboarding or setup wizard for DI or templates, or is the expectation that users rely on external documentation?

**5. Test results and run status clarity**
Priority reason: "Pending" shown after a completed run, no clear pass/fail, 3+ clicks to reach failure details. Users cannot complete the basic loop of run → understand result → fix. Confirmed across Jekaterina and Giovanni's sessions.
Discussion question: What does the intended results experience look like from a PM perspective, and where does the current implementation fall short of that design intent?

---

## Open questions

- Which of these issues are already known? Are any in the backlog, and if so, what is their current status?
- Are there user segments (e.g., less experienced users, customers on specific Tosca versions) for whom these issues are more severe or more frequent?
- The Launcher problems on macOS affect at least 2 designers. How large is the macOS user base in production, and is a macOS Launcher on the roadmap?
- Authentication via service accounts (G-01) was a complete blocker for Giovanni but no other designer hit it. Is this a known gap for CI/CD integration use cases, and who owns that path?
- Several workflows — full ARA recording, SQL Editor, Inventory management — were barely tested. Should a second round of dogfooding target those areas before conclusions are drawn?
- The product frequently sends users to external documentation when they are stuck in-product. Is there a plan or owner for in-product help content, or is that dependency intentional?
