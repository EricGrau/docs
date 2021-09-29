# What's New in the TMS

<span style="font-size:90%;"> <a href="/whats-new-toc.md">What's New in our other platforms?</a> 
## <u>Released September 27, 2021</u>
### Accessibility Items
*   In our continuing effort to improve accessibility for all our students and meet MAS standards we have implemented the following features:
    * Keyboard focus returns back to the ‘Displays Times in’ control after selecting the value for the combo box present in the ‘Output Options menu control.
    *   Keyboard focus returns to the ‘Edit’ control after pressing enter on ‘Save or Cancel’ controls present in the ‘Open’ saved search dialog. 
    *   Keyboard focus will now move to the ‘Privacy Policy’ link and move to the ‘Close (X)’ button.
    *   Tab Focus order is now logical while navigating on the page for Print, Export and Results/Page.
    *   When the Keyboard Tab focus is on the ‘Close (X)’ button and after pressing Tab key the focus will now move to the first list checkbox in the ‘Output Options’ list.
    *   Keyboard focus within the Filters area will move to the next interactive element after invoking ‘filter remove (x) button’.
    *   Tab Focus will now remain on the Output Options list when the ‘Close (X)’ button is pressed. 
    *   Tab Focus will now remain within the Open Saved Search dialog box when pressing ‘This is my default search’ checkbox.
    *   Keyboard Focus will only go to static text present in the ‘Description’ tab on the Course Assignment page.
    *   From a Simple Course Assignment, the keyboard tab order will go to Bookmark, Table of Contents and Description.
    *   From a student’s Current Training Page, the ‘Actions’ column header will be provided on ‘Bookmarks’ table.
    *   From the Course Catalog page, the ‘Open Saved Search’ dialog box Edit link label will be provided.
    *   From a Simple Course Assignment, the left/right arrow keys will navigate to the ‘Table of Contents’ and ‘Description’.
    *   From the Current Training page, screen reader will narrate ‘Bookmarks’, while navigating using the table shortcut key (T).
    *   From the TMS Home page, screen reader will narrate the user’s menu dropdown in Expand/Collapse state.
    *   From the Sign In page, screen reader will navigate main content using ‘Skip to navigation’ while in scan mode. 
    *   ‘LinkedIn’ and ‘Twitter’ URL meet minimum Luminosity ration greater than 4.5.1.
    *   From the Sign In page, if the ‘Username’ is not provided, screen reader will narrate ‘Please Enter the text in Email Format’.
    *   From the Edit User profile page, screen reader will narrate the First/Last Name, Primary E-mail address and Username.
    *   From a Simple Course Assignment page, an ARIA attribute aria-selected=true will not be used for the ‘Bookmark’ button. 
    *	Screen reader will no longer narrate the ‘Organization Belongs to’ filter twice on Find Courses page.
    *	From the Course Catalog page, screen reader will identify the table which is present in the ‘Open Save Search’ dialog using table short cut key (T).

### Enhancements and Fixes
*   Class Vouchers:  We have fixed an issue with the Course ‘Class Absolute Maximum Capacity’ and the ‘Override Organization Owned Max Capacity’ fields. An Operations Manager was able to exceed the ‘Class Absolute Maximum Capacity’ by clicking the ‘Add Class Voucher’ link on the class Roster page. Now, when the ‘Class Absolute Maximum Capacity’ has been met the following message appears if additional vouchers are requested.
    
    ' You Cannot have more than (X) students in this event.'

*   Publishing Groups: We have fixed an issue with Publishing Groups and Courses added to a Subscription.  When an Operation Manager created a course without a Publishing Group, it allowed them to assign a Subscription Profile for that course and create a Course Assignment from the Subscription.  A user was able to select a course from the assigned Subscription and launch the labs.   
 
    Now, if a Course does not have a Publishing Group and a Subscription Profile is added the following message will appear when the Course is Saved.  

    'The subscription profile 'Profile Name' is not valid because the course is not available to *Organization Name'
*   Translation - files Update:   We have updated the language files in TMS for   the following supported languages:  
    *   Chinese (Simplified) 
    *   German 
    *   Japanese 
    *   Korean 
    *   Portuguese 
    *   Spanish 

*   Certificate of Completion – Preview: We have fixed an issue with an Application Error occurring when previewing the certificate without any data.
*   Instructor Schedule Page: We have fixed an issue with the Instructor and Instructor Name Column not being aligned and the ‘More Than’ was removed from the ‘Schedule Timeframe’ filter.

----------------------------
## <u>Released August 30, 2021</u>
   
### Accessibility Items
In our continuing effort to improve accessibility for all our students and meet MAS standards we have implemented the following features:
*   Luminosity ratio for the focus indicator is greater than or equal to the minimum contrast ratio 3:1 for the ‘Close my Account’ control. 
*   Keyboard focus will not move to the non-interactive elements in ‘Login Assistance’ page while navigating through keyboard tab.
*   Keyboard focus will stay on the first interactive element Close (X) button once the ‘How would you like to sign in?’ dialog is opened while navigating through keyboard tab.
*   Keyboard focus will restore back on the ‘Learn on Demand Systems Account’ control after invoking the ‘Cancel’ button in the ‘How would you like to sign in?' dialog.
*   Screen reader focus will move to the first error field ‘Username’ after invoking ‘Sign in” button without filing mandatory fields on the page, when navigating using NVDA browse mode. 

