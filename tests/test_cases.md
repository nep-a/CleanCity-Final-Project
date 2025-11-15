# Test Cases 
### Group Name: BUG BUNNISHERS
### PROJECT TITLE: CLEANCITY
### TEAM : 3 MEMBERS

#### TEST CASE 1: NON - FUNCTIONAL TESTING.
| **Test Case ID** | **Area**       | **Scenario**                                    | **Expected Result**                             | **Tool / Method**    |
| ---------------- | -------------- | ----------------------------------------------- | ----------------------------------------------- | -------------------- |
| TC-NF-001        | Performance    | Page loads under 3 seconds                      | Pages load smoothly                             | Chrome DevTools      |
| TC-NF-002        | Responsiveness | Layout adapts to mobile, tablet, and desktop    | No overflow or cut content                      | Browser resizing     |
| TC-NF-003        | Accessibility  | Verify contrast, alt text, focus indicators     | Screen reader and WCAG 2.1 guidelines satisfied | WAVE or Lighthouse   |
| TC-NF-004        | Security       | Verify no sensitive data stored in localStorage | Credentials removed after logout                | Manual + Code review |
| TC-NF-005        | Usability      | Navigation and labeling are intuitive           | All buttons clearly labeled                     | Manual testing       |


#### TEST CASE 2: Admin Functionality Test
| **Test Case ID** | **Feature**            | **Test Scenario / Description**                                  | **Test Steps**                                                                                  | **Expected Result**                                  | **Priority** | **Status** |
| ---------------- | ---------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------------------------- | ------------ | ---------- |
| TC-REQ-001       | View All Requests      | Verify that all submitted pickup requests appear in Admin panel. | 1. Login as admin.<br>2. Go to Admin Page.<br>3. Observe “All Requests” table.                  | All submitted requests display with correct columns. | High         | Passed     |
| TC-REQ-002       | Approve/Reject/Modify  | Verify that admin can update request status.                     | 1. Select request from dropdown.<br>2. Choose status.<br>3. Click “Update Status.”              | Request status updates in table and dashboard.       | High         | Passed     |
| TC-REQ-003       | Assign Dates/Times     | Verify that request modification includes scheduling.            | 1. Select request.<br>2. Change status to “Scheduled.”<br>3. Confirm date/time field populated. | Assigned schedule visible to user dashboard.         | Medium       | Pending    |
| TC-REQ-004       | Filter/Search Requests | Verify that admin can filter requests by status or location.     | 1. Use filter dropdowns.<br>2. Select “Completed” or “Nairobi.”                                 | Table filters correctly to matching requests.        | High         | Passed     |
| TC-USR-001       | View All Users   | Verify that admin can see all registered users.   | 1. Login as admin.<br>2. Open Admin page.<br>3. Navigate to User Management (future). | User table displays all user data.            | Medium       | Future     |
| TC-USR-002       | Change Roles     | Verify admin can promote user to admin role.      | 1. Select user.<br>2. Change role.<br>3. Save changes.                                | User sees new access on login.                | High         | Future     |
| TC-USR-003       | Suspend/Delete   | Verify admin can disable or delete user accounts. | 1. Select user.<br>2. Click Suspend/Delete.<br>3. Confirm action.                     | User cannot log in after deletion/suspension. | High         | Future     |
| TC-USR-004       | Activity Reports | Verify admin can generate user activity report.   | 1. Click “Generate Report.”                                                           | Detailed report is displayed.     | Low          | Future     |
| TC-MOD-001       | Moderate Posts             | Verify admin can hide or delete community content. | 1. Login as admin.<br>2. Navigate to moderation panel.<br>3. Click “Delete” on post. | Post is removed from all user views.             | Medium       | Future     |
| TC-MOD-002       | Flag Inappropriate Content | Verify users can report posts.                     | 1. Click “Flag” on post.<br>2. Submit report.                                        | Admin receives flagged post in moderation queue. | Medium       | Future     |
| TC-MOD-003       | Announcements              | Verify admin can create announcements.             | 1. Navigate to Admin panel.<br>2. Click “Create Announcement.”<br>3. Save message.   | Announcement visible on dashboard or homepage.   | Medium       | Future     |



