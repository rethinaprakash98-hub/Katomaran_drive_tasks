+-# Tichi Application — Signup & Login QA Workbook

This workbook contains the test case documentation and defect log for the
**Signup, Sign In, and Forgot Password** flows of the Tichi application.

**File:** `Final_QA_signup_and_Login_Page.xlsx`
**Tester:** Rethina Prakash
**Modules covered:** Sign Up, Sign In (Initial Page), Sign In (Password Page), Forgot Password

---

## Sheets in this workbook

### 1. Test Cases
The full test case log, plus a live summary dashboard at the bottom.

| Column | Description |
|---|---|
| Test Case ID | Unique ID, e.g. `TC001` |
| Module | Feature area (Signup, Login, Forgot Password) |
| Test Scenario | One-line description of what's being verified |
| Preconditions | State required before running the test |
| Test Steps | Numbered steps to execute |
| Test Data | Input values used |
| Expected Result | What should happen |
| Actual Result | What actually happened when run |
| Status | `Pass` / `Fail` / `Not Executed` |
| Page | Which of the 4 tracked sections the case belongs to (used by the summary formulas) |
| Case Type | `Positive`, `Negative`, `Edge`, or `UI` |

**Summary dashboard** (rows 41–48, below the test case list):
- Row 41 — overall `Total / Pass / Fail / Not Executed` count
- Rows 42–48 — a breakdown per section (Sign Up, Sign In Initial Page, Sign In
  Password Page, Forgot Password), showing case totals, the Positive/Negative/
  Edge/UI split, and Pass/Fail counts per section
- All of these are **live formulas** (`COUNTIF` / `COUNTIFS`) that reference the
  `Page`, `Case Type`, and `Status` columns — so if you add a new test case or
  change a status, the dashboard updates automatically. Just make sure any new
  row gets a `Page` and `Case Type` value, and that the formula ranges
  (currently `$6:$36`) are extended to cover new rows if you add cases beyond
  row 36.
- The **Average** cell shows the overall pass rate (Pass ÷ Total).

### 2. Defect Report
One row per confirmed defect, in a vertical "bug card" layout (label in
column A, value in column B): Bug ID, Title, Reported By, Date, Module, Test
Case, Environment, Severity, Priority, Status, Preconditions, Steps to
Reproduce, Expected Result, Actual Result, and Attachment notes.

To log a new defect, copy the block for an existing bug, update the `Bug ID`
(next sequential number), and fill in the details from the failing test case.

---

## How to use this workbook

1. **Running new tests:** add a row to *Test Cases*, fill in all columns
   including `Page` and `Case Type`, and set `Status` to `Pass`, `Fail`, or
   `Not Executed`. The summary dashboard recalculates automatically.
2. **Logging a defect:** for any `Fail`, add a new bug card in *Defect
   Report* referencing the failing `Test Case ID`.
3. **Reporting status:** the `Total / Pass / Fail / Not Executed` line and the
   per-section breakdown at the bottom of *Test Cases* are the quickest way to
   share current QA status.

## Notes / known gaps
- Severity and Priority on defect cards are judgment calls based on user
  impact — review before sharing externally.
- The Environment field uses placeholder values in some cards; confirm actual
  browser/OS versions before finalizing.