### Enhancements and Fixes
*   Cloud Platform – AWS:  We have fixed the Cloud Platform filter dropdown to include AWS on the Find Labs page.
*   All Virtual Class Launches: When a student with an Enrollment Status of Enrolled launches a virtual class the Completion status will automatically be marked as Attending.
*   API Course Assignment – API Create Against Subscription: We have updated the Create and Update Course Assignment API end points to properly associate subscriptions memberships when provided.
*   Publishing Groups: We have fixed an issue with Publishing Groups allowing an Operations Manager to set the Organization running a class to an organization they manage that doesn’t have availability to the course.  If the course is selected during the class creation process, the following message will occur when the Save button is clicked. 

    'Organization Name does not have access to deliver Course Name, please select another delivery organization.'

    Previously, when creating a class using an Organization in the Publishing Group with a course from the Publishing Group, the Operations Manager could then change the organization to one they manage that is outside of that Publishing Group. Now, the following message will occur when a valid Organization is selected and then changed to an Organization outside of the Publishing Group.

    'The selected organization does not have access to deliver the selected course. Please choose another organization.'

    If the OK button is clicked, the following message will occur when saving.

    'Organization Name does not have access to deliver Course Name, please select another delivery organization.'
 
----------------------------
## <u>Released July 7, 2021</u>
### Accessibility Items
In our continuing effort to improve accessibility for all our students and meet MAS standards:
*   Resizing the page at 400% zoom will now act according to accessibility standards.

### Enhancements and Fixes
*   Classroom Maximum Capacity - Error on Roster: We have fixed an issue on the class roster where users received the error message below when changing the Enrollment Status to Enrolled.

   ‘This enrollment would cause the selected classroom to exceed maximum occupancy.’  

*   Translation - files Update:   We have updated the language files in TMS for the following supported languages:  
    * Chinese (Simplified) 
    * German 
    * Japanese 
    * Korean 
    * Portuguese 
    * Spanish 
*   Create / Edit Subscription Membership:  We have fixed an issue with the Expires date field not calculating the correct Start Date format when is not MM/DD/YYYY.

----------------------------
## <u>Released May 24, 2021</u>
### Accessibility Items
In our continuing effort to improve accessibility for all our students and meet MAS standards we have updated the Course Catalog page:
*	On the ‘Course Catalog’ page, at 200% zoom mode, the user profile menu and notification icon no longer disappear.

### Enhancements and Fixes
* Lab Activities - Status and Scoring Fields: On the Organization Preference tab, we have added a ‘Show Activity Status and Score on activities listings’ checkbox for Course Assignment / Class Enrollment. This will allow an organization to hide the Status and Score fields for all lab activities and the feature will be enabled by default.
* API – SearchClubs: We have fixed the API results from listing archived courses.
* Disabled Organization Text: On the Organization profile page, ‘Temporarily’ is removed from the text for disabled organizations.
* Notification Replacement Text - [ClassStartTimeLocal] and [ClassEndTimeLocal]:  We have fixed an issue with the replacement text values of [ClassStartTimeLocal] and [ClassEndTimeLocal] from inheriting the browser language setting when a notification is triggered by the UI.
* Course Assignments – Activities Complete: Completed required lab activities within sections now calculates the correct percentage.  
----------------------------
## <u>Released May 6, 2021</u>

### Simple Course Assignments
On a simple course assignment when a student clicks the ‘Start’ button and completes a lab activity the ‘Start’ button now changes to ‘Continue’ and moves to the next lab activity that has a Status of ‘Not Started’ or ‘Incomplete’. 

### Product Guides
Product guides have been added to the TMS for the following topics. These product guides may not be available to you, depending on your user account permissions.

- Create a user
- Create a course

### Enhancements and Fixes
*   UpdateUserCustomFieldValue:  We have added a new API call for UpdateUserCustomFieldValue.  This updates the current value of a specific custom field for a user. 
*   Class – Payment Section: The ‘Payment’ section on Create or Edit a class has been removed. 
*   SearchClubMemberships & SearchSubscriptions:  We have fixed the API documentation for SearchClubMemvberships and SearchSubscriptions.  An extra ‘s’ in ‘Subscriptions’ is removed from the Example Usage URL for version 2.0.
*   User Profile – Change Password:  The ‘Change Password’ dialog box has been fixed so that when a user clicks on the ‘Show Characters’ checkbox it no longer applies encoding onto the password characters.

----------------------------
<!-->
## <u>Released April 22, 2021</u>

### Training Key Pool Availability

An Organization can now make a ‘Training Key Pool’ available to use across any child within the Parent Organization. On the Create Training Key Pool page, we have added a checkbox called ‘Make these keys available to everyone using’ [Site Name and URL]. Displaying the name of the site that the owning organization belongs to and displays the site URL. This option is enabled by default, but it will not be automatically enabled for existing training key pools.  With this enabled any organization within the Parent Organization that redeems the training key must be using the same site. 

On the Find Training Key Pool page, we added ‘Sitewide use’ as a filter and output option. 

###  Accessibility Items 
In our continuing effort to improve accessibility for all our students and meet MAS standards on the Course Catalog page:
*   'BookMark’ control is accessible using the keyboard.
*   'Focus’ indicator is visible on the course tile while navigating using the ‘Tab / Shift’ tab keys.
*   Screen Reader now narrates the ‘Bookmark’ button click to bookmark a course.
*   Screen Reader now narrates the icon information within the tile. 
*   The ‘Course’ tile border is now visible in High Contrast Black and White theme Mode.
*   The ‘Focus’ indicator (Dotted Lines) is now visible on Facebook, Twitter and Linkedln image links while navigating using keyboard Tab / Shift tab keys.
*   Filter Control is now accessibility friendly. 
*   The ‘Course’ tile is now accessible using keyboard functionality. 
*   Screen Reader now narrates the ‘Button’ and state as ‘Expand/Collapse’ for ‘Filters’ and ‘Course Topic’ while navigating using the down arrow key 
*   Screen Reader now narrates ‘Match Any and All’ checkboxes when pressing the tab key.

### Lab Activities for Simple Course Assignments
On the Organization Preference tab, when the ‘Course Assignment – Use simple course assignment’ is enabled, a student with a simple course assignment can now launch the lab activity by clicking anywhere within the ‘Table of Contents’ activities tile.