#### TEST CASE 3: Community Features
-------------------- | :-------------- |
| TC_3-001|logged-in user can create a community post successfully | 1. Log in with valid credentials.2. click Community page.3. Clickcreate post.4. Enter a valid title and content.<br>5. Click Submit. | Post should appear immediately in the community   | Pass | High     |  Chrome | 70%  |
|TC_3-002|  comment on community posts   | 1. Log in 2. Open an existing post.3. Type a comment and  Submit | comment appears instantly under the post with correct user info. |pass | high  |  Chrome | 10%             |
|TC_3-003 |  non-logged-in users cannot comment on posts| 1. Log out of the app.2. click Community page.3. Attempt to  comment. | The system should prevent posting |fail| High |  Chrome | 20%             |
|TC_3-004 | can delete their own post  | 1. Log in. 2. Go to your post.3. Click Delete . | Post is removed from feed and no longer visible to others.| Fail | High   |  Chrome| 25%             |
| TC_3-005 | cannot submit an empty post  | 1. Log in.<br>2. Click Post.<br>3. Leave the fields blank and click Submit  |display an error message like Post content cannot be empty. |fail | Medium   |  Chrome| 10%             |
|TC_3-006 | image uploads   does not function correctly       | 1. Log in.2. Create a post with an image file PNG.3  Submit.| Image does not upload successfully and display in the post preview. |Fail | Medium  Chrome| 15%             |
|TC_3-007 special characters render correctly in posts	1. Log in.2. Create a post with special characters  and emoji.3. Submit and view.	Emojis and symbols display correctly without layout issues.	|Pass|	Low	| Chrome	5%
|TC_3-008 | Editing of post   | 1. Log in.2. Go to your existing post.<br>3. Click edit Post, modify the text, and save. | Changes should be reflected immediately with updated.  | fail | High     |  Chrome| 15%             |

#### TEST CASE 4: Content management Testing

| TC ID    | Feature            | Test Case Description                                | Precondition         | Steps                                                                          | Expected Result                             | Priority | Status |
| -------- | ------------------ | ---------------------------------------------------- | -------------------- | ------------------------------------------------------------------------------ | ------------------------------------------- | -------- | ------ |
| TC_CM_01 | Blog System        | Verify admin can create, edit, and delete blog posts | Admin logged in      | 1. Go to Blog Admin 2. Click “Create Post” 3. Add title, content, tags 4. Save | Post is created and visible in list         | High     | Draft  |
| TC_CM_02 | Blog System        | Verify users can view and interact (like/comment)    | User logged in       | 1. Open blog 2. Like a post 3. Comment                                         | Like and comment appear immediately         | High     | Draft  |
| TC_CM_03 | Blog System        | Verify blog categories/tags filter correctly         | Blog posts exist     | 1. Select “Recycling” tag                                                      | Shows only related posts                    | Medium   | Draft  |
| TC_CM_04 | Awareness Section  | Verify eco tips rotate every 5 seconds               | Page loaded          | Wait for 15 seconds                                                            | 3 different eco tips display sequentially   | Medium   | Draft  |
| TC_CM_05 | Awareness Section  | Verify quizzes load and submit                       | Quiz page accessible | 1. Start quiz 2. Answer all questions 3. Submit                                | Shows score and explanations                | High     | Draft  |
| TC_CM_06 | Awareness Section  | Verify infographics display correctly                | Page loaded          | 1. Scroll down 2. Observe graphics                                             | Infographics visible with correct data      | Medium   | Draft  |
| TC_CM_07 | Community Feed     | Verify users can create posts                        | User logged in       | 1. Go to Community Feed 2. Create post                                         | Post appears in feed                        | High     | Draft  |
| TC_CM_08 | Community Feed     | Verify likes/comments work                           | Post exists          | 1. Like and comment 2. Refresh                                                 | Likes/comments persist                      | High     | Draft  |
| TC_CM_09 | Community Feed     | Verify feed shows latest posts first                 | Multiple posts exist | Reload page                                                                    | Posts appear in reverse chronological order | Medium   | Draft  |
| TC_CM_10 | Community Feed     |Verify users can share tips and experiences via posts.                 | User logged in | 1. Create post with tip/experience. 2. Submit post.                                                         | Post is displayed under community section with visible content. | Medium   | Draft  |
| TC_CM_11 | Media Upload       | Verify user can upload images/videos                 | Post creation page   | 1. Upload media 2. Save                                                        | Upload successful and preview visible       | Medium   | Draft  |
| TC_CM_12 | Content Visibility | Verify only published content visible to public      | Admin logged in      | 1. Create draft post 2. View as user                                           | Draft not visible                           | High     | Draft  |


