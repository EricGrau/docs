<style>
    h1:first-of-type {margin-top:0;}
</style>
 
<div style="float:right; padding-top:5px; font-size:120%;">
   <a href="https://www.skillable.com/roadmap-updates-form/">Subscribe to Receive Email Notifications about Platform and Service Updates</a>
</div>

# What's New in Lab On Demand
<span style="font-size:100%;"> <a href="/whats-new-toc.md">What's New in the other Skillable platforms?</a></span>

## **Released December 17, 2021**

Lab Save & Timer Updates 

**Refinement of lab duration and save configuration options**

Expected Duration Changed to "Duration"

- On a lab profile, Expected Duration is now defined as Duration.
- On the lab profile edit screen, Duration now a drop down of selectable time options.

Lab Client Timer Based on Duration

- In the lab client, the timer now reflects Duration instead of Max Duration.
- On the lab profile edit screen, the Automatically Prompt User to Extend setting has moved from the Advanced to the Basic Information tab.

System Generated Max Duration

- On the lab profile edit screen, the Minimum time given to saved labs setting has been removed.
- On a lab profile, Max Duration is no longer a customizable field. This is now automatically calculated at 150% Duration if extensions are enabled.
- In a lab instance, Max Duration now enforced as maximum amount of time users may be within the lab.

In Development Labs May Extend Indefinitely
- Labs with a status of In Development may continue to be extended for an indefinite period of time.

Revamped Virtualization Sizes