###  Enhancements and Fixes 
*   SeachClubMemberships & SearchSubscriptions: We have added 2 new API calls for SearchClubMemberships and SearchSubscriptions.
* GetUser: We have added a ‘CustomFieldValues’ on ‘GetUser’ API Method.
* GetSsoRedirect:  We have fixed an issue with an ‘Exception Error’ appearing when no ‘UserID’ is supplied and passed through the API call.

----------------------------
## <u>Released April 8, 2021</u>

### Enhancements and Fixes
*   Course Details - Activities Count: A summary count for the number of activities will display next to the ‘Activities’ header.
*   Find Training Key Pools – Expires Default Filter: We have added ‘Expires In the Future’ as a default filter. This will automatically filter out any training key pools that have expired.
*   Zoom - Recordings: Users no longer had access to class recordings after 30 days.  We have fixed the issue and post-class recording access is available for 180 days.
* Course Certificate Date Format:  We have changed the date format of ‘dd MMM yyy’ to ‘dd MMM yyyy’.
*   Instructor Calendar – Calendar Color Olive: We have fixed the calendar color ‘Olive’ from changing ‘White’ when placing the cursor over the event name.

----------------------------
## <u>Released March 25, 2021</u>

###  Subscription Training Key 
We now allow a single Subscription Training Key to be used by multiple users that will align with a subscription. On Create/Edit Subscription Keys, we have added an ‘Expires’ and ‘Max number of uses per key’ field.  This will allow a user with the appropriate permission to set an expiration date and number of uses a subscription training key can be used.  If no expiration is set, the training key never expires.  If no value is set on ‘Max number of uses per key’, it will default to a single use.

On the Find Subscription Keys page, we removed the Redeemed filter and added the following Output Options on the Find Subscription Key page: 
* Max number of uses per key
* Subscriptions created from key
* Expires 

###  Accessibility Items 
In our continuing effort to improve accessibility for all our students and meet MAS standards,we have made the following changes:
*   The Screen Reader now narrates ‘Table of Contents’ and ‘Description’ for simple course assignments. 

###  Enhancements and Fixes 
*   Training Key – Character Update: We have increased the Training Key default from 8 to 16 characters.  
*   PercentComplete Column – Class Roster:  We have fixed the ‘PercentComplete’ on the class rosters showing 0% despite students completing their activities. 
*   API Documentation – SearchCourseAssignments:  We have included Training Key and Subscription as a ‘PaymentType’ to the ‘CourseAssignmentSearchResult’.
*   Translation - File Update:   We have updated the language files in TMS for the following supported languages: 
    *   Chinese (Simplified)
    *   German
    *   Japanese
    *   Korean
    *   Portuguese
    *   Spanish

----------------------------
## <u>Released March 11, 2021</u>

###  Accessibility Items 
Accessibility Items
In our continuing effort to improve accessibility for all our students and meet MAS standards,
we have made the following changes:
*   Focus indicator (Dotted Lines) are visible on My Training, My Transcript, Roadmap, Contact and Help links while navigating using the Tab key on the keyboard.
*   The ‘Please Make A Selection’ window text on the ‘End Lab’ dialog meets the minimum luminosity ratio of 4.5:1.
*   The Screen Reader now narrates Role and State for tab controls Instructions, Resources, and Help within a lab. 
*   Keyboard focus is restored back on the ‘More’ options menu after invoking the ‘Cancel’ button in the ‘End Lab’ dialog.
*   The Screen Reader focus is restored back on the More options menu after invoking the 'Cancel' button in the 'End Lab' dialog.
*   The Screen Reader now narrates Name and Role on the lab ‘More’ options menu.
*   The Screen Reader now narrates the ‘Add’ filter for Organizations and ‘Include Children’ check box on Find Courses.


###  Enhancements and Fixes 
*   User Impersonation: For those who can impersonate another user we have prevented the impersonator from seeing the Active Lab Instances link on the Labs tile.

----------------------------
<!--
## <u>Released February 25 2021</u>

###  Accessibility Items 
*   In our continuing effort to improve accessibility for all our students and meet MAS standards:
    *   General search pages will retain the focus on Add Filter after a filter option is selected. 
    *   Screen Reader is now narrating the pagination and Next controls on the Course Catalog page.  
    *   Screen Reader on the Course Catalog page from the header of the Open Saved Search dialog box now narrates My Searches and Shared Searches.
    *   Screen Reader is now narrating Display Times in Output Options. 

###  Enhancements and Fixes 
*   Course Certificate – Completion Certificate Template: We have added a Course Certificate Date Format field with 8 different options to choose from.  A user with the appropriate permissions can specify the date format on the certificate template. 
*   Find Organizations – Lab On Demand Organization ID Output Option: We have added a Mapped To Lab Provider filter and output option on Find Organization. 
*   User Profile – Time Zone Flag: We have added the ability to set a flag on the Time Zone field on the User Profile.  
*   API Documentation – SearchClasses: A CustomFieldSearchFilter has been added to the SearchClasses API calls. 
*   Bulk Update User Profiles – Organization Management: We have fixed an issue when Bulk Editing Users auto-checking all organizations and assigning organization management to edited users.  


----------------------------

## <u>Released February 11 2021</u>

###  Accessibility Item 
*   In our continuing effort to improve accessibility for all our students and meet MAS standards, 
    *   The Screen Reader will narrate Include Children for the add filter option of Belongs to Organization on Find Courses.

###  Create Multiple Course Assignments 
An option to create multiple course assignments for multiple students has been added to the Course Assignments tile.

