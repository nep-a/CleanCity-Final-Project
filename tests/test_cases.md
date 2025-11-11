# Test Cases 
### Group Name: BUG BUNNISHERS
### PROJECT TITLE: CLEANCITY
### TEAM : 3 MEMBERS

#### TEST CASE 1: NON - FUNCTIONAL TESTING.
| TC ID | Test Description | Test Steps | Expected Result | Status |Priority|Environment|Risk percentage|
| :--- | :--- | :--- | :--- | :--- | :---| :---|:---
| TC_1-001 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |
| TC_1-002 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |
| TC_1-003 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |

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
| TC-USR-004       | Activity Reports | Verify admin can generate user activity report.   | 1. Click “Generate Report.”                                                           | System exports or displays usage summary.     | Low          | Future     |
| TC-MOD-001       | Moderate Posts             | Verify admin can hide or delete community content. | 1. Login as admin.<br>2. Navigate to moderation panel.<br>3. Click “Delete” on post. | Post is removed from all user views.             | Medium       | Future     |
| TC-MOD-002       | Flag Inappropriate Content | Verify users can report posts.                     | 1. Click “Flag” on post.<br>2. Submit report.                                        | Admin receives flagged post in moderation queue. | Medium       | Future     |
| TC-MOD-003       | Announcements              | Verify admin can create announcements.             | 1. Navigate to Admin panel.<br>2. Click “Create Announcement.”<br>3. Save message.   | Announcement visible on dashboard or homepage.   | Medium       | Future     |



#### TEST CASE 3: Community Features
| TC ID | Test Description | Test Steps | Expected Result | Status |Priority|Environment|Risk percentage|
| :--- | :--- | :--- | :--- | :--- | :---| :---|:---
| TC_3-001 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |
| TC_3-002 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |
| TC_3-003 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |

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
| TC_CM_10 | Media Upload       | Verify user can upload images/videos                 | Post creation page   | 1. Upload media 2. Save                                                        | Upload successful and preview visible       | Medium   | Draft  |
| TC_CM_11 | Content Visibility | Verify only published content visible to public      | Admin logged in      | 1. Create draft post 2. View as user                                           | Draft not visible                           | High     | Draft  |


#### TEST CASE 5: Dasboard and Analytics
| TC ID | Test Description | Test Steps | Expected Result | Status |Priority|Environment|Risk percentage|
| :--- | :--- | :--- | :--- | :--- | :---| :---|:---
| TC_5-001 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |
| TC_5-002 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |
| TC_5-003 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |

#### TEST CASE 6: WASTE MANAGEMENT
| TC ID | Test Description | Test Steps | Expected Result | Status |Priority|Environment|Risk percentage|
| :--- | :--- | :--- | :--- | :--- | :---| :---|:---
| TC_6-001 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail |Environment|
| TC_6-002 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail | Environment|
| TC_6-003 | [Test objective] | 1. [Step 1]<br>2. [Step 2]<br>3. [Step 3] | [Expected behavior] | Pass/Fail | Environment|

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