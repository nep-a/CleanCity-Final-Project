# 🧾 CleanCity Test Report

**Date:** [18/11/2025]  
**Phase 3:** Test Design & Early Execution   

---

## Project Overview
The Clean City Project is a web-based sustainability platform enabling citizens to report waste, view cleanup events, and volunteer for environmental causes. The system includes a user interface, forms, event listings, and an admin dashboard.

---
## Purpose & Scope
This document explains how we will test the CleanCity waste pickup scheduling system. Our goal is to make sure users can:
-	Submit pickup requests
-	Register/log in
-	Track recycling status
-	Give feedback
-	View awareness information
-	Admins can update request statuses
- We’ll test the app manually and with automated React tests to confirm it works smoothly, looks right on multiple devices, and stores data properly.
## Scope
## (In-scope):
-	Home Page: pickup request form and validation 
-	User Registration & Login 
-	Dashboard: listing, filtering, and status display  
-	Feedback page submission, and request ID validation  
-	Awareness page: content and accessibility checks 
-	Admin panel: update statuses, UI state, persistence via localStorage 
-	Responsive layout on desktop and mobile viewports 
-	Automated unit/integration tests with React Testing Library 
## Out-of-scope:
-	Backend API tests  
-	Advanced Security penetration testing 
-	Performance load testing    
## Test Objectives
We need to verify all functional requirements (submit requests, view requests, filter, update status). Validate form inputs and error messages. Confirm data persistence. Check accessibility Ensure UI responds on different screen sizes (mobile, tablet, desktop). Execute automated test suite and verify passing tests for key flows.
## Test Approach & Strategy
## Strategies used:
-	Manual Exploratory & Scripted Testing: Execute explicit test cases for forms, filtering, admin actions, and feedback.
-	Boundary Testing: Inputs with very long strings, invalid dates, missing required fields.
-	Accessibility Checks: Manual screen reader checks, keyboard navigation, and Lighthouse a11y audits.
-	Automated Tests: Use React Testing Library to validate core component logic and form validation behavior.
-	Data Persistence Checks: Use browser devtools to inspect localStorage after actions.
## Test Types:
-	Functional tests (positive/negative)
- Usability & Accessibility tests
- Responsive tests
-	Regression tests after bug fixes
-	Automated unit/integration tests 
## Environments:
-	Development: localhost:3000 (React dev server)
-	Browser targets: Chrome, Firefox, Edge, and Safari; ensuring desktop and mobile simulation
-	Node.js
## Entry & Exit Criteria
Entry Criteria:
•	Application starts successfully.
•	Test data seeded / sample requests present (REQ001–REQ005).
•	Test environment (browsers) available.
•	Test plan approved.
Exit Criteria:
•	All P0 and P1 test cases executed and passed OR have approved mitigations / accepted risks.
•	All P0 defects fixed and re-tested.
•	Test summary report completed and signed off by Test Manager.
## Test Deliverables
-	Test Plan 
-	Test Cases & Execution Results 
-	Bug report 
-	Test Summary Report
-	Automated test reports

## Test Schedule
-	Day 1: Setup + smoke tests (install/run)
-	Day 2: Manual functional tests — Home & forms
-	Day 3: Manual tests — Dashboard, filtering, feedback
-	Day 4: Admin panel & persistence testing; exploratory
-	Day 5: Accessibility & responsive testing; automated test runs
-	Day 6: Regression re-test & summary report
## Risk & Mitigation
Risk	Impact	Likelihood	Mitigation
Form validation failures (intentional bug)	High (affects core functionality)	High	Log as P0; create ticket and re-test after fix.
localStorage not updating UI	Medium	Medium	Reproduce steps, capture devtools logs, create issue; consider forced re-render as temp fix.
Missing alt-text in Awareness images	Medium (accessibility)	High	Add alt attributes; add to acceptance criteria.
Cross-browser layout differences	Low–Medium	Medium	Test in target browsers; adjust CSS breakpoints.