###  Enhancements and Fixes 
*   Find Courses – Subscription Filters: We have added a “Subscription Profile (Choose) and Subscription Profile Name” filter on Find Courses. 
*   Find Courses – Organization Search:  You will no longer receive a query message indicating to reduce the scope of your query when finding courses. We have increased the default maximum organizations that you are able to search from 50 to 100.

----------------------------
<!--
## <u>Released January 28 2021</u>

###  Enhanced account security scheduled for implementation at 10:00pm ET Friday, February 12th 
We are implementing enhanced account security for user accounts that sign in with a username/password. You can learn more about these security measures here.
Starting 10:00pm ET on Friday, February 12, local users will be prompted to reset your TMS password upon login at https://lms.learnondemand.net. Users logging in through API or Corporate Azure AD will not be prompted to reset their password

###  This password reset will require email verification.  
*   If you want to continue to use this email address, no action is required. 
*   If you want to change your email address on file, update your profile by 10:00pm ET on Tuesday, February 9.

This small task will enable you to reset your password quickly and easily upon first login after the platform update.

###  Credit Pools 
The Credit Pool feature and functionality has been removed from all TMS UI.

###  Enhancements and Fixes 
Find Entities by ID – Filter: We have added an “ID” filter to the following search/choose pages.
*   Find/Choose Classes
*   Find/Choose Class Enrollments
*	Find/Choose Courses
*	Find/Choose Course Assignments
*	Find/Choose Subscriptions
*	Find/Choose Users


----------------------------

## <u>Released January 14 2021</u>

###  Enhancements and Fixes 
*   Find Lab Instances – E-mail Address: We have added a student “E-mail” address filter and output option on Find Lab Instances.
*   Find Publishing Group – Aligned To An Organization:  We have added an “Aligned To An Organization” filter on Find Publishing Groups.
*   Edit Users – Flag: When flagging fields for change, then editing the users page a second time and saving the formerly flagged fields are now flagged.  
*   Edit User Profile – Roles: The Starts/Expires time fields now fully display AM or PM and no longer stacked.
*   Course, Class, and Catalog Browsers – Default Search Save: When saving a search and making it default, then navigating away the default search is now saving.


----------------------------

## <u>Released December 17 2020</u>

###  Bulk Update User Profiles 
A new Bulk Update User Profiles page has been added to TMS. This page allows TMS administrators to disable users, set time zones, change company and account executives, assign permanent or temporary roles, and designate user accounts for organization management en masse. It can also flag the following fields for update on next user login:

*   First Name
*   Last Name
*   Job Title
*   Primary Phone
*   Secondary Phone
*   Address
*   Address Line 2
*   City
*   State / Province
*   ZIP / Postal Code
*   Country

###  Enhancements and Fixes 
*   API Documentation – Archived Status: An Archived field has been added to the GetCourse and GetCourseByExternalId API calls. 
*   Find Assessments – Company Name Field: A Company Name output option has been added to the Find Assessments Response page. 
*   Bug Fix – Duplicate Training Key: Fixed an issue that could allow for two course assignments to be assigned the same Training Key.
*   Bug Fix – TMS Error Messaging: Fixed a typo in a TMS error message displayed to students who enter their classroom before the class begins.
*   Custom Site – User Creation Landing Page: Newly created users will now be presented with a custom site’s designated landing page on first login. 
*   Bug Fix – Lab Instance Search Page: Fixed an issue on the Lab Instance Search page that displayed a non-translated string in a filter dropdown.
*   Bug Fix – Deferred Launch Labs: Fixed an issue that caused deferred launched labs to not be associated with a user profile.


----------------------------

## <u>Released December 3 2020</u>

###  User Role Expiration on Bulk User Import 
When assigning individual roles to users during the user import process, an option has been added to add automatic expiration dates for each role on a per user basis. 


*   API Documentation – Postman Collection: An importable Postman Collection of API calls has been added to the OneLearn TMS API documentation page.
* Bug Fix – Launching Archived Courses: Fixed an issue that allowed students to launch expired courses from their subscriptions by directly accessing the course launch URL.
*   Bug Fix – Course Progress Bars: Fixed an issue that caused progress bars on the Enrollment and Course Assignment pages to not properly reflect a student’s progress.
*   Bug Fix – Launch Activities Buttons: Fixed an issue that caused Activity Launch buttons to not appear when viewing the Class Details page.


----------------------------

<!--
## Released November 19 2020

###  Browser and Catalog Save Filter Selections 
When enabled, users will now be able to save custom search filters on the Course Browser, Class Browser, and Course Catalog pages.

###  Enhancements and Fixes 
*   Bug Fix – Notification plan calendar invites: Notification plans now properly send attached calendar invites.
*   Bug Fix – Enrollment status: Users with the enrollment statuses of Requested, Cancelled, or Denied are no longer treated as being enrolled in the class.
*   Bug Fix – Zoom recordings: Fixed an issue that would cause single delivery classrooms delivered over multiple days to only display the first days Zoom recordings.

<!--
## Released October 29 2020

###  Create Multiple Enrollments 
We have added a Create Multiple Enrollments link on the Classes tile. Operations managers can now waitlist and enroll multiple students to multiple classes simultaneously from a single menu. If the class is full and users are added with an enrollment status of “Enrolled,” the enrollment status changes to “Wait-Listed” when then enrollments are saved. 

----------------------------
###  Enhancements and Fixes 
*   Sites - Class browser anonymous access: The class browser will now have an option to Allow users to access the class browse page anonymously, allowing users to view class “sessions” without signing into TMS.
*   Notification plans with calendar invites: The following changes were made to notification plans. 
    *   Calendar invites are now only sent when a user has the status of Enrolled or Audit.
    *	Cancellations are now sent when a user status is changed from Enrolled or Audit.
    *	No calendar invite or cancellation is sent when a user is placed in a non-enrolled status.
