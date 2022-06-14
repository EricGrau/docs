## Lab Profile Settings

1. [Basic Information](#basic-information)
1. [Networks](#networks)
1. [Virtual Machines](#virtual-machines)
1. [Removable Media](#removable-media)
1. [Cloud](#cloud)
1. [Pre-Instancing](#pre-instancing)
1. [Life Cycle](#life-cycle)
1. [Availability](#availability)
1. [Tags](#tags)
1. [Advanced](#advanced)

### The following sections walk through each of the tabs located at the top of the Create Lab Profile page.

---

## Basic Information 

1. **Number:** Numbers are used in the title of the lab profile. 
1. **Name:** This will be the display name of the lab profile.
1. **Series:** Select the lab series that the lab profile will be associated with.
1. **Organization:** Select the organization that will own the lab profile and be responsible for maintaining the profile. 
1. **Virtualization Platform:** Select the virtualization platform that the lab profile will use. (Hyper-V, ESX, Azure, AWS, Docker or none.) Selecting _None_ will cause the lab profile to use the Cloud Client. 
1. **Code Lab Fabric**: Enable the lab to be use the Code Lab fabric. For more information, read [Code Labs documentation](/lod/code-lab.md).
1. **Parent:** A lab can optionally inherit some properties from a parent lab profile. Both the virtual environment (virtual machines, virtual networks, etc) can be inherited, as well as resources and content (manuals, scenario, objective, exercises, tasks, etc). Changes to the parent lab profile will be reflected in instances of this lab.
1. **Storage Reservation Per Instance:** This is the amount of storage that the lab scheduler will ensure is available before an instance of this lab is Launched on a lab host server. 
1. **Development Status:** Used to show lab profile development status. (In Development, Awaiting Verification, In Verification, Verification Failed, Complete.) Lab profiles in _Complete_ Development Status will be available for use, other development status' will only be available to registered lab developers. 
1. **Duration:** The expected amount of time it will take a user to complete the lab. After setting the duration, the maximum duration of the lab will be will be set to 150% of the duration. 
1. **Prompt user to extend time** by `X` Minutes when `X` Minutes Remain: automatically prompt the user to extend the lab time by a specified amount of time when a specified amount of time is remaining. 
1. **Language:** The language that the lab UI will be displayed in. This will not change the language displayed in the OS of any virtual machines used unless the virtual machine was configured to display a specific language. Language options include: Chinese (simplified), English, French, German, Japanese, Korean, Portuguese, and Spanish.  
1. **Level:** Sets the Level for the lab; this can be 100, 200, 300, or 400. 
1. **Evaluation:** Click to add an Evaluation to the lab profile. The Evaluation must already be created to add it to the lab profile using this button.
1. **Advertising Campaign:** Used to show introductory content while the lab is loading. This can be a video, PowerPoint presentation or anything accessible by a URL. 
1. **Description:** Used to provide more information about the lab profile. 
1. **Enabled:** Used to enable or disable the lab profile for use. If the lab is disabled, it will only be accessible to lab developers. 
1. **Enable Bug Reporting:** Allows bug reporting on the lab profile. Bug reports are collected on the lab profile details page by selecting **Edit** in the upper-right corner of the lab profile page. 
    - **Bug Report Email Address:** If this value is set, bug reports submitted by end users will be emailed to the supplied address. Notice that this field is not required in order for bug reporting and tracking to work. 
1. **Owner Name:** The name of the owner of the lab profile. 
1. **Owner E-mail:** The e-mail address of the owner of the lab profile. 

## Networks

To use network features, such as external internet access or communication between virtual machines, lab profiles must have a network created or inherit networks from a Parent lab profile. 

1. **Name:** Display name of the network.

1. **Description:** Used to provide more information about the network

1. **Type of network:** The type of network to be used by the lab profile. There are four options:

    >[!knowledge] VLAN IDs are configured differently for Hyper-V and ESX. The VLAN ID is set on the VM profile for Hyper-V and set on the Networks tab of the Lab Profile for ESX.

   - Private: private network (no internet access), typically used for communication between virtual machines. 

        - VLAN ID: Select automatic VLAN ID assignment or specify a specific VLAN ID. 

   - Web Access (NAT): internet accessible with NAT (network address translation)

        - VLAN ID: Select automatic VLAN ID assignment or specify a specific VLAN ID. 

        - Gateway address: specify the gateway address or use the default address of 192.168.1.1.

        - Subnet Mask: specify a Subnet mask or use the default Subnet Mask of 255.255.255.0. 

        - Enable DHCP: check to enable DHCP (dynamic configuration host protocol).

        - DHCP Start Range: enter the starting value of the IP range that will be available in the lab.

        - DHCP End Range: enter the ending value of the IP range that will be available in the lab.

   - Web Access (Public IP): internet accessible network with a public IP address

1. **Access Control List:** user to control how students use the web within a virtual machine. 

1. **Visible to Student:** Designates if the network is visible to users with student access, within the lab environment.

1. **Development Only:** Used to make the network available to lab profile that are currently in development. 

## Virtual Machines

1. **Add Virtual machine:** Click the add a virtual machine to the lab profile. The virtual machine must already be created to add it to the lab profile using this button. 

1. **Create Virtual Machine Profile:** Click to create a virtual machine. This will create a virtual machine, in which the lab author can specify hardware preferences.

1. **Has Virtual machine Pool:** A pool of unique virtual machine profiles can be created, to be issued to individual users. A single pool member will never be used by two different users simultaneously. This is useful for to ensure that a machine or set of machines is unique in the world at any given point in time. **If your virtual machine will be identical for all users, you do not need a pool.** It is important to note that you can only have as many concurrent users as you have pool members. This can greatly reduce the scalability of the lab, so ensure you create a sufficient pool depth to accommodate the peak number of anticipated concurrent users.

1. After a virtual machine profile has been added, the following options are available:

    - **Visible to Student**: Allows the student to view and select the virtual machine from the resources tab.

    - **Default Selection**: Sets the VM to be the default VM selected in the lab. This is the VM that will display when the lab is launched. 

    - **Connect to terminal**: Hides the desktop UI and allows the VM to be connected to via a terminal. For more information, read [Terminal Access](/lod/terminal-access.md).

    - **Start Automatically**: Enables the VM to start automatically when the lab is launched. 

        - **Startup Delay**: Enter that amount of delay for the VM to start, measured in seconds. 

    - **Wait for heartbeat before displaying to user**: When this is enabled, the lab client will not display the lab to the user until the virtual machine reports a heartbeat to the virtualization platform. This is useful if you want to prevent the user from accessing the lab before critical machines are up and running. 
    
        >[!knowledge] this feature requires the VM to have Hyper-V integration services installed on Hyper-V VMs, and VMware Tools installed on an ESX VM. Windows operating systems starting with Windows 10 and Server 2016 have Hyper-V integration services installed by default. Other operating systems require them to be installed. Additionally, on ESX VMs, you must ensure that the user credentials in the virtual machine profile are correct (they are used to initiate the file creation in the VM).
        >
        >- For more information Hyper-V Integration Services, please see the [Hyper-V Integration Services Documentation](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/reference/integration-services).
        >
        >- For more information about VMware Tools, please see the [VMware Tools Documentation](https://docs.vmware.com/en/VMware-Tools/).

    - **Synchronize system time with host**: synchronizes the VM system time with the time on the host that the VM is running on. 

    - **Set initial system time** (available on **ESX only**): Allows you to set the date and time that the VM will launch at. This can be used in conjunction with _Synchronize system time with host_ to freeze the date and time.

    - **Allow user to revert to initial state**: Allows the user to revert to the initial state that the lab was launched at. The user can roll back the VM no matter what has been done in the lab instance. This option is found in the Commands menu (lightning bolt icon) in the lab. 

    - **Make lab instance data available inside virtual machine**: When this option is enabled, lab instance data will be available in the virtual machine. The location varies depending on the platform used (Hyper-v or ESX):

        - Hyper-V: 
        
            On Windows registry: `HKLM\SOFTWARE\Microsoft\Virtual Machine\External`.

        - ESX: 
        
            On Windows-based systems: `C:\Users\Public\Documents\LabInstance.txt`.

            On Unix-based systems: `/tmp/labinstance`.

        All @lab token names and values will be included:

        - Lab Instance ID

        - Lab Profile ID

        - Virtual Machine Profile ID

        - User ID

        - External User ID (if launched via API)

        - Username

        - E-mail

        - First Name

        - Last Name

        - Tag (an optional value that can be passed in via the Launch API)

        >[!knowledge] If the VM is hidden from the student, the lab instance data will have the username and password for the VM removed, when viewing lab instance data from other VMs in the lab. This prevents a hidden VM from being tampered with by the student. 

    - **Resume Order**: Used when resuming from save and launching from a start state.

    - **Resume Delay**: the amount of delay for the VM to start, after resuming a saved lab. 

    - **Floppy Drive**: If removeable media is added to the lab profile, select floppy media in the drop-down to have that media loaded when the VM starts. 

    - **DVD Drive**: If removeable media is added to the lab profile, select DVD media in the drop-down to have that media loaded when the VM starts.

    - **Network Adapter**: If a network has been configured in the Networks tab of the lab profile, select the network that will be available to the VM in the lab. 

        - **Visible to student**: Checking this box allows the network to be visible to the student. If this box is not checked, the network will not be visible to the student in the lab. 

## Removable Media

1. **Add Removable Media:** Click to add removable Media to the lab profile. The removable media must already be created to add it to the lab profile using this button.

1. **Create Removable Media:** Click to create removable media. This will create removable media that can be used in the lab. Removable media types include Floppy and Optical.

    > [!ALERT] When removable media is created, you must choose a platform that the removable media will be used on; Hyper-V or ESX. The removable media is tagged in LOD with the platform. The media can only be used with the chosen platform. 

## Cloud

1. **Cloud Platform:** Select the cloud platform to be used by the lab profile. Selecting a Cloud Platform will allow the lab profile to use the IDLx Cloud Client.
1. **Override Client landing Page:** Enables the portal window to display a specific URL, configured in the Client Landing Page field after enabling this feature by checking the box. 
    1. **Client Landing Page:** Enter the URL that the portal window will display.  This is used in IDLx Cloud Client. Leave this field blank if no Cloud Platform   is selected in the previous step. 
    1. **Append Lab Date:** This option is only available when Override Client Landing Page is enabled. When Append Lab Data is enabled, the following lab data will be    appended to the URL as URL parameters in _name=value_ format. 
       - labProfileId
       - labInstanceId
       - globalLabInstanceId
       - userId
       - userExternalId (if the lab is launched via API)
       - email
       - firstName
       - lastName
       - tag (if included when launched via API)
1. **Enable Automatic Login (AWS Only):** When this option is enabled, users will be directly logged into the cloud portal. No cloud portal users are required. If disabled users will need to manually log into the portal using a required cloud portal user supplied in the user section. 

1. **Subscription Pool:** select the subscription pool that the lab will use. 

1. **Deploy Default VPC (AWS Only)**: When enabled, the lab instances will contain default VPC (Virtual Private Cloud) and resources. Default resources typically contain a VPC, Gateway and other networking resources. Default resources will be deployed prior to template deployment and may add to the instance launch time. 

1. **Deployment Failure:** Select the deployment failure action.

    - **No Action**: no action will be taken if resources fail to deploy.

    - **Terminate Lab:** the lab will be terminated if resources fail to deploy.

    - **Send User Notification:** a notification will be sent to the user in the lab if resources fail to deploy and the lab will still launch. 

1. **Datacenter Availability:** One or more datacenters that resources will be deployed to. If multiple datacenters are selected, the datacenter physically closest to the lab user will be selected. If a region is marked as 'Privileged' then additional clearance from the fabric owner may be needed to successfully launch labs in that region. 

    - **Max Lab Instances**: This must be enabled for each datacenter that is made available. Once this is enabled, you can specify the maximum number of lab instances that can be launched in that datacenter. 

### User Accounts
1. **Add User Account:** Add a portal user account. Enabling this will allow the lab to display credentials to log in to the cloud portal. 

    - **Name Prefix:** prefix that will be used to display the portal username. 

    - **Replacement Token Alias:** alias that will be used in replacement tokens to reference the portal username and password. 

1. **Add Cloud Resource Group (Azure ) - Add Stack Deployment (AWS):** Add a resource group or Stack Deployment that houses resources, access control policies and permissions for the lab. 

    - **Name Prefix:** prefix that will be used to display the name of the resource group. 

    - **Replacement Token Alias:** alias that will be used in replacement tokens to reference the resource group.

    - **Override Region:** Override to the region selected on the Cloud Resource Group or Stack Deployment.  

    - **Region**: Once Override Region has been selected, the region drop-down will be available. This specifies the region that the cloud resources will be deployed to. 

1. **Add Permissions:** select the user from the previous steps to add permissions to. 

    - **Reader**: has read access only to the cloud subscription. 

    - **Contributor** has read access and limited write access to the cloud subscription.

    - **Owner** has read and write access to the cloud subscription. 

1. **Resource Templates**: templates used to deploy resources in a cloud platform. 

    - **Add Resource Template:** add a resource template that is already created in LOD. 

    - **Create Template:** create a new resource template in LOD. 

## Pre-Instancing

**Current Settings**

1. **Enabled Pre-instancing:** Enables the lab profiles to be available for pre-instancing. 

**Schedule** 

1. **Add to Schedule:**

    - **when:** select the date and time when the lab should be pre-instanced. 

    - **Enable:** select to enable the schedule. 

    - **State:** select the state that the lab instances will pre-instanced to. Options include _Saved_ or _Running_.

    - **Batch Size:** enter the amount of labs that should be pre-instanced at a time. 

    - **Stock Level:** enter the minimum amount of labs to be pre-instanced at any given time. 

    - **Follow-Up:** allows subsequent batches to be scheduled, following the completion of the current batch.

## Life Cycle

**Life Cycle Actions:** Actions can be defined to occur at certain points in the lab life cycle. For instance, an external service could be called when the lab builds, or send a notification to the user when the lab is resumed. 

**Inherit Life Cycle Actions**

When a child lab profile is configured to inherit the lab environment from a parent lab profile, LCAs can optionally be set to inherit from the parent lab profile. 

To inherit Life Cycle Actions, click the checkbox on the Life Cycle tab of the child lab profile, to enable inheritance. Once inheritance is enabled, no other LCA configuration will be available on the child lab profile. All LCA changes must be made on the parent lab profile. 

**Life Cycle Actions**:

- **Send a web request:** sends a web request to the URL specified. The URL can optionally contain placeholders that will be replaced by live data, with @lab replacement tokens.
- **Send a notification to the user:**  sends a notification to the user during the specified event.
- **Send an email to the user:** sends an email to the user during the specified event.
- **Execute Script in Virtual Machine:** sends a PowerShell or Shell command to a virtual machine.
- **Execute Script in Container:** sends a Bash command to a container.
- **Execute Script in Cloud Platform:** sends a PowerShell command to the cloud platform.

**Life Cycle Events**:

- **Pre-Build**: the lab components are being deployed, as well as any cloud resources.
- **Post-Build**: the lab environment has been built, but components like virtual machines may still be starting. 
- **First Displayable**: all components of the lab are now running and the user can now interact with the lab.
- **IP Addresses Assigned**: if the lab has public IP addresses, this event will wire when all public IP addresses have been verified to be assigned to the lab's virtual machine(s).
- **Saving**: the lab is in the process of being saved.
- **Saved**: the lab is in a saved state and no longer active. 
- **Resuming**: the lab is resuming from a saved state.
- **Resumed**: the lab has been resumed from a saved state and the user can interact with the lab again. 
- **Tearing Down**: the lab environment is being torn down. 
- **Torn Down**: the lab environment is fully torn down.
- **Building**: the lab environment is being built.

There are additional settings that can **optionally** be configured:

- **Blocking**: this allows you to block further execution of the lab life cycle until the action completes. You can use this to sequence actions that depend on each other. 

- **Delay**: allows you to introduce a delay between the moment the life cycle event occurs and the action is executed. 

- **Error Action**: controls how Lab on Demand will handle errors that occur when executing this action. All errors are logged against the lab instance by default. You can also choose to notify the user about the error or to end the lab. To prevent users from losing their work, only events early in the lifecycle (build, building, running, etc) allow you to end the lab when an error occurs. 


For more information about Action and Event types, please see our [Life Cycle Actions documentation](/lod/life-cycle-actions.md).

## Tags

**Lab Tags**

1. **Add Tag:** Click to add a tag to the lab profile. The Tag must already be created to add it to the lab profile. 

**Lab Host Tags**

1. **Add Lab Host Tag:** Lab host tags are used to specify which Lab Host(s) the lab profile will use when users launch the lab. The Lab Host tag must already be created to add it to the lab profile using this button.

## Advanced

1. **Fabric Build Sequence**: If the lab contains cloud configuration and virtualization components, you can specify which will build first, or set them to build in parallel. 
1. **Theme:** Themes allow you to use custom styles and scripts across multiple lab profiles. Themes are usually set at the series or organization level. Set a theme here only if this lab requires customization that differs from other labs in this series and organization.  

1. **Display Delay:** When set, the lab will not be displayed to the user until the delay time has transpired. You can use this to allow a lab to _cook_ a bit before giving your users access to it. For instance if a critical service with in the lab takes time to spin up and you don't want the user to immediately interact with it. 

1. **Display Delay Message:** A message that will display on the lab loading screen after the lab is running, but the  display delay is in effect. For instance, if you are delaying display in order for critical services to start, you might set this message to _Starting critical services_.

1. **Introduction Content URL:** The content at this URL will be displayed in a dialog when the lab client interfaces first opens. The content can either be an HTML page or an MP4 file. The URL must use HTTPS.

1. **End Redirect URL:** If this value is set, users will be redirected to the specified URL when the lab ends. This feature isn't used often, but can help a lab fit into an external workflow. 

1. **Max Active Instance:** This sets the amount of concurrent labs that can be launched at a time. Setting to _Unlimited_ allows an unlimited amount of launches of this lab profile at a time. Entering a number limits the amount of concurrent labs to the number specified. Any labs that are attempted to be launched after the limit has been met, will be given an error message and will not be able to launch the lab until the number of labs launched is below the maximum amount.

1. **Show Timer:** Checking this box will enable the lab to display a countdown timer, showing the user how much time they have left to complete the lab. 

1. **Enable Navigation Warning:** A warning will be displayed if the user navigates away from the lab client before the lab is complete.

1. **Navigation Bar Width:** This sets the width of the navigation bar in the lab UI. 

1. **Show Instructions Tab:** Show the instructions tab of the lab. If this isn't enabled, the instructions tab will not be displayed. 

1. **Show Resources Tab:** Show the resources tab of the lab. If this isn't enabled, the resources tab will not be displayed. 

1. **Show Help Tab:** Show the help tab of the lab. If this isn't enabled, the help tab will not be displayed. 

1. **Custom Instructions Tab Label:** Specify a custom label to display on the instructions tab.

1. **Custom Resources Tab label:** Specify a custom label to display on the resources tab.

1. **Custom Help Tab Label:** Specify a custom lab to display on the help tab.

1. **Enable Type Text:** Enables the lab to use Type Text. Type Text is used to input information into the lab environment with one click.

1. **Show Virtual machine Power Options:** Checking this box enables virtual machine power options to be available to users.

1. **Require Hyper-V Enhanced Controller:** Checking this box requires the user to use the Hyper-V Enhanced controller to work in the lab. If this box is checked, users will not be able to use any other machine remote controllers. Note that the Hyper-V enhanced controller only allows one user to access the lab at a time. 

1. **Enable Instance Link Sharing:** When enabled, the lab instance URLs can be shared between users. If a user copies the URL from their browser's URL bar, they can send it to another user, or open it in a different browser. Note that most virtual machines only allow one user to access them at a time. This settings does not bypass the connection limitation of virtual machines. 

1. **Allow Lab instance Naming:** allows users to change the name of their lab instances. By default, lab instances have the same name as the lab profile they are based on. 

1. **Allow Multiple Active Instances Per User:** allows a user to have multiple active instances of this lab. This should be left disabled unless all users are willing and able to manage multiple instances. This typically isn't applicable to training scenarios. 

1. **Automatically Disable:** the lab profile will be disabled at the specified time. 

1. **Publish to Organization Template Gallery:** when enabled, this lab profile will be available as a new lab profile template within the organization template gallery. 

1. **Publish to Public Template Gallery:** when enabled, this lab profile will be available as a new lab profile template within the public template gallery. 

    1. **Reuse Template Container and Virtual machine Profiles**: when this option is enabled, new lab profiles created from this template will reuse the container and virtual machine proifles referenced in this template. When this option is disabled, new labs created from this template will have brand new container and virtual machine profiles cloned into them. 

        >[!alert] If virtual machine and container profiles are resued in new labs, changes made to those profiles will impact all labs that use them, including this template.  

1. **Enable virtual machine instance RAM/vCPU editing**: When this feature is enabled, an option will be available to users in the lab client to edit the amount of RAM and number of vCPU for individual virtual machines in the lab instance. Note these VM changes are isolated to the current lab instance and are not committed to the lab profile. Also note the user will have to have the _Edit Virtual Machine Instance RAM/vCPU_ permission with the lab client. 

1. **Record RDP Session**: When this is enabled, RDP sessions for a lab instance will be recorded. Recordings can later be viewed in the lab instance details page. 

### Shared Class Environment

1. **Shared Class Environment:** Shared class environments allow multiple lab instances to be bound together with one or more shared networks and resources. A shared class environment consists of at least two different lab profiles, each serving a particular role. 

    - **Shared Environment:** One lab is configured to serve as the shared environment. Exactly one instance of this lab will run per class. 
    - **Participant:** This is the lab that end-users will launch. There can potentially be more than one lab in this role per class, but they will all connect to the same shared environment instance. 

    Networks within the shared environment lab can be made available to participant labs, making it possible for participants to connect to each other and/or to virtual machines within the shared environment. To enable Shared Class Environment for this lab profile, select one of the options from the drop-down menu; _Shared Environment_ or _Participant_. 

### Save/Cancel Options

- **Allow User to Cancel Labs:** allows the user to cancel the lab at any point
- **Allow user to Save labs:** allows the user to save the lab in it's current state and return at a later time. Users have a specified maximum number of labs that can be saved at a time. Once users reach their maximum number of saved lab instances, they will need to cancel one of the saved labs, to be able to save a new lab instance. The default maximum instances per user is typically 2, but may vary by organization. Note that saved labs are only saved for 48 hours. Users can extend the saved lab expiration by resuming the lab and saving again. Each save sets the timer back to 48 hours. After48 hours has passed, the lab progress and components are discarded and cannot be recovered. 
- **Allow User to Disconnect from Lab Client:** Allows the user to disconnect from the lab client and leave the lab running. 
- **Auto-Save incomplete Labs:** Enables the lab to automatically save in complete labs after a specified amount of time has passed. 
- **Save/Cancel Labs When Last Console Sync Exceeds:** Amount of time given between console syncs, before the lab will automatically cancel or save. 
- **Save/Cancel labs when last Activity Exceeds:** Amount of time given of inactivity before the lab will automatically cancel or save.
- **Activity Required to Enable Auto-Save:** Amount of active time in the lab given before the lab will automatically save.
- **Maximum Allowed Snapshots:** Maximum amount of [snapshots](/snapshots.md) that are allowed

### Instructions Source

Lab on Demand allows you to set Azure DevOps (ADO) or GitHub as an instruction source, using an external ADO or GitHub repository into a lab and use that repository as the source of IDLx content for that lab. For more information, read [External Instruction Source](/lod/instruction-source.md).

- **Instructions Source:** indicates the source of the instructions; GitHub or Azure DevOps. 

- **Repository:** the name of the external repository where the instructions are stored. 

- **Username:** the username of the external repository where the instructions are stored. 

- **Branch:** the branch of the external repository where the instructions are stored.

- **Content File:** the name and file path of the content file. 

- **Last Sync Time:** the last time a sync was attempted or completed between Lab on Demand and the external instruction source. 

- **Last Sync Status:** the status of the last sync attempt.

- **Last Import Size:** the size of the last import of instructions and percentage of maximum allowed size used. 

- **Configuration Complete:** indication if the external instruction source is configured on this lab profile. 

- **Enabled:** enables the external instruction source to supply instructions in the lab.

### LTI (For LTI 1.1 and older only)

1. **Launch URLs**: **LTI** (Learning Tools Interoperability) is a standard defined by the IMS Global Learning Consortium that allows learning systems to consume content provided by external tools or services. This standard enables rich integration between different learning services and platforms, combining their strengths to offer more value to students of those learning systems. For more information on Lab on Demand LTI integration, see our guide here: [LTI Guide](/guides/lti/lod-lti.md).

    - **LTI Launch URL:** the URL to launch the lab via LTI.
    - **Scoring Policy:** Select the type of Scoring Policy. Types of Scoring Policy include: _Time Spent_ and _Tasks Complete_.
    - **Scoring Format:** Select the Scoring Format. Types of Scoring Format include: _% Complete_ and _Pass/Fail_.
    - **Time:** Define the amount of time that the Scoring Policy should use.
 
 ### Authenticated Launch URLs

- **Add Authenticated Launch URL:** Click this to add an Authenticated Launch URL to the lab profile. The URL must already be created to add it to the lab profile. 

### Cloud Credential Pools

1. **Add Cloud Credential Pool:** Click to add a Cloud Credential Pool to the lab profile. The pool must already be created to add it to the lab profile using this button.

### Resources

1. **Add Resource:** Click to add resource. 

1. **Name:** This will be the display name of the resource.

1. **Type:** Select the type of resource to add. Types of resources include:
   - External link
   - PDF document
   - Word document
   - XPS document
   - HTML document
   - Image
   - Video
   - Other

1. **URL:** Enter the URL of the external link or browse to the file that you wish to upload as a resource for use in the lab.

1. **Display:** Select where the resource will be available for users to access.

1. **Description:** Used to provide more detail about the resource.

1. **Lab Manual:** Check this box to include a link to the lab manual on the Lab Profile page. 

[Back to top](#lab-profile-settings)