## Test Data
Sample Requests (seeded):
•	REQ001 — John Doe — Nairobi — General — Preferred: 2025-11-06 — Status: Pending
•	REQ002 — Jane Smith — Kisumu — Recyclable — Status: Scheduled
•	REQ003 — Mike Johnson — Mombasa — Hazardous — Status: Completed
•	REQ004 — Sarah Wilson — Eldoret — General — Status: Missed
•	REQ005 — David Brown — Nairobi — Recyclable — Status: Pending
User accounts (demo):
•	Regular user: user@cleancity.com / password123
•	Admin user: admin@cleancity.com / admin123
## Traceability Matrix (Features → Test Cases)
Feature	Test Case IDs
Submit pickup request	TC-001, TC-002, TC-003
Filter by location	TC-010, TC-011
Lightbox / images (awareness)	TC-020
Feedback submission & RequestID validation	TC-030, TC-031
Admin status update	TC-040, TC-041
LocalStorage persistence	TC-050
Accessibility (alt text, labels)	TC-060, TC-061
Boundary test (long inputs)	TC-070

## Test Cases (Key / Required)
Below are sample test cases. Status column is to be filled after execution.
TC-001 — Submit valid pickup request (positive)
•	Feature: Request Waste Pickup (Home)
•	Precondition: App open at Home page; logged-in as user (or guest if allowed)
•	Steps:
1.	Navigate to Home → Request Waste Pickup form.
2.	Fill "Full Name" = "Alice Tester".
3.	Select Location = "Nairobi".
4.	Select Waste Type = "Recyclable".
5.	Optional: choose preferredDate = (tomorrow).
6.	Click Submit Request.
•	Expected Result: Success message displayed (success-message) and new request added to Dashboard with a new Request ID (REQxxx). localStorage updated with the request.
•	Priority: P0
•	Status: (Pass/Fail)
TC-002 — Submit with missing required fields (negative)
•	Feature: Form Validation
•	Steps:
1.	Leave "Full Name" empty.
2.	Click Submit Request.
•	Expected Result: Validation error displayed in name-error element; request is not accepted. (Note known bug: date field may not show validation.)
•	Priority: P0
TC-003 — Date validation bug check (intentional)
•	Feature: Date validation
•	Steps:
1.	In form, leave other required fields valid but input invalid past date or empty date if the requirement expects a date — exercise the known bug.
•	Expected Result: According to spec, date is optional, but known bug: "date field doesn't show validation error" — log behavior as observed.
•	Priority: P1
TC-010 — Filter by location (Eldoret)
•	Feature: Dashboard filtering
•	Steps:
1.	Go to Dashboard.
2.	Set locationFilter to "Eldoret".
•	Expected Result: Only requests with Location = Eldoret are displayed. (Known bug: currently shows Nairobi; log if reproduced.)
•	Priority: P0
TC-020 — Awareness images accessibility
•	Feature: Awareness page images
•	Steps:
1.	Open Awareness page.
2.	Inspect images for alt attribute.
3.	Use a screen reader or Lighthouse to check image accessibility.
•	Expected Result: Each image has an appropriate alt attribute. (Known bug: Missing alt-text on images.)
•	Priority: P1
TC-030 — Feedback: invalid Request ID
•	Feature: Feedback form
•	Steps:
1.	Enter requestId = "REQ999" (non-existent).
2.	Select reason and submit.
•	Expected Result: Validation error requestId-error shown indicating invalid request ID.
•	Priority: P1
TC-040 — Admin: mark as Scheduled and UI update
•	Feature: Admin status updates
•	Steps:
1.	Login as admin.
2.	Navigate to Admin → select REQ001 → choose "Scheduled" → click Update.
•	Expected Result: Request status updates in admin table and dashboard; localStorage updated; UI refreshes immediately. (Known bug: UI doesn't refresh.)
•	Priority: P0
TC-050 — LocalStorage persistence
•	Feature: Data persistence
•	Steps:
1.	Submit a request.
2.	Open devtools → Application → localStorage → verify new entry.
3.	Reload page and check request still listed.
•	Expected Result: data persisted across reloads.
•	Priority: P1
TC-070 — Boundary testing: very long input
•	Feature: Boundary testing
•	Steps:
1.	In Full Name, enter 5,000 characters.
2.	Submit the form.
•	Expected Result: Application handles gracefully — truncated or rejected with a validation message; layout not broken. If layout breaks, record as bug.
•	Priority: P2
## Automated Tests
Recommended automated tests to implement with React Testing Library:
•	Render pickup form and assert required fields and error messages (TC-001, TC-002).
•	Simulate filter controls on dashboard and assert filtered output (TC-010).
•	Test admin status update function updates storage and returns expected data (TC-040).
•	Snapshot tests for major components (home, dashboard, admin) to catch UI regressions.
Example Jest test skeleton:
// sample: PickupForm.test.js
import { render, screen, fireEvent } from '@testing-library/react';
import PickupForm from '../PickupForm';

test('shows error when full name is empty', () => {
  render(<PickupForm />);
  fireEvent.click(screen.getByText(/Submit Request/i));
  expect(screen.getByText(/required/i)).toBeInTheDocument();
});
Run with: npm test
## Defect Reporting & Management
Tool: Use GitHub Issues and Jira. Each defect should include:
•	Title (clear short summary)
•	Description (steps to reproduce, expected vs actual)
•	Environment (browser, OS, app version)
•	Severity (P0/P1/P2)
•	Attachments (screenshots, console logs)
•	Assignee & label (bug/UX/accessibility)
Severity Definitions:
•	P0 (Critical): Core functionality broken (submit request fails, filter returns wrong dataset). Blocker for release.
•	P1 (High): Important features affected or major UX problems (missing alt text, persistence issues).
•	P2 (Medium): Nice-to-have fixes or cosmetic issues (layout quirks).
•	P3 (Low): Low impact, suggestions.
________________________________________
## Test Metrics & Reporting
Metrics to gather:
•	Number of test cases executed / passed / failed
•	Number of defects opened / closed (by severity)
•	Test coverage reported by Jest (if configured)
•	Accessibility score from Lighthouse
Test Status Reporting:
•	Daily standup summary (what tested, top issues)
•	End-of-cycle test summary with pass rate, major defects, and recommendations
## Sign-off Criteria
Project is ready for sign-off when:
•	All P0 defects resolved and verified.
•	90%+ of planned test cases executed.
•	Test summary and defect list provided to stakeholders.
Team Roles (3 teammates)
Role	Responsibilities		Deliverables
Test Manager	  Plan, coordinate, finalize  report		Updated Test Plan, daily status reports, final Test Summary.
Risk Analyst	  Identify,log & monitor risks		Risk register, impact analysis, mitigation recommendations.

Test Executor	    Run tests & report bugs		Test execution evidence (screenshots, logs), defect tickets, test case status updates.
## Communication Plan
## Primary Channels:
-	Jira / Google Meet / WhatsApp: real-time collaboration & quick questions 
-	Issues: defect tracking and detailed bug reports.
-	Email: official sign-offs / final report submission.
-	Google Drive / Repo: share test artifacts (test case spreadsheets, screenshots).

## Escalation Path:
1.	Test Executor → Test Manager (for issues that block test progress)
2.	Test Manager → Instructor / Stakeholder (for unresolved issues)
Templates:
-	Completed: Executed test cases 
-	In progress: Accessibility checks 
-	Blocker: Unable to reproduce admin UI refresh bug on Chrome
-	Environment: Chrome 118 on Windows 10
-	Attachments: screenshot.png
-	Assignee: @member
## Quick Checklist Before Execution
• Confirm the project runs locally with npm start.
• Verify seed data (REQ001–REQ005) present.
• Create repository folder for test artifacts.
• Prepare test cases in a spreadsheet or Markdown for execution tracking.
• Create Issues


---
## Test Approach
- **Testing Type:** Manual Functional Testing  
- **Environment:** Chrome v120 on Windows 10  
- **Method:** Exploratory and scenario-based  
- **Focus Areas:** Form validation, navigation, authentication, and layout consistency

---


## Key Defects Summary
- Event filtering not functional.
- Minor alignment issues on small screens.
- Missing profile edit feature.
- Missing accessibility attributes.

---

## Risks & Recommendations
### Risks:
- Missing validation may allow incomplete data submission.
- Poor mobile optimization can affect usability.

### Recommendations:
- Implement backend validation.
- Improve mobile CSS layout.
- Add “Profile Edit” and event filtering.
- Conduct accessibility testing (WCAG 2.1).

---

## Conclusion
Overall, the Clean City Project performs well functionally with strong user experience and stability. Most modules are fully operational. Minor UX and responsive issues can be addressed in future iterations.


**Test Manager:** _MERCY CHEBET____________  
**Approved By:** __HORACE WITABA, EMILY AWUOR_____________  
**Date:** ___13/11/2025________________