*   Subscription Profile – Create multiple subscriptions: A Create Multiple Subscriptions link on the Subscription profile page has been added. This will allow an Operations Manager to assign multiple students to a subscription. 
*   Sites – Use training key pool checkbox: The Use training key pool owner organization for new user registrations checkbox will now appear when the Enable register by training key on logon page is checked.
*   Find Enrollments/Find Course Assignments – Duration: Duration has been added as an output option to the Find Enrollments and Find Course Assignments searches. 
* Find Courses – Training days: A training days field has been added as an output option and search filter to the Find Courses search. 


----------------------------

## Released October 15 2020

###  TMS Platform – Adobe Flash 
At the end of 2020, Adobe will permanently end the life of Flash. To prepare for this, the SCORM video upload and Adobe Connect integration have been updated to remove Flash from the platform. It should be noted that Internet Explorer only has legacy Adobe Connect available; once Flash is deprecated, students using Internet Explorer will have to download the Adobe Connect Client or switch to a different browser.

###  Instructors – Class Enrollments 
When an Operations Manager assigns an instructor to a class, the instructor will be prohibited from enrolling or auditing the class.  The following message will appear when the instructors Enrollment Status is set to Enrolled or Audit when attempting to save.

![](images/inst-class-enroll.png)

When an instructor has an Enrollment Status of Enrolled or Audit and is then assigned to the class as an instructor, the following message will appear when attempting to save. 

![](images/inst-class-enroll.png)

If the instructor is not assigned to the class but has an Enrollment Status of Wait-Listed or Requested, the instructor’s enrollment will be bypassed when another student’s enrollment is cancelled.  The student with the earliest created date will be automatically enrolled.   If there are no Wait-Listed students, it will look for Requested enrollments to promote. 

###  Enhancements and Fixes 
*   Find Users - Created By Filter Added: We have added Created By and Created By (Choose) as a filter on Find Users.
*   Featureset - Description: We have updated the Description field to allow values up to 2,000 characters from the previous limit of 1,000.
*   Custom Sites - Training Key Pool: Users can now redeem keys against a central (parent) site and still be placed correctly into the appropriate child org. This removes corner cases where students could register on a parent organization site that uses an older custom login page file that bypasses the normal org id check process, leaving the user registered incorrectly.
*   Class - Lab Activities: Resolved an issue that allowed non-basic users to launch otherwise disabled class activities.


----------------------------

## Released October 1 2020


###  Courses – Virtual Meeting Host – Custom Virtual Classroom 

We have updated the Custom Virtual Classroom to specify when the “Enter Classroom” launch button is available for Pre and Post Class access. Admins now have more flexibility to specify when Instructors and Students can access/enter class using a Custom Virtual URL. 

###  Enhancements and Fixes 
* Publishing Groups: We have added Open and Save options to the Published Organizations tab.  
* Class Details: We have removed Manage Courseware Vouchers from the quick launch menu bar on the Class Details page.
* Notifications: Attach a Calendar Event - We have fixed the .ics file attached to a calendar event from displaying as “Not Supported Calendar Message” within Outlook.

-->
----------------------------

<!--

## Released September 17, 2020

###  Courses – Class Absolute Maximum Capacity 

We have added a Class Absolute Maximum Capacity field on the Basic Information section on a Course Profile.  This will allow an Operations Manager, with the appropriate role to set the Class Absolute Maximum Capacity when creating or editing a course. The lowest value set on either the Class Absolute Maximum Capacity or the Owned Class Maximum Capacity on an organization will supersede, unless the Override Organization Owned Max Capacity is checked. 

When checked, the Override Organization Owned Max Capacity, will override any organization setting regarding the course capacity.

###  Courses - Microsoft Learn Catalog 

We have added support for Microsoft Learn with an Activity option on the Activities section of a Course, which will allow an Operations Manager, with the appropriate role to add Microsoft content to courses.
 
###  Accessibility Item 

In our continuing effort to improve accessibility for all our students and meet MAS standards,
* Aria-Role has been changed to Role in the Close Maintenance button.

###  Enhancements and Fixes 
* Class Details. We have renamed the Expires field to Post Class Lab Expiration Date.  

* Course Profile – Tab Alignment. Tabs on the second row of an entity Edit page now stay properly aligned and do not move over to be underneath the selected tab.  

* Instructor Profile. We have renamed Is Contract Instructor to “Check this box to op-in as a Contract Instructor.”  We added a new link named More Info that will direct a user to more information on What is the Contract Instructor Pool?

* Site Navigation. We have added a new option for single page site navigation and branding removal. 
    *	When entering ?nav=0 to the end of any URL within TMS, the branding and header/footer are removed. For the branding and header/footer to return, the user will need to click Show site navigation. 
    *	When entering ?nav=-1, the branding and header/footer are removed.  The user can either navigate to a different page in TMS or click Show site navigation for the branding and header/footer to return. 

## Released September 3, 2020

###  Organization Notification Plan Management 
We have made enhancements to our Notification Plan feature to allow ownership of notifications at the Org level.  An Operations Manager, with the appropriate roles, can manage their own notification plans for their organization. This will allow you to create your own automated notifications based on configured trigger actions that occur within the TMS (ex: new class created; course assignment completed etc.). 

In addition, we have added a new Notification user interface that will allow users, when logged in, to view any notification that have been sent to them directly within their user profile. To view notifications, click the Envelope icon to navigate to My Notifications.

![](images/org-note-plan-mang-1.png)

From My Notifications you can view any notification that has been sent to you and mark them as read. 

![](images/org-note-plan-mang-2.png)

###  Multiple Instances of the Same Lab 
An organization can now launch multiple instances of the same lab based on their organization limit. The user will be prompted with the option to launch an existing lab instance or launch a new lab instance.  From the screen, they’ll be able to save and cancel previous instances of this lab. 

![](/tms/images/mult instance of same lab.png)

