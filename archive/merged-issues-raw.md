# Merged UX Issues — Raw Ingest

## Issue counts per designer

| Designer | Issues | Source |
|---|---|---|
| Franc González | 17 | GitHub |
| Angelika Zych | 6 | GitHub |
| Jekaterina Aleksejeva | 28 | GitHub |
| Giovanni Tocco | 23 | GitHub |
| Diogo Lopes | 30 | GitHub |
| Ana-Maria Neaga | 22 | Confluence |
| **Total** | **126** | |

---

## All issues

| id | designer | feature_area | severity | issue_type | description | source |
|---|---|---|---|---|---|---|
| F-01 | Franc González | Data Integrity | Major | Help & guidance | No guidance that a working DB with accessible tables is required before DI module use | GitHub |
| F-02 | Franc González | Data Integrity | Major | Feedback | "SQL command execution timed out" names the symptom, not the cause (query, connection, or server) | GitHub |
| F-03 | Franc González | Data Integrity | Major | Help & guidance | No indication that SQLite file path must be on the agent machine, not the local Mac | GitHub |
| F-04 | Franc González | Data Integrity | Major | Feedback | "Use caching database" checkbox gives no feedback on existence or failure | GitHub |
| F-05 | Franc González | Data Integrity | Major | Help & guidance | Entire DI setup flow assumes Windows; Mac users hit multiple silent blockers with no in-product guidance | GitHub |
| F-06 | Franc González | Data Integrity | Major | Feedback | Test Connection runs server-side but gives no indication; timeout misread as connection failure | GitHub |
| F-07 | Franc González | Data Integrity | Minor | Efficiency | Search returns no results when querying by Last modified by | GitHub |
| F-08 | Franc González | Launcher | Major | Feedback | TBox quarantined by antivirus; UI shows only "Component executable not found" | GitHub |
| F-09 | Franc González | Launcher | Major | Feedback | Extension helper exe blocked; error names the file but provides no actionable steps | GitHub |
| F-10 | Franc González | Launcher | Major | Help & guidance | Launcher installs browser extension with no prior warning | GitHub |
| F-11 | Franc González | Launcher | Major | Feedback | Test run silently fails when extension cannot connect | GitHub |
| F-12 | Franc González | Launcher / Builder | Major | Feedback | Silent failure in Builder after Launcher-triggered event | GitHub |
| F-13 | Franc González | Builder — SQL Editor | Major | Help & guidance, Efficiency | SQL Editor shows "Unknown Connection"; Run SQL button disabled with no tooltip | GitHub |
| F-14 | Franc González | Launcher | Major | Help & guidance | No in-product guidance that corporate security policies may block execution | GitHub |
| F-15 | Franc González | Agents / Run tests | Minor | Help & guidance | Agents page shows cloud agent with no type indication | GitHub |
| F-16 | Franc González | Playlists / Run tests | Minor | Efficiency | Playlist test run dropdown — issue with run configuration | GitHub |
| F-17 | Franc González | Data Integrity / Launcher | Major | Help & guidance | ToscaDataIntegrityExecutor folder not created automatically on first run | GitHub |
| A-01 | Angelika Zych | Settings/Workspaces | Minor | Language & clarity | "All users have access" label gives no info about what access level | GitHub |
| A-02 | Angelika Zych | Inventory/Test cases | Major | Help & guidance | Launcher install prompted with no prior warning, no system requirements, no explanation | GitHub |
| A-03 | Angelika Zych | Inventory/Test cases | Major | Error prevention, Efficiency | Automatically downloaded Windows .exe on macOS without OS detection; failed with error -10661 | GitHub |
| A-04 | Angelika Zych | Settings | Critical | Error prevention, Help & guidance | Launcher Windows-only but no Mac warning; macOS user completely blocked | GitHub |
| A-05 | Angelika Zych | Settings | Major | Feedback | No download confirmation; re-clicks re-download | GitHub |
| A-06 | Angelika Zych | Onboarding/Ara recording | Major | Feedback, Help & guidance | No confirmation a step was recorded; laggy recording with uncertainty | GitHub |
| J-01 | Jekaterina Aleksejeva | Test case templates | Major | Efficiency, Consistency | "Create a template" action missing from obvious entry points; exists only in single test case view | GitHub |
| J-02 | Jekaterina Aleksejeva | Test case templates | Major | Feedback, Language & clarity | After clicking "Create template" page still reads "Test cases"; user unsure of context | GitHub |
| J-03 | Jekaterina Aleksejeva | Test case templates | Minor | Help & guidance, Language & clarity | No guidance on what a template requires; user assumed DB connection needed | GitHub |
| J-04 | Jekaterina Aleksejeva | Test case templates | Major | Feedback, Error prevention | Linking test sheet shows no confirmation message; user linked wrong source undetected | GitHub |
| J-05 | Jekaterina Aleksejeva | Test case templates | Critical | Feedback, Error prevention, Help & guidance | Instantiation says "successful" but instances list shows "no results" — false success message | GitHub |
| J-06 | Jekaterina Aleksejeva | Test case templates | Major | Control & freedom, Consistency | Delete unavailable from template page; only works from "Test case templates" tab | GitHub |
| J-07 | Jekaterina Aleksejeva | Test data | Minor | Efficiency | No way to copy column name on Test Data page; must type manually | GitHub |
| J-08 | Jekaterina Aleksejeva | Test case templates | Minor | Efficiency | Instantiate gated behind separate Save; tooltip re-prompts save each time | GitHub |
| J-09 | Jekaterina Aleksejeva | Test case templates | Minor | Language & clarity, Control & freedom | Can only link a test sheet, not test data as user expected | GitHub |
| J-10 | Jekaterina Aleksejeva | Test sheets | Major | Language & clarity, Help & guidance | No in-context definitions for Attributes, Instances, Straight-through values | GitHub |
| J-11 | Jekaterina Aleksejeva | Test data | Minor | Efficiency | Continuous tab-switching between Test data and Test sheet to fill sheet | GitHub |
| J-12 | Jekaterina Aleksejeva | Test case templates | Major | Language & clarity, Consistency | "Test Sheet" names two different things (instance and source data structure) | GitHub |
| J-13 | Jekaterina Aleksejeva | Test case templates | Minor | Feedback, Efficiency | Clicking generated instance doesn't show content; "Open in new window" button not obvious | GitHub |
| J-14 | Jekaterina Aleksejeva | Test case templates | Minor | Efficiency, Consistency | No run action from template page; must create playlist elsewhere | GitHub |
| J-15 | Jekaterina Aleksejeva | Playlist | Minor | Consistency, Efficiency | Renaming by clicking title doesn't work; must use separate edit button | GitHub |
| J-16 | Jekaterina Aleksejeva | Playlist | Minor | Consistency | Test sheets appear in no logical order in select-cases screen | GitHub |
| J-17 | Jekaterina Aleksejeva | Playlist | Minor | Help & guidance, Language & clarity | Failure details behind red icon not obvious for first-time user | GitHub |
| J-18 | Jekaterina Aleksejeva | Test case templates | Major | Feedback | No snack bar confirmation after creating instances | GitHub |
| J-19 | Jekaterina Aleksejeva | Test case templates | Major | Consistency, Feedback | "Test case templates" tab refreshes instead of navigating to top level — "rage clicks" | GitHub |
| J-20 | Jekaterina Aleksejeva | Test case templates | Critical | Help & guidance, Error prevention | No in-product help to diagnose empty result; user abandons self-service for docs | GitHub |
| J-21 | Jekaterina Aleksejeva | Test case templates | Minor | Consistency, Language & clarity | Confirmation dialog says "Delete multiple artifacts?" but snackbar says "Folders deleted" | GitHub |
| J-22 | Jekaterina Aleksejeva | Test case templates | Major | Consistency, Efficiency | Instantiate button absent after fixing/saving; appears only when template row is clicked | GitHub |
| J-23 | Jekaterina Aleksejeva | Playlist | Cosmetic | Consistency | Column order in playlist grid is wrong (checkbox, dragging, rest instead of dragging, checkbox, rest) | GitHub |
| J-24 | Jekaterina Aleksejeva | Playlist | Major | Feedback | After clicking Run, no immediate indicator run started; only cursor change | GitHub |
| J-25 | Jekaterina Aleksejeva | Test execution (Tricentis Launcher) | Minor | Feedback, Efficiency | Launcher startup modal shows "starting up" only on later screen | GitHub |
| J-26 | Jekaterina Aleksejeva | Test execution (Tricentis Launcher) | Major | Error prevention, Visual noise, Consistency | Modal warns "Don't close during testing!" but has prominent red "Close agent" button | GitHub |
| J-27 | Jekaterina Aleksejeva | Test execution (Tricentis Launcher) | Major | Feedback, Error prevention | Launcher closed Chrome browser unexpectedly with no warning | GitHub |
| J-28 | Jekaterina Aleksejeva | Playlist | Minor | Feedback, Language & clarity | Results view shows "pending" after completed run | GitHub |
| G-01 | Giovanni Tocco | Authentication | Critical | Efficiency | No service account or token-based auth option; entire automation setup blocked | GitHub |
| G-02 | Giovanni Tocco | Authentication | Major | Efficiency | Multi-step auth workaround required | GitHub |
| G-03 | Giovanni Tocco | Scanner / XScan | Major | Help & guidance | XScan fails silently on Chrome incognito; no error message | GitHub |
| G-04 | Giovanni Tocco | Workspace management | Minor | Consistency | Scanned modules saved to wrong workspace; no workspace selector in scan flow | GitHub |
| G-05 | Giovanni Tocco | Scanner / XScan | Major | Efficiency | Captures dropdown container (DIV) rather than individual options | GitHub |
| G-06 | Giovanni Tocco | Test execution | Major | Feedback | No reliable post-action feedback after running test | GitHub |
| G-07 | Giovanni Tocco | Test execution | Minor | Help & guidance | Failure details require 3+ clicks from result screen | GitHub |
| G-08 | Giovanni Tocco | Scanner / XScan | Major | Efficiency | Cannot reliably target individual buttons inside grid rows | GitHub |
| G-09 | Giovanni Tocco | Playlist | Major | Feedback | After clicking Run, no feedback given; no loading indicator | GitHub |
| G-10 | Giovanni Tocco | Playlist | Minor | Feedback | No visual cue after action | GitHub |
| G-11 | Giovanni Tocco | Playlist | Major | Efficiency | Viewing why test failed requires 3 clicks minimum | GitHub |
| G-12 | Giovanni Tocco | Playlist / Agent | Major | Consistency | Playlist/Agent consistency issue | GitHub |
| G-13 | Giovanni Tocco | Launcher | Minor | Help & guidance | Launcher guidance missing | GitHub |
| G-14 | Giovanni Tocco | Workspace management | Minor | Consistency | Workspace management consistency issue | GitHub |
| G-15 | Giovanni Tocco | Workspace management | Major | Consistency | Workspace management major consistency issue | GitHub |
| G-16 | Giovanni Tocco | Workspace management | Minor | Consistency | Workspace management minor consistency issue | GitHub |
| G-17 | Giovanni Tocco | Builder | Minor | Efficiency | Builder efficiency issue | GitHub |
| G-18 | Giovanni Tocco | Builder | Minor | Efficiency | Builder efficiency issue | GitHub |
| G-19 | Giovanni Tocco | Builder / Modules | Major | Help & guidance | No option to name module before scan | GitHub |
| G-20 | Giovanni Tocco | Builder | Major | Efficiency | No autosave; disruptive save dialog appears when navigating away | GitHub |
| G-21 | Giovanni Tocco | Scanner / XScan | Major | Efficiency | No "rescan module" action; requires 8+ step workaround | GitHub |
| G-22 | Giovanni Tocco | Test execution | Major | Feedback | Only signal of completed run is execution bar losing orange color; no result summary | GitHub |
| G-23 | Giovanni Tocco | Test execution | Minor | Efficiency | Execution efficiency issue | GitHub |
| D-01 | Diogo Lopes | Inventory > Module editor (Xscan) | Major | Efficiency | Hard to add data-test id attributes | GitHub |
| D-02 | Diogo Lopes | Inventory > Module editor (Xscan) | Major | Efficiency | Pervasive slowness during scan | GitHub |
| D-03 | Diogo Lopes | Admin > Workspaces | Major | Efficiency | Creator not auto-added to own workspace; time lost, manual self-add required | GitHub |
| D-04 | Diogo Lopes | Inventory > Create Module | Critical | Feedback | Scan fails to blank page; task blocked | GitHub |
| D-05 | Diogo Lopes | Inventory > Launcher | Major | Help & guidance | Installed Launcher failed silently | GitHub |
| D-06 | Diogo Lopes | Inventory > Launcher | Major | Efficiency | Extreme slowness | GitHub |
| D-07 | Diogo Lopes | Inventory > Module editor | Major | Help & guidance | No guidance on module structure | GitHub |
| D-08 | Diogo Lopes | Inventory > Module editor (Xscan) | Major | Efficiency | Scans extremely slow | GitHub |
| D-09 | Diogo Lopes | Inventory > Module editor | Major | Help & guidance | Browser extension not bundled; prompted mid-scan | GitHub |
| D-10 | Diogo Lopes | Inventory > Module editor | Minor | Efficiency | Hidden controls; had to use Xscan filter slider | GitHub |
| D-11 | Diogo Lopes | Inventory > Module editor | Major | Consistency | Repeat Launcher dialog on every re-scan | GitHub |
| D-12 | Diogo Lopes | Inventory > Module editor | Major | Efficiency | Hard to add data-test id attributes | GitHub |
| D-13 | Diogo Lopes | Inventory > Module editor | Minor | Efficiency | No undo in module editor | GitHub |
| D-14 | Diogo Lopes | Inventory > Module editor | Minor | Efficiency | Module defaults not auto-added | GitHub |
| D-15 | Diogo Lopes | Inventory > Test case editor | Minor | Efficiency | Easy to miss save name/location | GitHub |
| D-16 | Diogo Lopes | Inventory > Test case editor | Minor | Consistency | No option to name module before scan | GitHub |
| D-17 | Diogo Lopes | Inventory > Test case editor | Major | Consistency | "Create new module" only on non-default tab | GitHub |
| D-18 | Diogo Lopes | Inventory > Test case editor | Major | Feedback | "Run" CTA doesn't show partial selection scope | GitHub |
| D-19 | Diogo Lopes | Inventory > Test case editor | Major | Efficiency | Same-window run very slow | GitHub |
| D-20 | Diogo Lopes | Inventory > Test case editor | Minor | Help & guidance | Validation values not auto-added | GitHub |
| D-21 | Diogo Lopes | Runs > Test runs page | Major | Efficiency | Extremely slow cancel on failures | GitHub |
| D-22 | Diogo Lopes | Runs > Test runs page | Minor | Efficiency | Redundant "Stop immediately" checkbox | GitHub |
| D-23 | Diogo Lopes | Inventory > Test case editor | Major | Consistency | Standard objects vs user assets unclear | GitHub |
| D-24 | Diogo Lopes | Inventory > Test case editor | Minor | Consistency | Standard modules in user-assets search | GitHub |
| D-25 | Diogo Lopes | Inventory > Test case editor | Minor | Help & guidance | No visible "create new test case" in builder | GitHub |
| D-26 | Diogo Lopes | Runs > Playlist editor | Major | Efficiency | Only drag-and-drop to add tests; no "+" affordance | GitHub |
| D-27 | Diogo Lopes | Runs > Playlist editor | Major | Feedback | No loading state on save | GitHub |
| D-28 | Diogo Lopes | Runs > Playlist editor | Major | Efficiency | No autosave | GitHub |
| D-29 | Diogo Lopes | Runs > Playlist editor | Major | Language & clarity | "Test run" label confusing | GitHub |
| D-30 | Diogo Lopes | Runs > Playlist editor | Major | Feedback | Partial selection runs all test cases | GitHub |
| AM-01 | Ana-Maria Neaga | Workspace page (settings) | Minor | Efficiency | When creating workspace from homepage, redirected to all workspaces list; expects redirect to new workspace | Confluence |
| AM-02 | Ana-Maria Neaga | Homepage | Major | Help & guidance | Homepage highly misleading for new users; guides collapsed, empty dashboards dominate | Confluence |
| AM-03 | Ana-Maria Neaga | Create new + dialog | Major | Visual noise, Efficiency | Clicking "+" in menu shows too many options; overwhelming, unclear where to start | Confluence |
| AM-04 | Ana-Maria Neaga | XScan | Critical | Efficiency, Language & clarity, Help & guidance | Cannot figure out how to scan floating menus, dropdown controls, navigation; impossible without guides | Confluence |
| AM-05 | Ana-Maria Neaga | XScan | Major | Help & guidance, Control & freedom | Cannot find way to clear changes without saving or closing scan | Confluence |
| AM-06 | Ana-Maria Neaga | XScan | Major | Help & guidance, Control & freedom | Re-scanning confusing; XScan doesn't refresh; had to close and restart | Confluence |
| AM-07 | Ana-Maria Neaga | XScan | Critical | Help & guidance | Impossible to figure out how to scan drag and drop without documentation | Confluence |
| AM-08 | Ana-Maria Neaga | Create new + dialog | Minor | Efficiency | Triggering scan from Create new dialog doesn't navigate anywhere; expects redirect to modules list | Confluence |
| AM-09 | Ana-Maria Neaga | Module page | Minor | Visual noise | Buttons inconsistent with rest of app | Confluence |
| AM-10 | Ana-Maria Neaga | Module page | Minor | Control & freedom | No way to go back to modules list | Confluence |
| AM-11 | Ana-Maria Neaga | Module page | Cosmetic | Visual noise | Checkboxes not consistent with each other | Confluence |
| AM-12 | Ana-Maria Neaga | XScan + ARA | Critical | Efficiency | Very difficult to scan tables and automate table scenarios | Confluence |
| AM-13 | Ana-Maria Neaga | ARA | Minor | Help & guidance | Documentation link for help is broken | Confluence |
| AM-14 | Ana-Maria Neaga | XScan | Major | Error prevention | No warning that control is not unique or needs special handling; got identification errors on run | Confluence |
| AM-15 | Ana-Maria Neaga | Inventory (all) | Major | Efficiency | Working with inventory cumbersome without preview of object contents | Confluence |
| AM-16 | Ana-Maria Neaga | Inventory (all) | Minor | Efficiency | No way to see where a module is used from inventory | Confluence |
| AM-17 | Ana-Maria Neaga | Builder - Test cases | Minor | Efficiency | Active row concept doesn't work well with multi-select; context menu and toolbar skip only active row | Confluence |
| AM-18 | Ana-Maria Neaga | Builder - Test cases | Minor | Consistency | "View last run" detached from error around name; button hard to find | Confluence |
| AM-19 | Ana-Maria Neaga | Builder - Test cases / Runs | Minor | Consistency | Runs view detached from test case; wants tab inside test case to see runs | Confluence |
| AM-20 | Ana-Maria Neaga | Builder - Test cases | Minor | Feedback | Properties tab lacks proper zero state on no selection and selection with no properties | Confluence |
| AM-21 | Ana-Maria Neaga | Builder - Test cases | Minor | Efficiency, Control & freedom | No way to go back to list of test cases | Confluence |
| AM-22 | Ana-Maria Neaga | Runs page | Major | Feedback, Efficiency, Error prevention | Confusing error messages don't help debugging; e.g. "couldn't find tab" when issue was with buttons | Confluence |