**Virtual Machine and Docker Container size definitions have been modernized and simplified. More information available [here](https://skillable.com/vm-tiers/)**.

Change Docker RAM and CPU from Text Box to Dropdown

- When creating or editing a Container Image Profile, RAM and vCPU values are now defined via a single dropdown instead of multiple text boxes.
Change VM RAM and CPU from Text Box to Dropdown
- When creating or editing a Virtual Machine Profile, RAM and vCPU values are now defined via a single dropdown instead of multiple text boxes.

VMs enforce max number of NICs

- When creating or editing a Virtual Machine Profile, a maximum number of NICs will be applied based on the virtual machine size selected.

**LOD Improvements and Fixes**

- Fixed and issue that resulted in delayed implementation times for Access Control Policies.
- When monitoring a Hyper-V lab that uses Enhanced Session Mode, screenshots and thumbnails will inform the user that Enhanced Session Mode is in use. 
- vSphere labs with no Virtual Machines now show Screen Unavailable when monitored. 
- Fixed an issue preventing TMS lab instance monitoring from displaying screenshots.
- Fixed an issue preventing users from updating their password using the Reset Password link. 
- Fixed an issue that would cause duplicate identity claims during log in. 
- When importing and overwriting instructions into an existing lab, all existing content and files will now be removed.
- Fixed an issue resulting in the Template Gallery becoming disabled for an Organization.
- Fixed an issue resulting in LCAs appearing out of order when editing a lab profile. 
- Fixed an issue resulting in an Application Error occurring when logging into LOD under certain conditions. 
- Fixed an issue preventing JAWS from reading messages when starting a cloud lab.

## **Released November 19, 2021**

**Consumption Rules – New to Lab on Demand**
- Consumption Rules allow Lab on Demand administrators to limit launches of lab profiles as well as modify Themes and support URLs applied to specified lab instances based on a set of conditions such as API Consumer, Lab Series, and more!
- Please contact Skillable Support to configure rules for your organization.

**Security**
- Fixed an issue that allowed users to resubmit activities for scoring even when the activity did not allow retries.
- Numerous Platform and API hardening improvements.

**AWS, Azure, VMWare, and Container Lab Fabrics**
- Support added for AWS WAF CloudFront
- In labs using AWS Cloud Slice, Target Groups are now removed when Attached to an Application Load Balancer.
- Fixed an issue causing VMWare storage to be created with the wrong path.
- Fixed an issue allowing students to see containers that should be hidden. 
	

**Search and Auditing Improvements**
- Notes have been updated to use a paged structure and are only pulled from the server when needed. This will reduce load time for some entities, reduce DB overhead, and improve the UI. 
- Added "Custom API data / Tag" filter and output option to find lab instances page.
- A Script Execution Error filter has been added to the Lab Instance Search page.
- Improved page performance on the Lab Series Storage page

**LOD Improvements and Fixes**
- LTI 1.3 calls no longer require the lti_message_hint parameter.
- Lab variables are now updated between each script within a given activity.
- Corrected a display issue when selecting an image link on the Lab Manual preview page.
- Fixed an issue where notifications are sent, but no message is displayed to user.
- Fixed an issue preventing the Lab Profile edit page from honoring the sort order of Virtual Machines in the VM tab.
- Fixed an issue preventing Lab Manual viewing on labs inheriting content from a parent lab profile.
- Fixed an issue causing Lab Profiles inheriting an environment and content to be displayed multiple times on the parent Lab Profile.

## **Released October 21, 2021**

**AWS Cloud Slice**

- Added support for AppSync.
- Added support for Amazon CloudFront.
- Added support Load Balancer Target Groups.
- Added teardown support for CloudFormation Stacks in an Update_Failed Status.
- Fixed an issue where RDS MySQL resources may not tear down properly.
- Fixed an issue where Service-Roles deployed via Stack would not tear down properly. 
- Fixed an issue where AWS Backup Plan could prevent Cloud Formation from being torn down.
- Fixed an issue where user permissions would not be restored on lab resume.
  - [AWS Capabilities documentation](/https://docs.skillable.com/lod/aws-capabilities.md)

**User Interface and Accessibility Updates**

- When canceling an active lab from the lab instance details or lab profile details page, updated the confirmation dialog to be platform native instead of using the browser’s. 
- When launching a Cloud Lab using a screen reader, the following dialogue will now be read:  "Clicking 'Get Started' will open two windows. The cloud portal will be in the left window, and the lab instructions in the right window."
- When completing end of lab evaluations, the star rating now supports adding and subtracting stars via the arrow keys as described by a screen reader
- Updated the gray lab client theme to meet accessibility contrast standards.
- Updated translations for French, German, Japanese, Korean, Portuguese, Spanish, and Chinese.
- Fixed a typo on the “Provisioning files on high-performance storage” message.

**LOD Improvements and Fixes**

- Added lab profile number field to LTI deep link selection page.
- Fixed an issue where changes made to Access Control Policies had a delayed period before they would begin applying to new lab launches.

## **Released September 23, 2021**

**Cloud Subscription Pool**

The Cloud Subscription Pool pages have been updated to include the following features where applicable:
- Paging for increased performance.
- A Cloud Subscription Pool Summary visual to display subscription/account states.
- A link to the last lab instance run against dedicated subscriptions.
- A link to federated login.
- Sorting and Keyword Filtering of data fields.
  - [Azure Subscription Pool setup documentation](/guides/cloud-slice/microsoft-azure/azure-setup-cloud-sub-pool-in-lod.md)
  - [AWS Subscription Pool setup documentation](/guides/cloud-slice/aws/aws-setup-cloud-sub-pool-in-lod.md)

**LOD Improvements and Fixes**

- The API End Webhook is now called for scored labs when the lab ends.
- LTI scored labs that run beyond their access token expiration are now able to post score back to the LMS without getting an access token expired error message.
- The Cloud Resource Groups title has been replaced with Stack Deployments in the LOD Admin site when reviewing AWS Specific Lab profiles.
- External Stockpile Name requirement has been removed from recyclable type credential pools.
- Fixed an issue that incorrectly displayed the Record Desktop option on container labs.
- Fixed an intermittent issue delaying vSphere lab launches with non-Windows Virtual Machines.

## **Released August 26, 2021**

**Caching Improvements**

- When a differencing disk is added to a VM profile, the lab availability records will be purged for all associated labs.
- When a Lab Profile or VM Profile is updated, the lab availability records will be purged for all associated labs.
- Storage Profiler will now compare a lab profile's last modification date and date of cache, flushing the cache when applicable.

**vSphere**

- When creating a new vSphere Virtual Machine Profile, the Hardware Version will now default to 14.
- vSphere Hardware Version 15 is now supported by vSphere Virtual Machines running in Lab on Demand.
 
**Docker**

- In addition to terminal connections, LOD now supports connecting directly to a port on a docker container. A container configured this way can be displayed in the regular lab client alongside regular terminal connections.
    - <a href="https://docs.skillable.com/lod/terminal-access.md">Terminal Access documentation</a>
    - <a href="https://docs.skillable.com/lod/container-web-display.md">Container Web Display documentation</a>
 
**Template Gallery**

- Lab profiles that are published to the template gallery now have an option on the Advanced tab to Reuse Template Container and Virtual Machine Profiles. Selecting the option will cause Lab Profiles created from the Template Gallery to reuse the existing Container and Virtual Machine Profiles from the template.
    - <a href="https://docs.skillable.com/lod/feature-focus/lab-profiles/create.md">Lab Profile Documentation</a>
 
**Organization Name Changes**

- Organization names may no longer be changed from LOD unless they are a child organization configured with the same customer ID as their parent. Organization names should be modified from the Portal when they cannot be modified in LOD.

**LOD Improvements and Fixes**

- Update to HTML5 Gateway will release mouse on cursor exit of VM interface.
- Lab instances of exam type will now be scored when Mark as complete is chosen using the end option under the hamburger menu.
- Newly created users passwords will no longer expire.
- Parameters set on a Cloud Resource Template via JSON parameter file import can now be upper case. 
- vSphere shared environment networks can no longer be set to specific VLAN IDs.
- Price data when searching for lab series assignments now uses the lab series price field instead of summing prices.
- API Service no longer has a missing dependency injection registration.
- Added support for S3 Access Points.
    - <a href="https://docs.skillable.com/lod/aws-capabilities.md">AWS Capabilities Documentation</a>
- Fields beginning with an "=" will be sanitized when exported to CSV by prepending the string with a single quote. This is done to prevent excel formula injection attacks.
- Added logic to prevent distribution of malformed credentials from recyclable tenant pools.
- Icon added to Application card on Admin page.
- The Application card logo color should now match the rest of the theme color.
- Advertising icon has been restored on the Advertising card when using the purple theme.
- Fixed a typo in an error message shown when attempting to update the name of a Virtual Machine in a lab profile. 
- The Virtualization Platform read only tooltip now appears only when the virtualization platform setting is read only. 
- A Custom Audience Claim (Aud) can be defined in the LTI configuration of an API consumer. 
- The LOD.web scheduler now ignores shared lab environments when enforcing Class Max Active Lab Instances.
- When selecting a SCSI disk ID, the ID will be chosen from a pool of unused IDs rather than defaulting to ID 10. 
- Fixed an issue resulting in an error message when inspecting or adding disks to vSphere VMs. 
- Fixed an issue preventing the proper parenting of differencing disks when saved in quick succession. 
- Fixed an issue preventing the modification of an Organization Customer ID.
- Fixed an issue in AWS VPC teardown occurring when dependencies can't be resolved.
- Fixed an issue resulting in an error message when attempting to update a running Docker Container lab.
- Fixed an issue preventing HyperV host from self-updating. 
- Fixed an issue preventing double quotes from properly rendering in tool tips (info icons).
- Fixed an issue preventing users from editing their account information.
- Fixed an issue where an access key could remain active while a lab is in a saved state.
- Fixed an issue preventing CWD from Cleaning up Azure Cloud Resource Groups.

## **Released July 29, 2021**

**LOD Improvements and Fixes**

- Improved Pre-Instance performance using in-memory data and by removing recursive logic
- Rather than default to CSFX, cloud scripts will now target SEE by default.
- Added scale-out support for developer files.
- A new field has been added to Lab Series, Default Assignment Duration Days. The duration of all Lab Series assignments created using this lab series will be set to the value of this field.
- Mandatory note fields can no longer be bypassed by entering a space character.
- Removed the Cloud Log Transfer tab from Azure Cloud Subscription Pools.
- Network ACL is now included when exporting and importing lab profiles.
- vSphere labs no longer display a Record RDP Session option. RDP session recordings are only available for Hyper-V labs.
- Newly created Organizations will now have the Template Gallery enabled by default.
- When signing into Lab on Demand using Corporate Azure Active Directory authentication, you will now be prompted to select the account used to sign in.
- When searching for Lab Profiles, the search can now be filtered by the presence or absence of Life Cycle Actions.
- Outcome variable names and languages are now persistent when editing an Automated Activity.
- Fixed a bug resulting in an AWS teardown error due to a dependency on IAM resource. 
- Fixed a bug resulting in the wrong SCSI ID to be used in newly created virtual machine profiles when using the Save-as New Lab functionality from a running lab.
- Fixed a bug resulting in an application error when creating a Lab Series from an Organization page.
- Fixed a bug preventing lab authors from overwriting files when uploading a file/image to a lab profile's instructions. 
- Fixed several bugs preventing Azure Cloud Slice Subscriptions from moving between management groups correctly.
- Fixed a bug preventing AWS VPC deployment to default regions.

## **Released July 1, 2021**

**Pricing**

- Lab costs are now shown in USD, regardless of user language. 

**Code Labs**

- Lab On Demand now supports a new type of container image classed as CodeLab. The type filter on the Find Container Image page now supports filtering by type Codelab. 
- A new Code Language Administration page has been created. This allows for the management of the container used, the default templates shown in the Edit Code Fabric screen, and information used to process submitted code in the CodeHost. 
- Code language data is now pulled from a database object instead of being stored uniquely in each lab profile. 
- <a href="https://docs.skillable.com/lod/code-lab.md">Code Lab Documentation</a>

**Lab Instance Error Viewing By Organization**

- Lab authors with the "Error Viewing (by organization)" permission can now view any lab instance errors occurring in lab instances of lab profiles belonging to the organizations they manage. The Find Lab Instance Errors search page can be located under the Lab Instance tile on the Lab on Demand admin page.

**AWS**

- Two new services are now available in AWS Cloud Slice, Tag Editor and Resource Group Editor. 
- Fixed a bug allowing a user to access an AWS region selected in the Override Datacenter drop-down menu even when not enabled on the lab profile.
- <a href="https://docs.skillable.com/lod/aws-capabilities.md">AWS Services capabilities documentation</a>

**LOD Improvements and Fixes**

- Cloud Slice Subscription labs that apply an Access Control Policy at the subscription level are now returned in search results for that Access Control Policy. 
- If Background Event Service discovers residue on a virtualized host, cloud hosts will now ignore requests to tear down resources on the associated dedicated subscription if the subscription has already been assigned to another lab instance. 
- Child lab profiles inheriting an environment can no longer be exported. 
- Docker host app settings have been moved into environment specific files. 
- Client-side gateway scripts updated to allow Firefox to work with client-side ESM audio recording. 
- Activity groups in the Lab on Demand API v3.0 have been updated. When an activity group is used, the name of the group is sent as a variable with the total score for activities within that group only. In addition, full responses are sent for each individual activity. 
- Implemented support for SES scale out. 
- Fixed a bug preventing an ABA from picking up a variable set by a previous ABA when scoring a lab/exam. 
- Fixed a bug preventing lab authors from taking VM screenshots from the instructions editor. 
- Fixed a bug preventing internal administration of an account when removing an API consumer. 
- Fixed a bug preventing a post-build LCA from executing when preceded by a blocking post-build LCA. 
- Fixed a bug preventing lab saves on newly launched container labs. 
- Fixed a bug preventing changing a Virtual Machine Display Name. 
- Fixed a bug resulting in some users unable to launch into pre-instanced labs due to public IP availability. 
- Fixed a bug resulting in an application error when navigating back from an error page generated when saving a lab profile. 
- Fixed a bug resulting in an error when scripts are rapidly executed against a single-instance SEE container. 
- Fixed a bug resulting in an unknown platform type on removable media when imported as part of a lab profile. 

## **Released May 22, 2021**

**IDLx**

- IDLx variable assignment now supports a new password textbox. The textbox can be created in IDLx via the @lab token @lab.MaskedPassword(name). Text entered into the box will be obscured from the user, and will be assigned to the lab variable Name.
- Fixed an issue preventing IDLx replacement tokens with repeated special characters from displaying properly.

**Nested Virtualization**

An option to allow a vSphere VM guests to know their virtualization status has been added to vSphere fabric virtual machine profiles.

**LOD Improvements and Fixes**

- An improvement to the batch operation efficiency of AWS Log transfer has been implemented.
- Implemented compatibility mode for HyperV Gen1 virtual machines.
- Fixed an issue causing Series Save As to not save the answers for multiple choice questions in IDLx.

## **Released May 7, 2021**

**Script Execution Engine**

Our next generation Script Execution Engine, SEE is now available to power ABA automated activities and scripted Life Cycle Actions. This new engine allows LOD to expand into new scripting languages and also makes it easy for lab developers to add custom modules from select repositories. Languages will be available via a drop-down menu when authoring activities. Legacy options will still be available to run existing scripts already in place. In addition to running on virtual machines and containers, the following language combinations are now available:

- C# .NET 5
- C# .NET 5 | Azure.Core 1.13.0
- node.js 14 | AWS SDK for JS 3
- node.js 14.16.1
- PS 7.1.3
- PS 7.1.3 | AWS CLI 2.1.39
- PS 7.1.3 | AWS.Tools 4.1.10.0
- PS 7.1.3 | Az 5.7.0
- PS 7.1.3 | Azure-CLI 2.22.1
- Python 3.9.4
- Python 3.9.4 | AWS Boto3 1.17.50
- Python 3.9.4 | Azure SDK 1.13.0
- PS 5.1 | AWSPowershell.netcore 4.1.3.0 (Legacy)
- PS 5.1 | AzureRM 6.8.1 (Legacy)

**Disable Compatibility Mode**

HyperV Virtual Machines now can have Compatibility Mode disabled from the Advanced tab of the Edit Virtual Machine Profile page. Disabling Compatibility mode passes the flag limitProcessorFeatures=false to the hypervisor on Virtual Machine creation, allowing advanced instruction sets to be utilized by the guest Virtual Machine. Lab Profiles containing Virtual Machines with Compatibility Mode disabled cannot be migrated between hosts, and cannot utilize Virtual Machine Start States.

Two permissions have been added to LOD to manage Compatibility Mode under Lab Development: Host Compatibility Edit Global and Host Compatibility Edit By Organization.

**AWS**

- Added Support for AWS Service Event Bridge Schema
- Added Support for AWS Service SQS
- Fixed a bug preventing labs from saving when an access key was added to a user account.

**LOD Improvements and Fixes**

- HTML5 gateway updated to allow sound recording via Chrome and Edge browsers.
- Cloud automated activities can now set the activity's score by percentage.
- Script Execution Engine no longer displays a cloud subscription chooser in Cloud Slice Subscription multi-subscription labs when a locally hosted virtual machine is selected as the script target.
- The start state cache link will no longer be shown when the account viewing the lab profile page does not have the permissions necessary to modify the cached start state.
- The LOD API service now returns ActivityGroupResults as part of the Lab Instance Details call. 


## <u>Released April 23, 2021</u>

**Code Labs**

- JavaScript has been added as a Code Lab language.
- Setting a language as default now correctly displays that language when starting a Code Lab.
- When canceling a lab conversion to a code lab fabric, the code lab fabric checkbox is now unchecked.
- Copying a Code Lab that contains activities generates new internal activity IDs.

**RDP Session Recording**

- When editing an Organization, the "Retain session Recording for * days" information icon now correctly displays help text.
- Lab Instance Virtual Machine Recordings can now be downloaded from the Lab Instance Virtual Machine Recordings page as .rdpv files.
- The  Lab Instance Virtual Machine Recordings page now contains a link to navigate back to the parent Lab Session Details page.

**AWS**

- AWS Service Linked Roles will now be removed on cloud teardown. The following roles will persist through lab instances.
    - AWSServiceRoleForSupport
    - AWSServiceRoleForCloudTrail
    - AWSServiceRoleForTrustedAdvisor
    - AWSServiceRoleForOrganizations
    - OrganizationAccountAccessRole
    - AWSServiceRoleForSSO
- Added additional logic to AWS so that Virtual Machines with termination protection are properly torn down.
- Added verification to AWS Stack Deployment Name Field.

**LOD Improvements and Fixes**

- The ability to export Virtual Machines have been restricted to those with Global Storage Management permissions.
- Added additional logic to AWS so that Virtual Machines with termination protection are properly torn down.
- Unassign Credential Link is now displayed next to the first property in the resources tab of the lab client.
- Corrected a typo in the security review dialog displayed on a cloud lab profile.
- The German localization for "ID" has been updated.
- Public IP replacement tokens now appear in the instructions editor for child labs inheriting an environment. 
- The Subscription Token dropdown will now be populated on newly created Multi-Subscription Cloud Slice Subscription labs.
- Labs will no longer launch against disabled classes through API consumer.
- Fixed a typo in an Azure provisioning error message.
- Attempting to save a new Azure Cloud Subscription to a Cloud Subscription Pool without a Cloud Subscription Id will now warn that a valid Cloud Subscription Id is required.
- Azure hosted Virtual Machines in Azure Cloud Slice Subscription saved labs now properly resume when the lab is resumed.

## <u>Released April 9, 2021</u>

**Code Labs**

- Swift has been added as a supported code language.
- Ruby has been added as a supported code language.
- Code Labs now support scoring via API. For more information about scoring labs via API, click <a href="https://docs.skillable.com/lod/lod-api/lod-api-score-activities.md">here</a>.
- Code Labs lab instance details can now be returned via API. For more information about returning lab details via API, click <a href="https://docs.skillable.com/lod/lod-api/lod-api-details.md">here</a>.
- Code Labs tests activity results are now displayed on the lab details page. The details contain the console output, as well as metadata such as language and elapsed runtime.
- Code Labs now support the Learning Tools Interoperability (LTI) 1.1 & 1.3 standard for integration with Learning Management Systems. 

**LOD Improvements and Fixes**
- Cloud Slice Subscription labs are now returned as results when searching by Access Control Policy.
- Fixed a dependency issue that would prevent the removal of CloudFormation stacks dependent on a missing role.
- Fixed a bug preventing AWS Fabric labs from launching after they are created via Save-As.
- The support chat link appearing in the lab client will now be determined by the organization the lab user is a member of, rather than the source organization for the lab.
- AWS Fabric labs with shared subscriptions no longer support executing Life Cycle Actions against AWS.

<!--

## <u>Released March 26, 2021</u>

**Virtual Machine Key Codes**

Clickable links to send keyboard shortcuts to a virtual machine can now be added via the `@lab.KeyCombo(Label)[KeyCode1, KeyCode2]` syntax. 

For example, when `@lab.KeyCombo(Win+Tab)[91,9]` is written into the instructions, a clickable link with the text Win+Tab will be rendered into the instruction pane. When the link is selected by a student, the keycodes 91 (Windows Meta Key) and 9 (Tab) will be sent to the virtual machine. These particular keycodes will open task view in the Windows operating system. Not all keycodes/combos are available, please verify the keycodes required for your scenario are available before publishing your lab.

**LOD Improvements and Fixes**

- A new Lab Profile search filter, Code Lab, has been added to help locate labs that are or are not code labs.
- Cloud Slice labs that deploy resources to the cloud in the background now require at least one ACP to be immediately applied on lab launch.
- Shared Class environments may no longer be launched after the end of a class availability. A message will be shown informing the instructor why they may not launch the lab, "The class this shared lab environment is being launched against is no longer available." 
- The Code Lab Save icon now properly reflects the save status while editing Code Labs.
- Updated the error messages and required asterisks on the create user page for conformity and clarity.
- AWS Cloud Slice labs no longer show an invalid option to Enable Multiple Subscriptions.
- Fixed an issue that allows Azure Cloud Slice labs to properly clean up Recovery Services Vaults with Protected Items.
- Fixed an issue preventing S3 buckets from being torn down when they contained an item.
- Resolved a bug that prevented scrolling in a virtual machine when using Chrome 89.


## <u>Released March 12, 2021</u>

**Code Labs**

- Expanded the size of the input fields for creating custom test variables to better accommodate testing against strings. 
- The enabled icon now accurately shows the status of the selected language without having to exit or refresh the Code Lab editor. 
- Improved handling of the default language selection: 
  - When no default language is selected, the Code Lab will display the first enabled language. 
  - Disabling a language that has been selected as default will remove the selection. 

**Lab on Demand API Accounts**

When launching via API call, we will now append a unique identifier to the username when an existing user not associated with an API consumer shares the same username.

**LOD Improvements and Fixes**

- Updated the Lab Client Main Menu button to show an outline on focus. 
- Default Lab on Demand session length has been extended to 240 minutes 

## <u>Released February 26, 2021</u>

**Lab Series Save-as**

The option to save a lab series as a new series has been added to Lab on Demand.
After selecting the Save-as link from the lab series edit page, a dialog box will be shown allowing you to name the new series, choose a different organization, and deselect any lab profiles you would not like to carry over into the new series.

**Restricted Editing Permissions Around Lab Profiles Published to The Template Gallery**

Editing of Lab Profiles and dependencies will be restricted to those able to publish to the gallery when a lab profile is already published to the corresponding gallery (Public or Organization). A banner has also been placed at the top of any lab profile published to a gallery. Dependencies include:
- VM profiles
- Container Profiles
- Cloud Templates
- Access Control Policies
- Instructions
- Differencing Disks
- Start States
 
**Azure Cloud Slice**

- Azure CSS labs now maintain their Access Control Policies when created via the Save menu within the lab client. 
- Added additional retries to Azure Management Group operations.
- Azure hosted VMs running in Azure CSR labs now properly deallocate and resume when a lab is saved.
- The lab instance details page now supports showing all subscriptions for multiple subscription CSS labs.
 
**Code Labs**

 - Code lab custom tests can now be edited after creation.
 - Code labs now retain custom tests after the page has been refreshed.
 - Code labs custom tests now properly display returned results for multiple tests.
 - A default language for Code labs can now be chosen from the Code lab creation menu.
 - Code labs can now be immediately started after creation, without adding a default test or language.
 
**Launch on Datacenter**

Hyper-V and vSphere lab profiles can now be launched against a chosen datacenter. To view the Launch on Datacenter option in the lab profile, lab developers will need organization management and storage management permissions. The organization they manage will all need to be configured so that storage is available across multiple datacenters.
 
**LOD Improvements and Fixes**

- Updated VM Gateway Client Scripts.
- Updated translations for Japanese, Simplified Chinese, Korean, French, and Spanish.
- When searching for Lab Instance Errors from a selected Cloud Subscription Pool, search results are now returned properly.
- Fixed a bug preventing an admin from launching a second instance of participant lab belonging to a shared lab class in Lab on Demand. 
- Fixed a bug preventing multi-subscription labs from importing with the correct number of subscriptions.
- Fixed a bug preventing vSphere labs from saving or resuming after having been moved between lab hosts.
- Fixed a bug preventing an instructor from launching into a shared environment lab when initially launched in conjunction with a participant lab.

## <u>Released February 12, 2021</u>

**Central Authentication**

Lab on Demand implemented enhanced account security for user accounts that sign in with a username/password. You can learn more about these security measures [here](https://www.skillable.com/enhanced-account-security-faq/).
Local users will be prompted to reset their LOD password upon login at https://labondemand.com. Users logging in through API or Corporate Azure AD will not be prompted to reset their password.

**Multiple Cloud Slice Subscriptions**

Lab on Demand now supports multiple Azure subscriptions in Cloud Slice Subscription labs. 

**AWS Services**

AWS Cloudshell Service now supported.

**LOD Improvements and Fixes**
- Lab authors can now disable individual scripts within automated activities.
- Code labs now allow tests and test inputs to be created without first adding a code language.
- IDLx activities can now be hidden from the scoring output of a lab instance.
- The "go to page" feature of outcomes now correctly sends users to the top of the target page.
- The search field is no longer obscured while searching within the Cloud Resource Template editor. 
- Full screen view is no longer obscured within the Cloud Resource Template editor.
- Added a Launch on Datacenter option to launch on-prem virtualization labs on a target datacenter.
- Added a rescoreAll parameter to the ScoreActivities API call. Triggering scoring of a lab with the rescoreAll=1 parameter rescores all lab activities, overwriting all previous results.
- The number of ports utilized by a container lab is now shown in the basic information tab of the lab profile.
- An Email Confirmation has been added when creating an account.
- vLan ID can now be specified per network on vSphere fabric lab profiles.
- Fixed a bug resulting in broken links when on a Lab on Demand class.
- Fixed a bug resulting in an incompatibility between Wait for Heartbeat option on VM and Deploy in Background option on resource group in cloud tab of a lab profile.
- Fixed a bug where cloud security review would persist when updating the parent of a child lab profile
- Fixed a bug preventing child labs from inheriting resources when updating to a different parent profile.


## <u>Released January 30, 2021</u>

**Code Labs**

Code Labs can help you provide a comprehensive development environment for learners to grow their coding skills. Each lab will open to a browser based code editor where students can test their coding skills against challenges defined by lab authors. When the student is ready, they may run the code to return a pass/fail for each challenge. Code labs will be released with support for the following languages:
-	C 
-	C# 
-	Go 
-	Java 
-	PHP 
-	Python 
-	R 

**New Note Fields**

Notes may now be left on the following entities from the details page. A notes dialog will also prompt when updating an existing entity.
-	Organizations. 
-	Cloud Credentials Pools. 
-	Cloud Subscription Pools. 

**LOD Improvements and Fixes**
-	Support for AWS EventBridge and Backup added. 
-	LTI 1.3 integration now supports multi-domain instances of Canvas LMS. 
-	Virtual Machines can now be located and added to lab profiles by Virtual Machine Profile ID. 
-	Updated compatibility between the transfer lab instances feature and the multiple active instances per user feature. 
-	Cloud Security Reviews may now simultaneously  be requested for both parent and children lab profiles by selecting the Include Children checkbox.  
-	Updated the error message received when lab launches for an organization exceed the organization wide limit. 
-	ID is now available as an output option when searching for lab series. 
-	Type text will now function correctly for Enhanced Session Mode VMs without clipboard redirection enabled. 
-	Removed the Show Navigation Bar option from the Advanced lab settings. 
-	Fixed a scrolling issue when lab developers that occurred when arranging activities. 
-	Fixed a bug preventing the Show Detailed Results toggle from displaying on newly created scored labs. 
-	Fixed a bug preventing lab developers from saving changes to their account information. 
-	Fixed a bug that prevented saved labs from resuming. 
-	Fixed a scrolling issue when lab developers were rearranging activities. 
-	The Move Up/Move Down buttons are now populated when adding new scripts to an activity. 

## <u>Released January 16, 2021</u>

**Activity Based Assessment Outcomes**
Outcomes offer adaptive learning experiences based on the result of an automated activity or question. This allows lab authors to provide additional guidance if a student were to answer a question incorrectly, or move the student forward at an expedited pace if the student answers correctly. An outcome consist of an event, condition, action, and target. 

- Event: When a question is Answered or Evaluated, or when a script is Evaluated.
- Conditions: 
	- Correct
	- Incorrect
	- Correct or Incorrect
	- Answer = (Question only)
	- Score Value =
	- Score Value >
	- Score Value >= 
	- Score Value <
	- Score Value <=
- Actions: Can set either a variable or progress the student to a different page within the lab.
- Target: The variable to set or page number the student will be forwarded to.

**AWS Service**
- Cloud Formation Deployments will now reflect of the name of the Cloud Formation Template, allowing for custom naming. Special characters will be removed and spaces replaced with short dashes.
- AWS *Retry Cleanup* will now use the same logic to renew the account as when a lab is torn down.
- There is now an AWS Bulkhead Status display at the top of the AWS host page. This shows current operations impacting the AWS host.
- Fixed a naming conflict when using two AWS cloud formation templates in the same stack

**Automated Activity Output**
- Automated Activities now have the option to disable output to the lab user. This feature will default to showing output to the user, but can be disabled, so that the user only sees the Correct/Incorrect Answer Feedback.
- When a script fails due to a scripting error or platform error, we will now note it on the lab instance details page. It is also available under ActivityResults > ScriptResults in the lab Details API call.

**LOD Improvements and Fixes**
- Cloud resource groups will be checked by default when creating a lab profile using inheritance.
- When creating a lab profile from the template gallery, the org selection will now default to the first org managed by the lab developer.
- Updated the error message for labs left in a starting state for more than thirty minutes.
- Added a feature that allows admins to edit the number of days a lab may be saved for individual lab instances.
- The automatically prompt user to extend time feature now honors an organizations "Maximum Lab Extension Hours" value.
- URL encoding in IDLx will no longer under certain circumstances double encode image titles and links.
- Fixed a bug that prevented subsequent labs from launching against an AWS account after a nearly blank lab is torn down.
- Assigning a background cloud deployment now persists when adding a resource template simultaneously.
- Fixed a bug that prevented API Consumers with LTI 1.3 integration from correctly provisioning a JWK based on the Client ID.
- Incoming LTI 1.3 tokens will now be recorded to the lab instance details page for better visibility.

## <u>Released December 4, 2020</u>

**External Instruction Service**
- Optimizations have been made to support upcoming changes in ADO and GitHub, to change the primary branch name from Master to Main.
- Optimizations have been made to remove invalid webhooks in ADO repositories, when syncing external instructions with a lab profile. 
- Optimizations have been made when syncing a lab profile with an ADO repository and the repository belongs to an ADO project that has been synced with other lab profiles. 
	
**LOD API now supports a new parameter in the Launch call; maxSaveDays**
- This parameter allows an organization to set the number of days a student may save their lab, subject to the contracted configuration on the API consumer.

**ABA Display and Output Options**
- Basic Markdown can now be used in Correct Answer Feedback and Text fields of Activity Based Assessments. Emojis, Images , Bold, Italic, Strikethrough, Bullets, Numbers, and Headers are all supported. Characters may be escaped as needed using ``` \``` just prior to the character. 
- When ABA feedback or output from an activity is returned, the output will be displayed under the evaluation button when On-Demand evaluation is enabled.
- When enabled, the evaluation button for Task Lists can be configured to display over or under the lists of tasks in the lab instructions.
- Removed incorrect invalidation message when configuring an ABA Task List.
- Task list sort order is now properly reflected in the lab profile edit instructions preview pane.

**AWS Improvements**
- AWS output tokens are now properly shown on first display in Hyper-V and vSphere lab profiles.
- Improved logic when tearing down multiple AWS Cloudslice lab instances.

**LOD Improvements and Fixes**
- Lab Series can now be scheduled for disablement at a specified time and date. The labs will no longer be available to launch after the series is disabled.
- Fixed a typo on the pre-instance dashboard when clearing instances.
- Lab profile details page hardened against application error when lab series is null.
- Terms and Conditions are now linked in the footer of Lab on Demand.
- Fixed a bug resulting in users exceeding the maximum number of retakes allowed in a lab series.

## <u>Released November 20, 2020</u>

**AWS v2 Lab Host**
- AWS lab fabric support has been updated with changes that will improve stability, efficiency and scalability. 

**Access Control Policy Search Filter Added**
- A new filter has been added to Access Control Policies (ACP) search, to filter results based on the JSON content. This will provide the ability to quickly locate ACPs in Lab on Demand that use specific resources.
 
**Detailed Scoring Results**
- When a lab uses Activity Based Assessments (ABA) that are scored, it is now possible to show detailed score results to the lab user when the lab is scored. This option is configured in the Activity editor within the lab profile. 
 
**Activity Based Assessment Script Order**
- It is now possible to change the order of scripts when an Activity Based Assessment (ABA) has multiple scripts. Changing the order of the scripts in the UI also changes the order that the scripts will be executed. 
 
 
**Shared Lab Improvements**
- When a Shared Environment lab is cancelled, a warning is now displayed to notify the user that all participant labs will be cancelled. 
- When setting a lab to be a Shared Class Environment, the setting to save/cancel labs when the Last Activity threshold is exceeded, is now unchecked. This will prevent participant labs from being cancelled when the Shared Environment is cancelled due to inactivity. 
 
**LOD Improvements and Fixes**
- Added a new IDLx replacement token that shows the region where a cloud resource group is deployed.
- Activity Task Lists now list results in lab instance details page.
- Fixed a bug that prevented the Override Client Landing Page from displaying when a cloud platform or virtualization platform was not configured on the lab profile. 
- Fixed a bug that prevented a scored lab created via the save as function from properly inheriting scoring information.
- Fixed a bug causing errors when viewing, modifying, or exporting lab manuals after exporting and importing an AWS lab series.
- Fixed a bug that prevented the Enable Navigation Warning setting from working in some lab configurations. 

## <u>Released November 6, 2020</u>

**Support Chat**
- Lab on Demand now has a support chat option on the Admin site, as well as in the lab client. Users can initiate a chat session with our Support Team. This feature is enabled by default for all organizations, but it can be disabled if needed from the organization profile. Chat transcripts are stored in a support ticket, and a copy is emailed to the user.

**Lab on Demand legacy Flash and Silverlight Machine Remote Controllers Removed**

Lab on Demand legacy Flash and Silverlight machine remote controllers have been removed. 

- Any students still using Flash or Silverlight machine remote controller are encouraged to migrate to the HTML5 machine remote controller. Connectivity requirements for the HTML5 controller are available in our [Connectivity Requirements documentation](https://docs.skillable.com/tms/connectivity-requires.md).

**Disk Inspection Permission Adjusted**

The permissions required to inspect disks in Lab on Demand have been adjusted. 
- Inspection of a disk on a datacenter is now based on viewing rights on the datacenter.
- Inspection of a disk on a file share is now based on viewing rights on the file share.
- Inspection of a disk on a lab host is now based on viewing rights on the lab host.

**API Consumer Configuration**
- A new API Consumer configuration option has been added on API Consumer profiles for exams.

**LOD Improvements and Fixes**
- Mouse cursors in Hyper-V based labs will now dynamically change when resizing windows, while hovering over a text field, and selecting anchor points. 
- More flexible API configurations by allowing presets to be adjusted.
- Virtual machines can now be renamed when saving a new lab profile from a running lab instance.
- Improved Task Tracking behavior when using in conjunction with Includes.
- Updated verification message when deleting cloud subscriptions pools.
- Fixed a bug that improperly appended title information to container labs.
- Fixed a bug preventing ABA scripts from appearing in lab profiles created from the template gallery.

## <u>Released October 16, 2020</u>

**Cloud Watchdog**

The Cloud Health Monitor Service has been improved and given a new name. The service is now called Cloud Watchdog. It now performs better and more efficiently than the Cloud Health Monitor Service.  The service works in multiple stages:
- Stage 1 - Find service: Finds issues and logs them.
- Stage 2 - Remediation: Resolve issues found in stage 1, delete resources that failed to tear down if needed.
- Stage 3 - Report: Report issues in Health Check emails if necessary, and update cloud subscription pool Health Check UI
    - Features include:
        - Health Checks now apply to CSS labs, the same way they applied to CSR. 
        - Health Checks have two functions; checks for orphaned resources are a frequent rate, and checks for subscription configuration issues such as invalid credentials or expiration, at a longer interval. 
        - Health Check intervals have been updated to check every hour/day/week.
        - If an issue is detected, the subscription owner listed on the subscription pool will receive an email with a list of the issues found, as well as a link to the associated pool. 
	
**Life Cycle Action Inheritance**

Life Cycle Actions (LCA) can now be inherited on child lab profiles. Child lab profiles can also use different LCAs than the parent lab profile, by disabling LCA inheritance on the child lab profile. Child lab profiles have a checkbox on the LCA tab to enable inheritance on the LCAs from the parent lab profile.

**Multiple API Keys for API Consumers**
- API consumers now support creating, disabling, expiring, and revoking API keys.
- Manual key rotation available, add a new key and mark the old one to expire after a set period of time.
- Keys can be named to describe intended purpose.
- Keys can be copied to clipboard with the click of a button without exposing the key.

**LOD Improvements and Fixes**

- New lab profile search filter "Allow Multiple Active Instances per User" allows you to filter on if a user can launch more than one instance of a lab. 
- Clients and internal staff will now see the price of labs and series after acquiring the Price viewing (by organization) permission.
- The Launch API call email parameter now how a 256 character limit (previously 50).
- The "Let's open a lab window" page won't be available after the lab has been completed, cancelled, or timed out.
- When choosing a particular cloud subscription to launch a cloud lab, only subscriptions in the pool configured on the lab profile will be shown. 
- Updates to virtual machines, including differencing disks, will be blocked when a snapshot is detected on the VM due to incompatibility. If needed, the snapshots may be removed to restore differencing functionality. 

## <u>Released October 2, 2020</u>

**Enhanced Lab Saving**

- As part of the New Lab Developer Experience, a new save dialog window has been introduced into the Lab on Demand Lab Client. Lab Developers will be able to update and create new lab profiles by selecting _Save_ from the hamburger menu.
 
    - Update the number of processors and RAM on virtual machines right from the lab instance, no need to relaunch.
    - Improved workflow when capturing differencing disks and committing container  changes. 
    - Easily create new lab profiles by specifying the RAM, Processor count, Number, Name, Description, Organization, Expected and Maximum Duration.
    - Dynamically create new lab series or select existing ones for assignment when saving  a new lab profile.
    - Save current lab instance with no more clicks than before.
 
**Cloud Subscription Name Replacement Token**
- A new lab token has been added for Azure CSS labs to show the cloud subscription name. This can be used in lab instructions, Activity Based Assessments or Life Cycle Actions.
 
**LOD Improvements and Fixes**
- Updated translation on the _Next_ and _Previous_ buttons when using German in the lab-client.
- Fixed a bug that caused the number of credential pools to be inaccurate on lab profile details pages.
- Fixed a bug that prevented some fields from being displayed during a lab profile import. 
- Fixed a bug that allowed configuring multiple virtualization platforms in a lab profile while editing or creating a lab profile. 
- Fixed a bug that prevented adding a second script in an automated activity. 

## **Released September 3, 2020**

**Lab Profile Save As**
- When using _Save As_ on a lab profile, to create a new lab profile or a child lab profile, there are now options to change the organization and lab series in the prompt. This only affects the new lab profile and does not change the parent lab profile's lab series or organization.
- When a new lab profile is created using _Save As_, if the user performing the task does not have permissions to interact with different network types, the networks on the lab profile will be downgraded to a private network and a note will be left on the lab profile to specify which networks were downgraded. Users must have permissions for Public IP networks, as well as Web Access (NAT) networks in order to clone them into a new lab profile. 
 
**Instructions Modified By**
- When a lab profile's instructions are edited, a timestamp is added to the lab profile at the bottom of the page for Instructions Modified.  This notes the date/time, as well as who modified the instructions last. 
 
**Inline Virtual Machine and Container Terminals**
- It is now possible to display a Virtual Machine or Container Terminal inline with the lab instructions. This allows the lab to launch in a single window, showing the VMs and terminals only where the lab author specifies in the lab instructions. You can enable inline VMs/terminals by marking them as hidden from the student on the lab profile virtual machines tab, and then inserting them into lab instructions using @lab tokens. 
 
**LOD Improvements and Fixes**
 
- Updated VM OS identifier list to include _Red Hat Enterprise Linux 8 (64 bit)_ and _Windows Server 2016 or later (64 bit)_.
- Updated translation when using German in the lab-client.
- When searching Lab Series Assignment, more refined Max RAM and Total Ram output options based on lab completion status are displayed. Only labs marked Complete will impact these values.
- When saving a lab profile that previously required a security review, but no longer needs one, we will no longer leave a security review invalidation note on the lab.
- The VM import options will no longer appear on the Lab Profile Details page for users without Lab host viewing permissions.
- Fixed a bug preventing the creation of AWS pools in select configurations. 
- Fixed a bug that prevented Evaluations from displaying on scored labs. 
- Fixed a bug that prevented ABA groups from displaying in a standalone lab manual. 
- Fixed a bug that prevented _Blocks page navigation_ until evaluated from working properly in automated activities.

## **Released September 3, 2020**

**Activity Based Assessments(ABA) Activity Groups**

ABA Activity Groups allow question and automated activities to be grouped together so that they may be managed as one unit. Some of the benefits of this approach include:
- Activities can easily be sorted into groups and the order chosen by the lab author. A group is then inserted into the instructions using one @lab replacement token.
- Drop a group into your instructions and allow the platform to handle displaying individual activities. As new activities are added to the group, there is no need to update the IDLx markdown.
- Activities can be randomized when displayed to a student with the click of a button.
- The number of activities to display from each group can be specified by the lab author. This allows the author to create a pool of activities to draw from, further randomizing the assessment between students. Scoring will be normalized to a value specified in the group when this option is enabled.
- A new option to consolidate evaluation buttons has been added. Instead of displaying an individual "Check" or "Evaluate" button for every single activity within a group, a single button that will perform on-demand evaluation for the entire group may be displayed.
- Additionally, the answers to multiple choice questions can be displayed in a random order in both activity groups and standalone activities.

**Un-assign Cloud Credentials**
- A new button is now shown in the lab client next to the cloud credentials to un-assign the credential from the user it was assigned to when the lab launched. This button is only visible to users with permissions to edit the cloud credential pool. When the credential is unassigned, it is immediately available to subsequent lab launches for labs that use the credential pool.
 
**LTI 1.3 Improvements**
- Select LTI 1.3 claims are now available as replacement tokens in labs. The list of available claims and tokens include (case sensitive):
    - context_id = @lab.Variable(LtiContextId)
    - context_label = @lab.Variable(LtiContextLabel)
    - context_title = @lab.Variable(LtiContextTitle)
    - roles = @lab.Variable(LtiRoles)
- Fixed a bug resulting in an invalid launch when a global custom claim is provided in the Canvas developer key.
- Upgraded to Httpclientfactory library when launching labs and accessing deep links.

**LOD Improvements and Fixes**
- Whitespace is trimmed when configuring credentials for Cloud Subscriptions and Cloud Subscription Pools.
- Cloud fabric VMs will automatically target a resource group when added to a lab profile.
- Storage fields removed from subscription page when not applicable.
- Removed erroneous label on "Choose File" dialog when adding resources.
- Removed external class link from class monitoring page when accessed through the API.
- Fixed a bug that caused a cloud subscription to display on a lab profile details page after the cloud platform was set to none. 
- Fixed a bug preventing a cloud lab from launching after adding a non-cloud lab parent and inheriting environment.
- Fixed a bug where the target of an automated activity was lost upon export/import of a lab profile.
- Fixed a bug that would cause images to disappear in a lab that had been exported/imported.


## **Released August 22, 2020**

**Multi-Instance Labs**
Labs can now be configured to allow users to launch and access multiple instances of the same lab profile at any given time. Upon launching the same lab twice using a specially configured API consumer, users will be presented with the option to open an existing lab instance or create a new lab instance. From this screen, they will also be able to save and cancel previous instances of this lab.
 
**Azure Virtualization**
Several optimizations and improvements have been made for Azure virtual machines (VM). 
- Azure hosted VM labs show a connection quality (latency) indicator in the lab client. 
- Shadow monitoring is available for Azure hosted VMs.
 
**Lab Profile Scheduled Disablement**
Lab profiles now have an option on the Advanced tab to schedule a date and time for the lab profile to be disabled. Once it is disabled, it cannot be launched until the lab is manually enabled. 
 
**External Instruction Source**
External instruction source has been updated with performance enhancements for the following scenarios
- When a repository is synced with multiple lab profiles. 
- When multiple commits are made to the content file in the external repository rapidly.
- When a repository is very large and synced with multiple lab profiles and the repository is updated rapidly.
 
**LOD Improvements and Fixes**
- When launching a lab using the Launch API call, MaxActiveLabs and MaxSavedLabs parameters will default to the maximum allowed by the API consumer when the values specified are greater than is allowed. (Out of range values were previously ignored) 
- Get/Update Lab instructions API calls will now work with child organizations of the organization listed on the API consumer.
- Updated Lab Manual link on the instance details page.
- VM profiles can now properly be sorted by number of vCPU (output option)
- ABA on demand feedback styling has been updated when displaying correct or incorrect answers. 
- The lab client no longer produces an erroneous error on the first attempt to save a lab.
- Short answer exact match questions will now ignore leading and trailing spaces when scoring the given answer.
- When a lab is disabled, it no longer displays in the Deep link modal dialog. 
- Fixed a bug that occurred when saving non-cloud labs from saving when edited by a user without cloud permissions.


## **Released August 7, 2020**

**External Instruction Source**
- When an error occurs between the lab profile and the external instruction source, the error message is now displayed on the lab profile details page. A note will be displayed at the top of the page to indicate that there is an error. 
- External instruction source configuration messaging has been updated to not mention any specific external instruction sources. 
- When configuring a lab to use external instructions, a warning will now be displayed if the repository exceeds the maximum repo size limit (500mb) or if the repo is getting close to the limit.

**Search Filters and Output Options**
- Search filters have been added for _Was Launched_ and _Was Not Launched_ to the following search pages:
    - Find Cloud Credential Pools
    - Find Subscription Pools
    - Find Organizations
    - Find Lab Series
    - Find Lab Profiles
- A new output option has been added to the Find Lab Profiles search page. 
    - number (#) networks is now available as a filter and output option.
- A new output option has been added to the Find Organizations search page. 
    - _Parent_ is now available as an output option.

**Additional API Options**
- We have two new API commands. A parameter of id can be used to specify the lab profile.
    - _GetLabInstructions_: returns the IDL-MD instructions of a lab profile as a string. 
    - _GetLabInstructionsPackage_: allows you to download the IDL-MD instructions of a lab as a binary file.
- We have added two parameters to the Catalog API Call.
    - _LabSeriesID_: will limit results to the Lab Series specified.
    - _organizationID_: will limit results to the Organization specified The Organization ID is the integer at the end of URL when visiting the organization page in LOD. For example, https://labondemand.com/Organization/3 , the organization ID would be 3.

**Cloud Slice Geolocation**
- Cloud Slice labs can now be geolocated to launch in the cloud region that is physically closest to the lab user. 
- In addition to IPv4 geolocation services, LOD can now process IPv6 IP addresses during the lab launch process. 
 
**Upgraded Instructor Monitoring for Hyper-V Labs** 
- The instructor monitoring experience has been upgraded with the following features:
    - Better screen refresh rates provide a smoother view of what is happening in the lab.
    - Works with Enhanced Session Mode.
    - Allows instructors to see the mouse cursor of the student.
    - When taking control, students and instructors will see each other’s initials next to their respective cursors in real time.

**LOD Improvements and Fixes**
- The _My Labs_ link in LOD has been replaced with _Dashboard_. When logging into Lab on Demand, lab developers will be directed to Dashboard instead of the Admin page.
- Cloud Resource Templates no longer display the description in the Resources tab of the lab client for Cloud Slice labs. 
- The sort order of resources configured on the Advanced tab of a lab profile are now reflected in the lab client. Subsequent changes to the sort order are reflected in the lab after the lab has been reloaded.
- Updated vSphere Activity Based Assessment logic to be more resilient when scoring.
- LTI 1.3 can now provide a status of complete/incomplete for labs that do not have any scoring. 
- Updated localization on virtualization set up screen to localize all text displayed.  
- Class monitor pages now default the layout to display lab instances in small tiles, instead of a list view.
- Updated logic when detecting windows for cloud slice split view results in greater accuracy when determining whether an interstitial page should be shown.
- Added the ability to remove an expiration date on a cloud subscription in a Subscription Pool. 
- Fixed a bug that caused an application error when a lab tag is deleted while a lab profile that uses the lab tag is being saved.
- Fixed an issue that caused an application error when viewing a lab instance details page, from a lab profile where the cloud tab was edited while there were active lab instances. 
- Fixed an issue that prevented saving some child labs that use a CSS subscription pool.
- Fixed a bug that hid the _Allow Setting Expiration Time_ drop-down menu when creating new lab profiles.
- Fixed a bug that prevented lab developers from adding VM profiles to a lab profile when the number of vCPUs did not exceed the limit.
- Fixed a bug that resulted in some extraneous text displayed next to the Force Check In link in the instruction editor.

## **Released July 10, 2020**

**Multi-fabric Sequencing**
Lab profiles have a new option on the Advanced tab, to configure lab fabric build sequence. This allows labs that contain multiple fabrics to control which fabric is built first or if building can occur simultaneously. Lab fabrics can be built virtualization then cloud, cloud then virtualization or parallel to each other. 
 
**Shared Labs**
Lab authors can now choose whether a shared lab environment will automatically launch when a participant lab is launched or if an instructor will first need to launch the shared environment before participants are allowed access. Automatic launching is enabled by selecting the checkbox next to the shared environment role on the advanced tab of a lab profile.
 
**LOD Improvements and Fixes**
- Variable output and text replacements will be rendered in the lab client immediately upon any creation or update.
- A read only copy of the instructions is now available via the edit instructions link in lab profiles with externally managed instructions. This allows authors to utilize the recently released Replacements feature as well as manage replacement tokens and activities.
- The connection quality indicators in LabonDemand and the lab client have been updated with new values to better align with the recently implemented changes in how latency is calculated. 
- Total score, passing score, and passed results are now displayed on the lab instance details page of scored labs.
- LTI 1.3 Deep Linking is now available for Moodle.
- Fixed a bug causing select browsers/OS combinations to loop through the launch process for cloud labs.
- Fixed a bug that prevented the close button from appearing in modal dialog windows.
- Fixed a bug that prevented the lab client from tracking progress when selecting tasks list configured in Git Integration and includes.

## **Released July 6, 2020**

- The Docs app has been updated with a search function in the top menu bar. This will search document titles, as well as the contents of available LOD and TMS documentation, and list any documentation that matches your search term(s).

## **Released June 26, 2020**

**Lab Latency**
- Lab instance average latency now filters out outliers that could skew the overall average of the latency value displayed in the lab client, as well as lab instance details pages. 
- Lab instance and lab instance connection history pages now show the latency deviation for that lab instance. Lab instance deviation is the standard deviation of all recorded latency values for the lab instance. A high standard of deviation indicates an inconsistent and potentially unstable network connection. 

**Azure CSS Improvements**
-  Lab instance details pages now show the cloud subscription instance that the lab used. Additional details are available for the subscription, including subscription state, pool, cloud subscription ID, enrollment account, state last changed, created and Azure management group. This will assist with management and administrative tasks.
- CSS Subscription pools Now have search buttons to view lab instances and Cloud Subscription Instances that are associated to the subscription pool.

**LTI 1.3 Deep Linking**
- Deep linking is now generally available for use with Canvas and Blackboard. Speak with your Account Executive to help determine if your LMS is LTI 1.3 compatible.

**LOD Improvements and Fixes**
- Cloud Slice labs will now launch an interstitial page to help with resizing and relocation if opened in a window or tab that cannot readily be resized or moved. 
- You can now search for API Consumers by specifying which lab series are available to them using the Available Lab Series and Available Lab Series Name filters.
- A note is now placed on the lab instance details page when the instance is canceled using the API cancel call.
- Fixed a bug that prevented enhanced users from saving a differencing disk to their organization storage.
- Fixed a bug that prevented a user with the proper permissions from being able to view lab tags that they have added to lab profiles. 
- Fixed a bug that caused an improper title to appear in the Network drop-down selector in the lab client.
- Fixed a bug that prevented a user with proper permissions from deleting a cloud resource template.
- Fixed a bug that prevented a lab instance from closing when using the split windows view.
- Fixed a bug that caused a VMware lab to fail to launch when ESX creates a folder that already exists.

## **Released June 12, 2020**

**IDLx Replacements**
- There is a new option in the IDLx @lab menu for Replacements. Replacements allow for text or regex find and replace. Replacements can be used to cleanup or extend existing instructions sources, potentially eliminating  the need for lab errata. 

**Azure CSS Improvements**
- Azure CSS Resource Group names have been simplified to be read more user friendly.
- Removed the Name field from Azure Enrollment Accounts. Only the Principal Name is displayed.
 
**LOD Improvements and Fixes**

- Per hour pricing is now displayed on lab profile details pages and returned in a LabProfile and Catalog API calls. 
- When a cloud based lab inherits the environment from another lab, the virtualization and cloud platforms are now disabled.
- Users can now choose to cancel a lab instance directly from a running lab when saving their current lab would otherwise exceed the number of allowed saved labs configured on their account.
- When starting a virtual machine in a running lab instance, the message "There is not enough available memory to start this Virtual Machine. Please try again later." will appear when their isn't enough RAM on the host.
- The DeepLink URL is now displayed on API Consumer page.
- Dark theme updated so that autofill fields match other text fields. 
- Updated outgoing TS1 notification to include the reason and user org when an API launch fails.
- Search filters are now shown in alphabetical order when selecting from the add filter drop-down menu.
- Cloud hosted VMs no longer take Datacenter availability into account.
- Themes applied to the lab will now render when viewing the instructions through the Lab Manual view.
- When lab instructions contain a non-breaking space, it will no longer be parsed and displayed in lab instructions or in IDLx syntax such as code blocks.
- Additional logging of API errors has been added to the API Error Console to provide more information about the error that occurred. 
- Fixed a bug that prevented IDLx sections with variable dependencies from showing/hiding in a Lab Manual. 
- Fixed a bug resulting in an error when a description is provided through an LTI 1.3 launch.
- Fixed a bug that prevented ACP enforcement on a lab profile with specific user permission configuration.
- Fixed a bug that caused an application error when viewing a lab instance for a lab profile where the cloud platform is changed on a lab profile while there are running lab instances. 
- Fixed a bug that would populate CSS settings on the Cloud tab when a lab was configured for CSS, changed to CSR and then back to CSS. 
- Fixed a bug that prevented Expected Cloud Cost to be displayed when printing or exporting lab profile search results. 
- Fixed a bug that prevented labs from displaying when the lab profile is configured for French language.


## **Released May 29, 2020**

**Lab Instance Transfer**

- When permitted, students, instructors, and lab developers can transfer their lab instance to one another using email. This setting can be turned on at the organization level. LOD administrators will also be able to swap lab instances between users using a Transfer console available through the lab instance details page.

**Lab Instance Time Extension** 

- When permitted, students and/or instructors can be allowed to extend their lab instance via the pencil icon next to the lab timer. When the icon is selected, they will be presented with a calendar to set the new expiration date for their lab. The maximum amount of time that the lab can be extended is configured on the Organization that owns the lab profile. Once a maximum extension time is set, a drop-down menu in the lab profile will have three options to select who can extend their lab. 

    The options consist of:
    - Not Allowed
    - Allow only instructors to extend lab expiration
    - Allow users to extend lab expiration (includes instructors)

**Activity Based Assessment (ABA)**

- There is a new ABA option for both Question and Automated activities that allows  page navigation to be blocked until the student answers or completes the activity correctly. This feature will be very beneficial for challenge based lab scenarios.

- Fixed a bug that prevented multiple answer ABA activities from displaying properly in a task list. 

**Evaluations**

- When creating or editing an Evaluation, there is now a setting labeled Allow Skipping. By default, Evaluations will allow skipping, but it is now possible to disable the option to skip an evaluation, by unchecking the Allow Skipping setting.

**Improved Error Messaging** 

- We have updated error messaging to better indicate why a lab cannot be launched. The new messages include:
    - All available hosts have hit a launch throttle limit.
    - A host with sufficient RAM could not be found.
    - A host with access to all required virtual disk files could not be found.
    - A host with sufficient local storage could not be found.
    - A public IP address is not currently available.
    - A host with an available external container port is not currently available.

**API Error Console**

- A new console for tracking API launch errors is now available under the Lab Instances tile. This will allow LOD and organization admin to quickly identify the following issues that students may encounter when trying to launch a lab through the LOD API. Note the values in parentheses are only placeholders and will likely be different depending on the resources requested during the launch.
    - A host with sufficient local storage could not be found.
    - This lab is not currently available for launch via API. It is awaiting security review.
    - Sorry, you have taken this lab the maximum number of (3) times.
    - User has too many active labs (2).
    - Student is already using too much RAM to launch this lab (max 100 GB).
    - External API integration has reached the maximum number of concurrent lab instances (1000).
    - API consumer is using the maximum amount of allowed RAM (1000 GB).
    - The maximum number of current labs for this lab profile are currently running (10).
    - The user's organization currently has the maximum allowed active labs (300).
    - The user's organization is currently using the maximum allowed amount of RAM (800 GB).
    - The maximum amount of RAM for labs belonging to ABC Learning Co. is currently in use (1200 GB).
    - The maximum number of labs that belong to ABC Learning Co. are currently running (800).
    - The maximum number of current labs for this lab series are currently running (30).
    - The user's organization is currently using the maximum allowed amount of RAM (1200 GB).
    - Class has reached the maximum number of concurrent lab instances (30).

**Improvements and Fixes**

- Updated markdown to HTML parser. This update allows better integration with Github flavored markdown.
- The number of results displayed on an event's homepage can now be set when configuring the event.
- The number of concurrent instances allowed per user can now be set with the API parameter maxActiveLabs.
- Added Win Shortcut key to the commands menu (lightning bolt)
- Activities and LCAs are now saved into new lab profiles created from a running lab instance.
- When configuring a lab profile that uses Azure or AWS as the virtualization platform, the tabs are re-ordered in a more intuitive order so that a lab developer can configure the lab one tab at a time, from left to right.
- Validation has been added to VM profiles to ensure that a network adapter is added, when creating a new Azure VM profile or editing an existing profile.
- Corrected typo in lab instance sharing tool tip and also Container port unavailable error message.
- When creating or editing a VM profile that uses AWS as the platform, unsupported checkbox options have been removed from the bottom of the Basic Information tab. Removed options include: Host Integration Enabled, Use Enhanced Session Mode, and Enabled Dynamic Screen Resizing.
- When creating or editing a VM profile that uses vSphere, AWS, or Azure as the platform, unsupported checkbox Use Enhanced Session Mode has been removed.
- VMware VM display names are now limited to 64 characters.
- The Zoom slider will move above the tab labels in the lab client when long custom tabs are configured on the lab profile or the slider would otherwise overlap the tabs.
- Added a loading screen to lab profiles that have a hidden VM and no Cloud landing page.
- Improved resilience during the Differencing Disk process when capturing very large virtual machines.
- In addition to standard PKCS#1 keys, LTI 1.3 now supports PKCS#8 keys provided by Blackboard for launching and scoring labs.
- Fixed a bug resulting in an error when searching for Lab Profiles by Expected Cloud Cost.
- Fixed a bug that allowed a user to continue using expired permissions so long as they used AAD to sign in.
- Fixed a bug that prevented the instructions from being carried over when saving a running lab as a new lab profile.
- Fixed a bug that caused an application error when force checking in lab instructions.
- Fixed a bug that prevented some applications from honoring line breaks when using Type Text.
- Fixed a bug that prevented Cloud Resource Templates from being saved, cloned, or deleted.
- Fixed a bug that allowed a lab to be pre-instanced from a disabled Lab Series.



## **Released May 15, 2020**

**Life Cycle Action**
- A new Life Cycle Action hook has been added to Lab on Demand. A script can now be run against a VM or Container when the lab is Tearing Down and the Blocking option enabled. This combination will allow the script to complete before tearing down the resources required by the script.

**Lab Instance Sharing**
- Lab instance Sharing is now available for Cloud Slice Labs.
- Fixed a bug preventing the validation of an email address when the character-case didn't match the value returned by the authentication provider.

**Lab Instance Monitoring**
- The Class monitoring page has been upgraded to include a grid layout that displays currently running labs. There are three different sizes of thumbnail to choose from and the layout can be toggled to the legacy layout when desired.

**Azure CSS and CSR Improvements**
- When a CSS lab profile is exported and imported, the subscription level settings (ACP and user permissions) are now preserved during the export/import.
- The subscription prefix setting on enrollment accounts has been moved to the CSS subscription pool, so that the prefix will be applied to all enrollment accounts in the pool.
- Reworked CSS resource provisioning so that resources deployed via Resource Templates are not blocked by the Access Control Policies configured in the lab profile. 
- Azure CSS labs are now subject to Cloud Security Review based on Access Control Policies. 
- Improved the way that Access Control Policies are applied in CSS labs to scope subscription and resource group ACPs appropriately. 
- Updated the naming convention on the LOD Policy Set in Azure, to include identifiers for the platform and type of Azure lab. A script will be ran to update any references to this in Life Cycle Actions and Activity Based Assessments. 

**Accessibility**
- Star rating evaluations are now announced by a screen reader and are keyboard navigable. 
- Added and corrected labels used by assistive technologies.

**Improvements and Fixes**
- Updated Snapshot feature to use an improved process for transferring files.
- In Azure and AWS labs the User Account name prefix is pre-populated with the text, User1-.
- LTI 1.3 Error messages are now properly presented in HTML instead of text.
- Updated logic in LTI 1.3 service to respect enabled/disabled status of an API consumer when it is set to integration testing status.
- Removed dialog that would be improperly displayed  when assigning an AWS user to a region when saving a new lab profile.
- Removed references to deleted lab profiles on Shared Environment Lab Profile pages.
- Fixed a bug that prevented the VLAN ID set in a VM profile from initializing on a lab host.
- Fixed a bug that caused some vSphere VM profiles to display the wrong OS version on the details page.
- Fixed a bug preventing variables from populating in the Intellisense menu while editing lab instructions in a running lab. 
- Fixed a bug preventing labs utilizing German language option from launching.

---

## **Released April 24, 2020**

**We are now LTI Advantage Complete Certified**

- LTI allows administrators to easily integrate labs into their existing LTI 1.3 compliant learning management systems.
In addition to more granular scoring and grading, LTI offers enhanced security utilizing OAuth 2 tokens and an improved authentication flow.

**Azure Cloud Slice Subscription (CSS)**

- There are now two variants of Azure Cloud Slice; Cloud Slice Subscription (CSS) and Cloud Slice Resource Group (CSR). CSS allows full access to an Azure subscription, to allow Azure training at the subscription level, rather than at the resource group level. This solution will be a functional replacement for Azure Passes for MOC courses. Cloud Slice Resource Group (CSR) has had no changes in functionality. For more information about CSS, read Enabling Azure Learning in the Post Azure Pass Era.

**Accessibility Enhancements**

Many accessibility improvements have been made to the lab client resulting in an improved experience for those utilizing assistive technology. Some of these enhancements include the following.
- Menu buttons are now 100% accessible using keyboard commands.
- Notifications, text fields, and status messages can now be announced by screen readers in real time.
- The colors used in Lab on Demand lab client  themes have been adjusted so that text is easier to read and differentiate from the background. All themes now meet WCAG AA guidelines.
	
**Lab Client Localization API Parameter** 

- Platform generated Dialogs, tabs, and menu items in the lab client can now be localized using the lang parameter during API launches. The available options include Chinese, English, French, Japanese, Korean, Portuguese, and Spanish.

**Lab Instance Sharing**

- Lab instances can now be shared from the hamburger menu in the lab. This allows those with permissions to share their lab instance with another individual. When sharing, an email will automatically be sent out to the email address provided. Optional features may be extended from the original user's account such as saving differencing disks and editing instructions. The share can optionally be set to expire at a specified time and date. Additionally, the lab instance share can be protected by an established authentication provider.

**Virtual Machine (VM) Profile Improvements**
- VM profiles now display the hard disk capacity on the details page. 
- Lab developers can now create VM disks up to 2TB in capacity, this was previously limited to 256GB.

**Improvements and Fixes**
- When exporting a lab profile that uses a vSphere VM with EFI enabled, that setting will now persist when the lab is exported.
- Increased security for authenticated launch links and introduced optional per user retake logic.
- Fixed a bug in the lab client that could prevent a lab from syncing with the server when the lab is configured for virtualization but does not contain any VMs.
- Fixed a bug in the lab edit page that prevented the minimum show time on Content URLs from being removed.
- Removed the validation warning when saving an Azure CSS lab without a Resource Group configured.
- Improved logic to require an Access Control Policy in Azure CSS labs when a user is given Contributor or Subscription Permissions.
- Updated tool tip in Cloud Subscription Pool Automation Settings.
- A column has been added to Lab Series details pages to identify the cloud platform that is being used in each lab profile. 

## **Released March 27, 2020**

**Lab Instruction Improvements**

- Lab instruction authoring has been improved to allow a function to show/hide lab instructions and lab instruction elements. Instructions and elements in Sections and code blocks can be shown or hidden based on the lab variable set via Life Cycle Actions, Activity Based Assessments, an IDLx textbox or an IDLx drop-down menu.
	 
- This can also work in conjunction with labs that use instructions stored in GitHub and displayed in the lab via a Markdown include. This allows the lab instructions to be displayed dynamically based on the variable set in the lab. For example, you could configure the drop-down menu to have 2 language options; en and fr. Then in GitHub where the lab instructions are stored you could create 2 copies of the lab instructions; one in English and one in French, with the lab variable value at the end of the file name. The lab user could then select en or fr in the drop-down menu in their launched lab, and the corresponding lab instruction file from GitHub would be displayed in the lab.

- Additionally, the variable can be selected with an API launch. This allows the lab to display a specific Section when the lab launches.

    - **Sections**: Sections are used to group lab instructions and elements together so they may be called up on and manipulated as one. This is done by assigning a lab variable that has been set via LCA, ABA, an IDLx textbox  or an IDLx drop-down menu.

    	> :::sectionName(variableName-variabelValue)

    	> section text or markdown elements

    	> :::

    - **IDLx Drop-down**: there is a new @lab token to add a drop-down menu to lab instructions, and assign multiple values to the drop-down menu. The values added to the drop-down become variables in the lab and can be assigned to IDLx sections as a way to show/hide lab instructions. The @lab token can be found in the @lab button when editing lab instructions or by using the syntax below.

    - **Dynamic Includes**: IDLx already supports displaying lab instructions stored in GitHub via a Markdown Include. That functionality has been expanded to use variables set in the lab to display lab instructions based on the drop-down menu selection. This requires the file names of the content in GitHub to have the variable value at the end of the file name, and a Section created in the lab instructions with a variable that has been set via LCA, ABA, an IDLx textbox or an IDLx drop-down menu.

        > **External repository file name**: 
        > 
        > `sample1-en.md`.
        >
        >**Include syntax with variable in file name**: 
        > 
        > `!instructions[(https://raw.githubusercontent.com/user1/sample1-@lab. Variable (language).md)`
        > 
        > In this example, the variable value is `en` and the variable name is      `language`. 
    
    These are not limited to language selections. Lab variables, Sections and code blocks can be used to show/hide content based on the lab variable. Another use case for this could be Choose your difficulty, where there are multiple versions of the lab instructions with varying difficulty levels and the lab user selects their preference and lab instructions are displayed accordingly.

**Improvements and Fixes**
- Updated Instructions Import Page Title to reflect general usage of IDLx.
- The background color and foreground color in the lab client now meets the minimum contrast ratio of 4.5:1. 
- Language now declared in HTML of Lab Client.
- Deprecated QR code for lab launches.
- Resource Template parameters are now preserved when cloning a lab using Save As or when a child lab inherits the cloud environment from a parent lab profile.
- Disabled API consumers will now be hidden on the lab series publish page.
- Tabs in the lab client now have an underline to show which tab is in focus.
- When launching a lab by clicking launch on subscription or launch on subscription pool, the correct dialog is now displayed.

## **Released February 28, 2020**

**Alt+Tab Shortcut Available in Commands Menu**
- The Alt+Tab keyboard combination is now available as a shortcut under the Commands Menu. This allows students to swiftly switch between two full screen applications in their lab instance. When switching between three or more applications, the shift key may be held while selecting the Alt+Tab shortcut to cycle through all open applications on Windows and select Linux virtual machines.

**Cloud Security Review**
- A Cloud Security Last Reviewed filter is now available when searching for lab profiles. The output will display the date and time that the last Cloud Security Review was completed.
- Access Control Policies can now be sorted by Requires Security Review.
- Never has been added to the list of available options in the Cloud Security Review Approval Expires filter when searching for lab profiles.

**Lab Variables Now Configurable by Lab Authors**
- Lab authors can now initialize lab variables from the very start of the lab. These can be used in Life Cycle Actions(LCA) as well as Activity Based Assessments(ABA). These variables are available in IDLx using @lab.Variable(name).

**Improvements and Fixes**
- Access Control Policies can now be sorted by Requires Security Review.
- Tooltips have been added to the Advanced tab of API consumer profiles, to describe the available options.
- Two new filters, Is parent of and Is child of, are now available when searching for organizations on Labondemand.com.
- Updated the root file path of resources on the Lab profile details page.
- Lab Tags are now returned when the LabProfile API method is called.
- Fixed a bug allowing students to launch an additional lab when they should have been limited by the number of retakes configured on the lab series.
- Fixed a bug preventing labs from launching when URL reserved characters are passed to the lab host as cloud passwords.
- Fixed a bug that prevented Last Activity and Last Console Sync from periodically 

---

## **Released February 14, 2020**

**Save As for Access Control Policies and Resource Templates**
- It is now possible to create a copy of an Access Control Policy (ACP) or Resource Template (RT) from an existing ACP or RT, by clicking Save As. This behaves similar to Save As on a lab profile. This will provide the creation of policies and templates in a timely manner without having to manually enter the same settings. 
 
**Cloud Security Review**
- Lab profiles that use cloud orchestration are subject to a cloud security review. Until a review is completed, the lab cannot be launched via TMS, API, LTI, or other outside Learning Management Systems. The cloud components that are used in lab profile must be reviewed for any security issues, such as: Access Control Policies, Resource Templates. Additionally, any changes made to the lab profile's Cloud tab will cause the lab to undergo a security review again before the lab can be launched. 
 
**Events**
- Start and End times can now be defined for an Event. Labs are available to launch only during this time period.
This will allow us to exercise greater control over cloud and virtualization resources.
 
**Improvements and Fixes**
- Architectural improvements have been made to increase throughput, stability, and resiliency in the LOD Platform.
- Lab Profile RAM is now calculated to include overhead from NAT network after adding or removing RAM from a VM profile belonging to the lab profile.
- The network required for Linux ABA scoring is now properly created when launching lab profiles that inherit content.
- Lab Profile ID is now an Output Option when searching for Lab Instances.
- Client Landing Page URL now accepts up to 512 characters, previously this limit was 256 characters.
- Cloud Credentials are now issued to lab instances according to expiration date, and then by creation date.
- There are two new result codes that can be returned when launching a lab via API. Result code 100 is returned when a user has launched the maximum number of instances for the lab profile. The was previously displayed as an result code of 0. Result code 110 is returned when a lab profile requires a security review.
- Select cookies for Labondemand will now be set to Secure with SameSite policy explicitly set to none.
- Added new logic to handle scoring and tear down of multiple labs when scoring stalls on a particular lab instance.
- Bug report, Tag, Theme, and Display Delay fields now included when exporting lab profile.
- The LabClient service has been updated to .Net Core 3.1.
- Fixed a bug where the browser would open a very small window when launching container labs.
- Fixed a bug that resulted in the Display Delay being shown while resuming labs. Display delay messages are no longer displayed when resuming a saved lab.
- Hyper-V Virtual Switches are now removed when the lab instance that spawned them is no longer running.
- Fixed a bug that prevented searching for child lab profiles using Access Control Policies.
- Fixed a bug that prevented Sign in History from displaying after modifying user's account.
- Updated missing fields in various Print and Export reports.
- Fixed a bug that prevented lab instances from going to the correct state when a lab is cancelled during the save operation.
- Fixed a bug that prevented a lab from being submitted for grading, when on-demand evaluation was enabled and then later disabled during lab authoring.
- Fixed a bug that prevented a lab developer from being able to create and find virtual machine profiles, if they didn't belong to an organization but they did have management over an organization.
- Fixed a bug that caused _Edit Instructions_ to show in a launched lab that uses GitHub or Azure DevOps as an external instruction source.

---

## **Released December 13, 2019**

**Improvements and Fixes**
- When making the Details API call, the EstimatedReadySeconds property is now the sum of the time it takes to launch the lab and the Display Delay configured in the Advanced tab of the lab profile.
- Fixed a bug that prevented a lab instance search from returning results when the lab profile contains special characters in the lab profile name. 
- Fixed a bug that prevented a lab from honoring the default selection on VMs when a new lab was created during differencing disk capture, or when creating a new lab using Save As and choosing the option to create new VM profiles.
- Fixed an issue that prevented lab series assignments from being retaken when the lab failed to launch. Labs that fail to launch no longer contribute to the users maximum allowed retakes. 

---

## **Released November 22, 2019**

**Evaluation Star Rating Scale**
- A new option has been added to Evaluations, to allow the use of a star rating scale. 

**Theme Options**
- Lab on Demand has been updated with a universal theming engine. Instead of having separate theme settings for the lab client, authoring tools, and admin tools, one theme setting now applies to all areas of the platform. No matter where you set the theme, it will apply across the entire platform. This also means that all the themes previously only available in the lab client are now available in the LOD admin site.

**Improvements and Fixes**
- Cloud subscription details pages now have a Find Lab Instances link to search for all lab instances associated with the cloud subscription. 
- When a resource is added to a lab profile on the Advanced tab and the Lab Manual box is checked, and there are no IDLx instructions, the lab will default to the instructions tab.
- Fixed an issue that prevented folders from appearing in alphabetical order in the storage browser when there is leading or trailing white space in the folder name. The white space is now omitted from the name when it is saved. 
- Fixed a bug that prevented a parent lab profile from being deleted, when the child profile is deleted. 

---

## **Released November 8, 2019**

**VMware SATA Disk Support**

- It is now possible to use a SATA disk controller in VMware based labs.

**Improvements and Fixes**

- _My Labs_ page now displays the virtualization platform and cloud platform used for lab profiles in the _Favorites_ section.
- Special characters can now be added to cloud credential pools when adding credentials to a pool.
- Special characters can now be used in a password when creating or editing a user profile.
- When a lab profile uses a theme with custom CSS, it is applied to the lab instruction editor as well as the lab.
- When the portal window is closed on a Cloud Slice lab, portal links in the lab instructions will now reopen the portal window and direct it to the URL in the Portal link.
- When a user logs out of the AWS portal or closes the portal window, clicking the Portal link on the Resources tab of the lab instructions will now reopen the portal window and sign the lab user back in.
- VM thumbnail images are now a larger size to allow a better output on high dpi screens (4k/5k). Please note that the size on screen will not change, but will be scaled to display better on high resolution displays.
- Fixed a bug that prevented Imported From links on a lab profile or lab series note section from navigating to the profile/series that it was imported from.

---

## **Released October 25, 2019**

**Fixes and Improvements**
- It is now possible to add a virtual machine to a lab belonging to a different series. Previously, the VM chooser dialog was permanently filtered against the lab’s series. Now, this filter can be removed if desired. 
- Files and folders within storage management pages are now always sorted in alphabetical order.
- Life Cycle Actions now indicate if they are disabled without the need to edit the LCA.
- Fixed a bug that prevented search pages from functioning when using Internet Explorer.

---

## **Released October 18, 2019**

**Alphabetical Output Options**

- A sort button has been added to sort output options alphabetically. Clicking the sort button changes to alphabetical, and clicking again changes it back to the by relevance sort order. This does not change the sequence that the fields are display in search results. This only makes it easier to find options when enabling or disabling output options.

**Improvements and Fixes**

- Fixed a bug that prevented PowerShell from being available for ABA scripts in cloud/container hybrid labs.
- Fixed a bug that prevented a user profile image from displaying on the _My Labs_ page.
- Fixed a bug that prevented the cloud subscription pool name from displaying when launching a lab using the _Launch on Subscription_ button.

---

## **Released October 11, 2019**

**Enable Disk UUID**
- It is now possible to enable Disk UUID on vSphere VMs. There is a checkbox on the VM profile to enable this feature. 

**Disconnect from Labs**
- Lab profiles now have an option on the advanced tab to allow lab users to disconnect from the lab and keep the lab running. The disconnected lab will still count towards the user's active lab instances. 

**Improvements and Fixes**
- Updated text on lab profile details page to reflect external instructions, rather than Git Integration.
- Fixed typos on instruction source selection page.
- Fixed a bug that prevented some users with proper permissions from deleting files in cold storage.
- When using a filter for Key in a lab instance search, an error message is now displayed if you are searching with an invalid value (non-GUID). Enter a valid GUID allows the search to perform as expected and return search results. 
- Fixed a bug that prevented a virtual machine from being reverted, in a shared lab environment. 
- Disabling a lab series now disables labs that belong to that lab series from being launched. Labs that are disabled this way will not be included in the Catalog API call response. 
- Fixed a bug that prevented a theme from being applied to event room pages.

---

## **Released September 27, 2019**

**IDL Legacy Retirement**
- IDL legacy is no longer available to use in new labs. The option to use IDL (legacy) for lab instructions has been removed from LOD. IDL legacy labs that have not yet been converted to IDLx will be automatically upgraded on October 1.

**IDLx Page Titles**
- The next page button in lab instructions now displays the first header on the next page for all header sizes (H1-H6), instead of only using H1 headers on the next page button.

**Instruction Source from Azure DevOps (ADO)**
- It is now possible to use an ADO repository to sync instructions to a lab profile. Syncing instructions with an ADO repository allows lab authors to utilize version control in ADO, multi-author support, as well as centralized management of lab instructions in ADO. 

**Improvements and Fixes**
- Fixed an issue that prevented custom CSS from displaying correctly on some event pages. 
- Fixed a bug that prevented exam settings from being inherited in child lab profiles. 
- When editing cloud templates, validation logic has been updated to ensure that changes won’t break any labs that use the template. Safe changes are allowed, changes that would break labs are blocked, and changes that might impact labs require confirmation.
- VMware VMs can now be built using hardware version 14. 
- Fixed a bug that prevented lab profiles with containers from being imported. 
- Fixed a bug that prevented a network from being visible in the lab when it isn't connected to a VM.

---

## **Released September 13, 2019**

**Container Registry Accounts**

- Add any number of external registry accounts to LOD. This is useful if you have containers in a registry such as Docker Hub, and have multiple organizational accounts for managing your container images.
 
**Improvements and Fixes**

- Fixed a bug that caused an error to occur during lab launch, when the option in subscriptions to override subscription pool settings is disabled and use the subscription pool authentication settings instead. 
- Fixed a bug that could cause manually evaluated activities to be scored more than once. This issue did not impact automated ABA/PBT. 
- Fixed an issue that prevented some pages from being able to choose an organization when the organization profile had Assignable to Users enabled. 
- Fixed a bug that caused an application error when editing lab instructions of an AWS lab profile that does not have an AWS region configured.


---

## **Released August 30, 2019**

**Persist Container Changes**

- Containers can now persist changes, similar to how differencing disks work for VMs. Changes can be persisted to a new container image, new lab and container image or the current container images in the lab can be updated. This allows lab authors to configure the container image and save it, so that the configuration will be present on future lab launches that use that container image.

**Container Registries**

- LOD now supports creating custom container registries that are linked to an external registry, such as a private Docker Hub repository. When persisting changes to a container image, you can choose to save the changes to the custom container registry. This allows you to use containers defined in any registry you have access to in your labs.

**Improvements and Fixes**

- Fixed a bug that prevented networks from being saved to a new lab, when cloning a lab and reusing containers.
- Fixed a typo on cloud subscription authentication tab.
- Fixed a bug that prevented roles from being removed that were created by a lab user in a lab.
- Fixed a bug that would prevent resource deployment errors from being logged to a lab instance.
- Fixed a bug that caused hybrid AWS and Hyper-V labs to be stuck loading during launch.

---

## **Released August 23, 2019**

**Lab Client Improvement**
- The Lab client has been updated with memory optimizations for general stability and performance improvements.

**Active Lab Instances Search**
- A filter has been added to filter active lab instances by cloud platform.

**Fixes and Improvements**
- Fixed a typo on the tooltip for Introduction Content URL, on the Advanced tab of lab profiles. 
- Fixed a bug that caused an error to occur when printing search results from a container image search or a cloud subscription pool search. 
- Fixed a bug that prevented some fields from printing or exporting, on cloud credential pool search results. 

---

## **Released August 16, 2019**

**Lab with No Menu Options**
- When no menu items appear in the Lab Client’s main menu, the menu button will no longer be visible. This can happen when the lab doesn’t allow Cancel, or Save.

**AWS Improvements**
- AWS Amazon Simple Notification Service (SNS) service is now available to use in AWS labs. 
- AWS lab user account names will include a lab specific unique identifier. This will enable better auditing of activity in AWS labs, particularly in exam scenarios.
- Support for Amazon CloudWatch Events and Logs in AWS Cloud Slice labs.


**Improvements and Fixes**
- Fixed a bug that prevented concurrent ABA to perform in AWS labs. 
- Fixed a bug that would cause the number of available cloud credentials to display incorrectly.
- Fixed a bug that prevented low availability emails from being sent when a cloud credential pool meets the low availability threshold.
- A bug has been fixed that prevented launching a lab as a non-administrator from an internal Lab Series Assignment.



## **Released August 2, 2019**

**Find Lab Series Assignment Output and Filter**

- There is a new filter and output option for Lab Series Organization.

**Enabled Bug Reporting Filter**

- When performing a lab profile search, there is a new filter to display labs that have bug reporting enabled.

**Cloud Subscription ID Filter and Output**
- There is a new filter and output to display the subscription ID in search results for lab instances and/or cloud subscriptions. This was done to help identify where a subscription is used in LOD. 

**In-Lab Notifications**

- Long notifications now allow scrolling. This was done to prevent the close button from being hidden when a long notification was displayed in a lab.

**Token Aliases**

The following items in LOD are now referenced by an alias instead of an ID, in replacement tokens. This was done to make items in LOD more flexible and import/export without errors.

- IDLx activities 
- Cloud Resource Groups
- Cloud Templates
- Cloud Credentials
- Cloud Portal Credentials

**Credential Pool Import/Export**
- When importing a lab that has a credential pool associated, the  pool will now be preserved on the new lab profile during import. 


**Cloud Resource Groups Selected by Default**
- When creating a child lab profile, cloud resource groups from the parent profile will now be selected by default on the child lab profile. 

**Improvements and Fixes**

- Fixed a bug that prevented filing a bug report from a launched lab.
- Fixed a bug that would cause importing to fail when importing a lab profile from an older version of LOD.
- Fixed a bug that would cause importing to fail when the lab contained replacement tokens. 
- Fixed a bug that would prevent blocking web request LCAs to replace tokens when sent in a post/put body.


## **Released July 19, 2019**

**Private Networking in Container Labs**

- Docker containers are now able to communicate with other containers in the same lab instance using a private network. A container network is configured the same way as a VM in LOD -- add a network from the Networks tab and make it available to the container on the Containers tab. 
 
**Deleting Lab Profiles**

- It is now possible to delete a lab profile that has lab instances associated with it. Preventing the lab from being deleted in this scenario isn't necessary, now that lab profiles aren't deleted from the database. 

**API Consumer Configuration**

- Configuration templates have been updated to allow Default Max Lab Instances to be modified on a non-custom API consumer configurations (Per Instance, Per Series Assignment, and Concurrent Usage).

**Azure Resource Deployment Output Data**

- Azure resource templates can now be configured to output data from Azure, back to LOD in the lab instance data. This data can be displayed in the lab via @lab replacement tokens. This is helpful in scenarios when a student needs to RDP or SSH into a VM in Azure, or when information is needed about a deployed resource such as a storage account.  

**Improvements and Fixes**
- Fixed a bug that prevented the lab extension timer from being extended by the configured amount.
- Fixed an issue that could cause a lab to not reflect recent changes made. This issue affected a very small number of lab authors. 
- Fixed a bug that prevented Azure cloud slice labs from deploying resources in the background and allowing the lab to display before resources were deployed. 


## **Released July 12, 2019**

**Docker as a Lab Fabric**

LOD is adding a new fabric, to run labs in containers. Currently data centers have lab hosts to run virtual machines, but we will soon be adding lab hosts to run containers. This release of Docker containers is for internal use only and will be enabled for the public at a later date.

- Docker will be configurable on lab profiles, in the same drop-down where you would select Hyper-V or vSphere. 
- The user experience will be similar to Linux SSH labs, where there is no desktop UI for the student to interact with. 
- Running labs in containers results in labs that can be launched much quicker than a traditional VM-based lab. 
- Running labs in a Docker container will be particularly exciting for Linux labs. Linux environments will be ready for student use in a matter of seconds, instead of minutes. This is because each Linux sub-system does not need to be loaded per lab instance, as most of the files needed for the lab are already running on the Docker lab host. 
- Containers enable Linux labs to perform similar to a Windows-based VM with improved mouse support. 

- Docker fabric v1 will include support for:
    - Load balancing across hosts
    - Lab save/resume support
    - Multiple containers
    - Split window support 
    - Activity based assessments (ABA). 
    - Life Cycle Actions (LCA)
    - ABA and LCA in containers use Bash for scripting and scoring. Refer to the [Activities documentation](https://docs.skillable.com/lod/activities.md) for more information about Bash scripts.

**Exposed Ports in Docker Labs**
- Lab authors will now have the ability to reference host and/or port values independently of the overall address. Many applications reference addresses differently than the standard host:port syntax, so making the components available independently will allow maximum flexibility.
    - @lab.Container(alias).ExposedPort(exposedPortValue).Address 
    - @lab.Container(alias).ExposedPort(exposedPortValue).HostPort 
    - @lab.Container(alias).ExposedPort(exposedPortValue).HostName 

**Docker Resume Message**
- When a docker container lab is saved and resumed, the resume message now says  This shouldn't take long.

**Lab Display Delay and Custom Message**
- Lab profiles can now be configured with a time delay and a custom message, while the lab is loading. You can configured these options on the Advanced tab of a lab profile. This feature is available on all lab types in LOD (Hyper-V, VMware, Azure, AWS, Docker). This was done to provide a more seamless lab experience in labs when additional services are deployed when the lab is launched and are needed to be ready and displayed when the lab launches.

**Azure Lab Host Management Service Improvements**
- The Azure lab host management services has been updated with some improvements that will help improve performance, resilience, scalability and long-term maintainability. 
- Updated all API interactions to help cope with transient Azure service issues. 
- Moved to an Azure app service for better resilience, reliability and scalability. 
- Rebuilt on .NET Core, which will improve performance and maintainability. 

**AWS Improvements**
- AWS cloud subscription names now have a default prefix of Prefix-Platform Instance ID-Subscription ID. If a prefix is defined in the automation settings of a cloud subscription, the prefix will be appended to the default prefix. This was done to make subscription names more human readable, as well as helping to determine which account in AWS is associated with which cloud subscription in LOD.

**AWS Services**

- Support for additional AWS services have been enabled in LOD. These services can be used in labs that use AWS services.
    - AWS OpsWorks
    - AWS OpsWorks Configuration Management
    - AWS Secrets Manager
    - Amazon Athena
    - Amazon Cognito User Pools
    - Amazon Kinesis
    - Amazon Kinesis Analytics
    - Amazon Kinesis Firehose
    - Amazon Kinesis Video Streams
    - Amazon Route 53
    - AWS Step Functions
    - Auto Scaling Plans

**IDL (legacy) Exam Tab**
- The Exam tab has been removed from the lab profile editor. All legacy exams have been migrated to IDLx.

**Azure Cloud Subscription Improvements**
- Azure cloud subscriptions now have an option to enable billing reporting when editing an existing subscription or creating a new subscription.

**Improvements and Fixes**
- Cloud subscription pages now have a link to find lab instances for the subscription. This is helpful for determining the use of a specific cloud subscription within LOD. 
- Fixed a bug that would prevent a non-super user from being able to select Docker from the available virtualization platforms when creating a lab profile.
- Fixed a bug that prevented VMs from being cloned using Save As from a VM profile.

## **Released July 5, 2019**

**IDLx Improvements**

- Code Blocks have received minor changes. Clicking on the copy or type text icons trigger the expected behavior and clicking the code block itself will no longer copy or type text.

## **Released June 28, 2019**

**Improvements and Fixes**

- VMs that are not visible to the student but have the option for _Make lab instance data available inside virtual machine_ selected will no longer inject the username and password into the VM. This was done to prevent a hidden VM from being tampered with by the student. 

    ![](images/make-lab-instance-data-available-in-lab-highlighted.png)

- When a lab profile is deleted, it is now archived instead of purged from our platform entirely. This will preserve usage data, as well as speed up the deletion process. 

- Improved our host health check procedures to reduce the amount of time a student is stuck on the _connection lost_ screen after recovering from a network-related failure.

---

## **Released June 21, 2019**

**IDLx Improvements**

- Code blocks that contain multi line commands will now wrap to the next line, by adding `-wrap` when declaring the code block language. For instance `PowerShell-wrap`.

- Line numbers can now be added to code blocks, by adding `-linenums` when declaring the code block language. For instance `PowerShell-linenums`.

**Improvements and Fixes**

- Fixed a bug that caused @lab replacement tokens not to render in a lab when they were added to the lab instructions using a Markdown include from a GitHub RAW file. 

- Fixed a bug that caused users to be unable to be able to view subscription pool pages, unless they had a permission to view credential pool pages. 

- Fixed an issue that would cause some characters in a cloud credential to render as HTML. 

- Fixed a bug that would cause some developer files uploads to fail.

---

## **Released June 7, 2019**

**Improvements and Fixes**

- Fixed a bug that would prevent files from being deleted from a class after the instructor deleted the file from the Share Files section of the Monitor Labs page.

- Fixed a bug that caused the AWS region selection drop-down menu to display incorrectly on the virtual machine tab of a lab profiles, when using Internet Explorer. 

---

-->