###  Enhancements and Fixes 

* Find Material Responsibilities. When a search is saved, it did not filter for organization management. We have fixed the issue to include organization management. 
* API. The documentation for CreateCourseAssignment and UpdateCourseAssignment API methods have had these two parameters updated from Expire and TargetCompletion to Expires and TargetCompletionDate.
* Course – Activities. When a section was added to the Activities, you would need to Save twice before the section would appear on the class page.  We have fixed the issue and the section will appear when saving on the first attempt. 


----------------------------

## Released August 17, 2020

###  Class Session Times 
We have made the following updates to class Session Times:
* The Session section now automatically displays the Add Multiple Session Times option and the # Sessions defaults based on the Training Days set on the course.
* Add Multiple Session Times has been renamed to Add Session Times
* Add Session Times has been moved to the left displaying as the first option and Add Single Session Time has moved to the right

![](/tms/images/add-multiple-session-times.png)

###  Enhancements and Fixes 

Additions to API Method Results:
* CourseSearchResult – We added Created and LastModified to the results that are returned from the SearchCourses API method.
* SearchLabInstances – We have added LastActivityTime as a Parameter to the SearchLabInstances API Method.

Other Enhancements:
* Enrollment Retake - When a student redeems an Event Training Key, it was not being recognized as a retake within the post-class lab availability. It now recognizes the enrollment as a retake.
* Find Classes - On the Course Profile page, clicking on Find Classes used to navigate to the Event Schedule; it now navigates to Find Classes.  Also, clicking on Class Schedule, now lands on the Event Schedule.

----------------------------

## Released July 30, 2020

###  Enhancements and Fixes 

* Course – Activity Sections: If the first activity within a section is not “Available Instructor-Led,” all other activities within the section that are “Available Instructor-Led” will now be displayed in classes and class enrollments
* Subscriptions - We have fixed the multiple subscription duration from defaulting to 1 year to the duration set on the subscription profile
* Zoom - We have fixed the Zoom API to look for more than 30 users when validating licensed users

Class Launch Button:  The Launch button has been changed from Launch Class to Enter Classroom prior to the class starting
----------------------------
## Released July 9 2020

###  Enhancements and Fixes 

* End User License Agreement - A user impersonating a student will no longer receive “Access Denied”.  The message displayed will now be “Only [Student Name] can accept this agreement.  Impersonated users cannot accept License Agreements”.
* Lab Profile - The lab profile Expected Duration in the TMS will now match the Expected Duration in LOD. 
* Find Lab Instances – The Start filter default has been changed from “Anytime” to “Within Last [Number] Days”.

###  Accessibility Items 

In our continuing effort to improve accessibility for all our students and meet MAS standards, the Screen Reader now narrates:
- The Find Course header.
- The Pagination and Next controls on the Course Catalog page.

----------------------------
## Released June 29, 2020


###  Segmented Student Class Activity Assignments 

For Classes where different activities should be completed by different Students, Instructors and others can now assign individual Class activities to a subset of Students.  This allows some Students to see and access some activities while other Students will see and access others. This feature is best utilized if you are running Classes in a Shared Lab Environment. 

This feature is enabled on the individual activities in the Course using the “Assign to Students Manually” checkbox.  When this is checked for an activity, if a User has one of the new permissions, they can then assign that activity to one or more Students in the class. The activities are assigned and unassigned manually. Only those Students assigned an activity will see it in their Enrollments.  If no Students are assigned to the activity, no student will see it.   

If an Instructor assigns an activity to a Student while the Student is looking at the Enrollment, the activity will automatically appear after a few seconds.  If a Student’s assignment is removed it can take up to 25 seconds to be removed from the Student’s Enrollment.  If they click the Launch button prior to it disappearing, they will receive a message stating “Sorry, you don’t currently have access to this activity.  Please see instructor”.  

This feature is separate from the Disable activities feature released in April of this year, which is used to disable an activity for all students.  Note: If a course is set to Allow activities to be auto-enabled after a class ends, any activities that were disabled when class ends will still show as disabled for anyone looking at the Class but will be enabled for the Students. 

###  Multi-Language Support for TMS Pages 

We now support the localized language on a user’s browser setting for many of the core TMS platform pages. Available Language Translations for localization are: 

* English 
* Chinese (Simplified) 
* German (Germany)
* Japanese 
* Korean 
* Portuguese (Portugal)
* Spanish (Spain)

###  Lab Instance Transfers via TMS 

Earlier this month, we released functionality that allowed a user to transfer their lab instance to another user via email within the Lab on Demand platform. We’ve now included this functionality within the TMS.  

A user can now transfer their lab instance to another user from within the same organization. The transfer occurs via the recipient’s email address. 

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/transfer-lab-email.png)

Items to be aware of: 
The system looks in the Primary Email address field in the transferee’s LOD profile. The user must belong to the same organization as the owning user in LOD.  If the email address is not found, the following message will appear in the Transfer window: “Sorry, this user was not found within your organization”. 

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/transfer-lab.png)

This will occur if either of the following is true:  
* The transferee has never launched a lab 
* The transferee last launched a lab while belonging to an organization outside of the LOD organization family tree the user transferring the instance belongs to.  

If the transferee has the maximum number of saved labs when the transfer is initiated, the transfer will fail, and the following message will appear in the Transfer dialog: “Transferee has the maximum number of saved lab instances”. 

###  Accessibility Items 
In our continuing effort to improve accessibility for all our users we have made the following updates to the TMS: 
* The Screen Reader will narrate Close “X” and “Display times in” on Output Options.  
* The “Featured” and “New” icons on courses meet the minimum luminosity ration of 4.5:1. 