| TC ID | Test Description (Summary) | Priority | Risk |
| :--- | :--- | :--- | :--- |
| **Data Accuracy** | | | |
| `TC-CC-039` | Verify "New Reports Today" KPI widget shows correct count | **High** | **High** |
| `TC-CC-040` | Verify "Reports by Status" pie chart shows correct data segmentation | **High** | **High** |
| `TC-CC-045` | Verify "Reports by Type" bar chart shows correct data segmentation | **High** | **High** |
| `TC-CC-046` | Verify "Total Reports" KPI widget shows the correct all-time count | **High** | Medium |
| `TC-CC-044` | [E2E] Verify dashboard accuracy, refresh, and filtering in one flow | **High** | **High** |
| **Interactivity & Filtering** | | | |
| `TC-CC-041` | Verify "Date Range" filter correctly updates all dashboard widgets | **High** | Medium |
| `TC-CC-047` | Verify "Waste Type" filter (if any) correctly updates all charts | Medium | Medium |
| `TC-CC-048` | Verify "Location/Area" filter (if any) correctly updates all charts | Medium | Medium |
| `TC-CC-049` | Verify clicking on a chart segment (e.g., "New" slice) filters the report list | Medium | Low |
| **Dynamic Refresh & State** | | | |
| `TC-CC-007` | Verify dashboard data refreshes after a new report is submitted (on page reload) | **High** | Medium |
| `TC-CC-043` | Verify dashboard displays a "No Data" message when no reports exist (Empty State) | Low | Low |
| `TC-CC-050` | Verify widgets show "0" and not an error when data exists but is zero for the filter | Low | Low |
| **Usability & Performance** | | | |
| `TC-CC-051` | Verify dashboard links (e.g., "View All Reports") navigate to the correct page | Medium | Low |
| `TC-CC-052` | Verify dashboard widgets are responsive and display correctly on mobile screens | Medium | Low |
| `TC-CC-053` | Verify dashboard page load time is under 3 seconds (with 1,000+ reports) | Medium | Medium |
#### TEST CASE 6: WASTE MANAGEMENT
| TC ID | Test Description | Test Steps | Expected Result | Status |Priority|Environment|Risk percentage
| TC_6-001 | user can schedule a waste pickup successfully | 1. login.2. click Schedule Pickup section.<br>3. Enter required details location, type of waste.4. Click Submit Request. | Pickup request is submitted successfully and a confirmation message is displayed. | Pass | High     | chrome | 30%   |
|TC_6-002 |system validates empty fields  | 1.login  Schedule Pickup page.<br>2. Leave all mandatory fields empty.3. Click Submit.| error messages appear indicating required fields. | Pass | Medium  |chrome  | 20%   |
|TC_6-003 | Verify that a user can view their scheduled pickups   | 1. Log in 2. Navigate to My Pickups .<br>3. Check the displayed list.  | User sees accurate list of scheduled or completed pickups. | Fail |Low  |chrome | 10%   |
| TC_6-004 |  special characters in waste description  | 1. Go to Schedule Pickup.2. Enter special characters in description 3. Submit the request.| System accepts   | Pass | Medium   |chrome    | 15% |
|TC_6-005| location works properly | 1. go to Schedule Pickup.2. Click on location .3. Select a valid location. | Selected location is captured and displayed correctly in the form.  |pass | High |chrome     | 25%  |
TC_6-006| duplicate waste reports for same location	1. Log in.2. Submit a waste report for a specific location.3. Try submitting another report for the same location immediately.	System should prompt A report already exists for this location.|Fail	|High	|Chrome	20%
TC_6-007|notifications when waste status changes	1. Log in as admin and update a report’s status.2. Log in as the reporting user.3. Check Notifications.	User receives a notification indicating the change in waste report status.|Fail	|Medium	|Chrome	15%


#### TEST CASE 7: Authentication
| TC ID | Test Description | Test Steps | Expected Result | Status |Priority|Environment|Risk percentage|
| :--- | :--- | :--- | :--- | :--- | :---| :---|:---
| TC_7-001 | User Registration | 1.Click register button<br>2. Enter Details<br>3.Click Submit | To register a user and return a successful message. | Pass |High|Chrome|89
| TC_7-002 | User Log in | 1. click login<br>2. Enter email and password<br>3. Submit correct email and password | To log in successfully and user to seea dashbord | Pass |High|Chrome|88
| TC_7-003 | password Validation | 1. Enter all details<br>2. Submit the details<br> | User to confirm a password | Fail |High|Chrome
| TC_7-004 | session management | 1. Enter all details<br>2. Submit the details<br> | user to be kept logged in |pass |High|Chrome|77
| TC_7-005 | security | 1. Enter all details<br>2. Submit the details<br> | Verify user is not kept logged in if "Remember Me" is unchecked |Fail |High|Chrome|75
| TC_7-006 | Role-Based Access Control (RBAC) | 1. Enter all details<br>2. Submit the details<br> | Verify a User role cannot access the Admin Dashboard URL |Fail |High|Chrome|80
| TC_7-007 | Verify an Admin role can access the Admin Dashboard and sees all admin tools | 1. Enter all details<br>2. Submit the details<br> | Verify a User role cannot access the Admin Dashboard URL |Fail |High||70