###  Enhancements and Fixes 
* Has Shared Lab Filter and Output Option.  We have added “Has Shared Labs” as a filter and output option on Find Courses, Classes, Enrollments and Labs. 
* Training Keys and archived courses.  Training Keys will be expired for courses that are archived. Users will receive an error message when using these keys.  Training key pools will display the following message “The course aligned to this pool has been archived and the keys in this pool have been expired.” 
* Zoom Update: Zoom recordings will now show properly. We have fixed an issue with the Zoom api query and its date parameters.  
* TMS Administrators: You will no longer receive an application error when modifying your own roles when you have permissions to do so.  
* Courses: Courses will now always archive on their auto archive date and the message displayed on the course will now be “This course is archived.”  
* Has Shared Lab Filter and Output Option.  We have added “Has Shared Labs” as a filter and output option on Find Courses, Classes, Enrollments and Labs.   
* Training Keys and archived courses.  Training Keys will be expired for courses that are archived. Users will receive an error message when using these keys.  Training key pools will display the following message “The course aligned to this pool has been archived and the keys in this pool have been expired.” 

----------------------------
## Released May 21, 2020


###  Wait-Listed Enrollments – Automatic enrollment after cancellation 
We can now automatically enroll a student from the Wait-List when an enrolled student cancels.  This requires an organization to enable this feature under Preferences on the Organization profile.  Auto-enrollment is only done when a student cancels their own enrollment and class is at its maximum capacity; not when an Operation Manager cancels the student. Automatic enrollment is based on earliest created date. If there are no Wait-Listed students, it will look for Requested enrollments to promote. 

![](/tms/images/waitlist-enrollment.png)

###  TMS Enhancements and Fixes 

* Zoom. We have fixed the recordings display issues from zoom accounts configured to save recording files outside MP4.
* Find Class Sessions – Has Labs Filter.  We have fixed the Has Lab filter to be based on Activity type in order for cloud-based lab class sessions to appear in the Does Have Lab results. 

----------------------------
## Released May 7, 2020


###  Class Browser - Multiple Tag IDs in URL 

You can craft your Class Browser URL with multiple tags in it so the page loads with them automatically checked and the page filtered by them when it loads. 

For multiple tags without group reference, the URL structure is https://[site url]/class/browse?tagId,tagId&matchtype=1. The matchtype is optional. If you leave it off, Match All will be checked. If you include it, use 0 for Match All and 1 for Match Any.
 
For a tag in a specific group and a tag in any group, the URL structure is https://[site url]/class/browse?groupIdtag,tagId. Use the group Id for the specific group in which you want the tag to be checked.

###  Find Lab Instances - Company Filter/Output Option 

Need to see your students’ lab instances by the company they belong to? You can do this using the new the new Company output option on Find Lab Instances. This column will display the company set in the user’s profile. You can also narrow the results to see only lab instances from a specific company’s users with the new Company filters available, Choose Company or Company Name. 

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/FindLabInstances-CompanyFOO.png)
 
###  Instructors in All Sessions of Class Automatically 

Now when you set up a class with multiple instructors, all instructors will be automatically added to all sessions of the class. In addition, if you add an instructor later, they are also automatically added to all sessions. If you add another session, all instructors are added to it. When you remove an instructor from one or more sessions, they will not be re-added unless the you click Add all instructors to all sessions in the Instructors section of the class. 

###  Position of HTML Description on Courses  

Want the HTML Description on your courses to be easier to see? This section is now at the top of the Course Profile page, directly below the Description, if present. The HTML Description section will be expanded by default. 

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/CourseHTMLDescription.png)

###  Disabled Class Activities Re-enabled at Class End  

Do you or your instructor’s forget to re-enable class activities at the end of class? No worries. Now, if the course is set to allow activities to be auto enabled after class ends, any activities disabled for students in a class will automatically be enabled for them when the class ends.

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/ClassActivitiesReenabling.png)

###  Accessibility Items  

Two improvements have been made to assist users with accessibility needs.
1. Users can now use the keyboard to access the pagination elements of search pages to pull up different pages of results.
1. The contrast ratio for the Incorrect Username and Password message on the login page has been increased to help with visual clarity.

###  TMS Enhancements and Fixes 

1. Class Browser/Course Catalog/On-Demand Browser. We have improved the filter functionality on these pages to not allow a change in filters until the previous filter results are loaded.

1. Tab alignment on Create/Edit pages. Tabs on the second row of an entity's Create/Edit page now stay properly aligned and do not move over to be underneath the selected tab.

1. Featured Date Chooser in User's Date Format. The Date Chooser will now input the date, using the browser setting of the user, into the Featured field in the Create/Edit Course page.

1. Percent Complete Column for New Students. The Percent Complete column will now appear correctly for new students added to a class roster.

----------------------------
## Released April 23, 2020

###  TMS Enhancements and Fixes 

1. API – Calls for GetCourse and GetCourseByExternalID have had the new Date/Time values added to display in seconds rather than milliseconds. 
1. Class – Class activities now have a disable all check box to disable or re-enable all activities at once. Once any activities are disabled by the instructor, they cannot be launched by students but now remain available for class instructor(s) to use. This allows instructors to demo labs or prepare future activities while preventing students from skipping ahead in the curriculum.
1. Class – A Custom Virtual Meeting Host issue has been corrected. When setting the delivery to use a Custom Virtual Meeting and inputting a URL for the meeting, if the delivery was reset to Physical, the Enter Classroom button still displayed. Changing a class delivery back to Physical no longer displays the Enter Classroom button to users.
1. Class – Zoom’s integrated Virtual Meeting Host will now reflect the correct time in UTC for when a class is scheduled. It was picking up the user’s time zone as the UTC time for the event. Zoom does straight UTC and does not take into consideration daylight savings time. Therefore, if a class is scheduled right now for 8:00 Central Daylight Time, it will appear in Zoom as 13:00 UTC instead of 14:00 UTC. 
1. Class import – The “Inherit certificates from course” setting was not being enabled by default for classes when they were created through the class import. This prevented completion certificates associated with the course to be set up automatically on the class. The setting is now enabled by default when classes are imported.
1. Enrollments – On the Find Enrollments page, when using the Class Status filter and filtering for Any, it was not showing any search results. It now shows results for all statuses. 
1. Course Assignments – The Find Course Assignments page has had several updates. The Payment Type filter now has options for Is, Is Not, and Is or Is Not. Columns for Payment Type and Completion Status are now sortable. 
o	Sorting on the Payment Type column groups by types of payments but not within types. For example, a listing in the column may be Payment Type “Subscription” with the “Subscription Name”; it will sort Subscriptions together but does not sort by the name of the subscription. 
1. Labs – On the Lab Details page we have relabeled the button that cancels a lab instance to read Cancel instead of Delete. The delete label was confusing to some users.
1. Badges – On the Class Roster page, when a badge is added for an individual by clicking the trophy icon on the roster, a Badge chooser dialog opens to select the badge(s) to add. When the badge is added a message will briefly display on the roster line for the student that the badge was successfully added. The success message which showed in the chooser dialog has been removed. 
1. Chrome browser back button – A search issue in Chrome has been corrected, you can now use the Back button to return to a search page and have it return results. The issue was that on any “Find” page, if you ran a search, navigated away, then used the Back button to return to the search and run it again, you would receive an error message.  

----------------------------
## Released April 10, 2020

###  Use Zoom for your Integrated Virtual Meeting Host 

Zoom can now be integrated in the TMS, allowing you to schedule a class and create the Zoom meeting all at once. The integration also gives each student links to class recordings directly from their enrollment. 

For information about how a Zoom integration functions, click here and for information about setting up a Zoom integration, click here.

###  Enable or Disable Class Activities 

You can control when and if students have access to class activities. Instructors can enable or disable any activity in a class they teach. Operations managers can disable activities in classes they manage. This allows blocking students from launching labs requiring an Azure pass. 

The course controls if activities can be disabled in a class. Courses default to not permitting activities to be disabled. When a course allows for activities in a class to be disabled, then any class using that course shows an Enabled check box on activities. All activities in a class, labs, external links (video, document, website), assessments, and SCORM modules can be disabled or re-enabled during class. Surveys cannot be disabled.

In the class, all activities are enabled by default. Instructors and operations managers have a check box on each class activity to disable or re-enable it. Uncheck the Enabled box to disable the activity. Students will see the update to the status of the activity within 30 seconds without refreshing the page. 

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/enable-activity.png)

A disabled activity displays, slightly grayed out with a “Disabled by Instructor” message for students and the Launch button does not display.

> ![](https://github.com/LearnOnDemandSystems/docs/blob/master/tms/images/student-disabled-activity.png)

###  TMS Enhancements and Fixes 

1. Edit Class – We have corrected the prohibition from editing a class after it has started when the date has not been changed. Users were receiving a message, “You don't have the necessary permissions to set this class’s start date prior the current date and time." when they attempted to update fields other than the class start date and save a class.

----------------------------
## Released April 02, 2020 

###  TMS Enhancements and Fixes 

1. API – We added some return values to several API calls. The SearchLabInstances call now returns the LastActivity value. The GetCourse and the GetCourseByExternalId calls now include values for CourseDateCreated and CourseLastModifiedDate.
1. Date and Time formats – We have updated the date formatting to configure based on the browser’s language setting rather than only show in US date format of MM/DD/YYYY. 
1. Classes – We have modified classes so that the start date and start time must be equal to or later than the user’s current date and time. 
1. Training Key Pools - Ops Managers are no longer able to create a Training Key Pool using an archived course or a course scheduled to be auto-archived before the expiration date set on the pool. Saving a new pool using an archived course shows the message, “Sorry, the course you are trying to create training keys for is archived.” Saving a pool with a start or expiration date that falls after the auto-archive date, shows either the message, “Sorry, the course you are trying to create training keys for is scheduled to be archived before the training key pool start date. Please select another course.”  Or “Sorry, the course you are trying to create training keys for is scheduled to be archived before the training key pool expiration date. Please select another course.”
1. Find Subscriptions – We have added an output option for Price on the Find Subscription search page.
1. Class Roster – We have corrected the negative figure in the Percent complete column on the Class Roster page. The Percent complete column shows the percentage of the required course activities that have been completed by each student. This was displaying a negative number before students started the labs and has been corrected to show zero. 
1. Find Lab Instances – We have updated the Lab Instance details page which was giving a Server Error. From the Find Lab Instances search, a server error displayed when the Details link was selected. LOD removed some legacy exam information which the page previously displayed. Initially, a fix was put in place that incorrectly removed exam results information, this information has been restored.

----------------------------
## Released March 19, 2020 

###  TMS Enhancements and Fixes 

1. Find pages – We have corrected a sorting issue on the Output Options menu. When output options other than the defaults for a page are selected, now when you switch between Sort Alphabetically and Sort by Group, your selections will be retained.
1. Find Classes – We have added an Output Option to the Find Classes page showing the Max Lab RAM per Student showing the highest amount of RAM used in the class’ course per student.
1. Find Enrollments – We have added an Output Option to the Find Enrollments page showing the Job Title field’s data from the User profile.
1. Browse on Demand Catalog – We have updated the Browse on Demand pages to allow multiple Course Tags to be selected by default when users arrive on the page. Along with this, the page can now be set to default either the Match Any or Match All selections on the page. 
1. Class Training Key – We corrected an Application Error which was showing up when you saved after editing a Class Training Key. 
1. Find Lab Instances – We have repositioned the Percent Complete column when the search results are exported from the TMS to match column order on the Find Lab Instances page. 
-->
