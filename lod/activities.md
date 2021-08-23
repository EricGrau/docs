---
title: "IDLx Activities"
description: "Activities fall into two broad categories: Questions and Automated. Questions are simply multiple choice or short answer questions. Automated Activities have a script configured to run against a cloud subscription or Windows-based virtual machines running on Hyper-V in the lab."
isPublished: true
---

# Activities

Activities are configured in the lab instructions, using the lab instruction editor. Activities can be modified at anytime, by anyone that has access to edit the lab instructions. When an Activity is created, it is represented in the lab instructions by a Replacement Token.

Activities fall into two broad categories: Questions and Automated. 
- Questions are simply multiple choice or short answer questions. 
- Automated Activities have a script configured to run against a cloud subscription or virtual machines running on Hyper-V or VMware in the lab.  

> [!KNOWLEDGE] If your lab profile does not use a Cloud Subscription, or if it does not have virtual machines configured, Automated Activities are not available in the Activities menu. 

To get started with Activities:

1. Navigate to your **lab profile**.

1. Click **Edit Instructions**.

1. Click the **Activities icon** to enter the settings Activities menu in your lab instructions. 

![](../lod/images/activity-icon.png)

Next, you should decide what type of Activity you would like to create -- Question, or an Automated Activity that targets a Cloud Subscription or a virtual machines running on Hyper-V or VMware, with a PowerShell or Shell script. 

Click to go to a specific section, or continue reading to learn more about creating Activities in your lab. 

- [Automated Activities](#automated-activities)
    - [Virtual Machine Requirements](#requirements)
    - [Automated Activity Syntax](#automated-activity-syntax)
    - [Automated Activity Creation](#automated-activity-creation)
    - [Automated Activity Output](#automated-activity-output)
    - [Activity Based Assessment Outcomes](#activity-based-assessment-outcomes)
    - [Automated Activity Best Practices and Guidelines](#automated-activity-best-practices-and-guidelines)
    - [Automated Activity Notifications and Variables](#automated-activity-notifications-and-variables)
    - [Example Automated Activities](#example-automated-activities)
- [Questions](#questions)
    - [Multiple Choice Question](#multiple-choice-questions)
    - [Short Answer Question](#short-answer-questions)
- [Scoring](#scoring)
    - [Performance Based Testing](#performance-based-testing)
    - [Scoring Methods](#scoring-methods)
- [Group Management](#group-management)
- [Activity Management](#activity-management)


## Automated Activities 

Automated Activities are PowerShell Windows command Shell Shell scripts that target a Cloud Subscription, or virtual machine running on Hyper-V or VMware in the lab. Cloud Subscriptions are targeted by a PowerShell script, and Windows-based virtual machines can be targeted by both PowerShell and Shell. Automated Activities support using @lab replacement tokens in scripts as well. Automated Activities can be used to help make sure the student has configured their lab environment correctly, help the student understand mistakes that are made in their lab, as well as give the student confirmation that they are completing the lab instructions correctly. Automated Activities can also be used to automate any configuration or lab steps that you wish to automate. 

### Virtual Machine Requirements {requirements}

**Hyper-V**:

- LOD Integration services are not required to be installed but it is recommended, to enable features such as screen resizing. 

- Supported Windows Operating Systems:
    - Windows 10
    - Windows Server 2016
    - Windows Server 2019  

- The VM must support Hyper-V PowerShell Direct. There are no additional steps to install or configure PowerShell Direct, but the VM must support it. 

    >[!knowledge] PowerShell Direct can be used to remotely manage a Windows 10, Windows Server 2016, or Windows Server 2019 virtual machine from a Windows 10, Windows Server 2016, or Windows Server 2019 Hyper-V host. 
    >
    >PowerShell Direct allows Windows PowerShell management inside a virtual machine regardless of the network configuration or remote management settings on either the Hyper-V host or the virtual machine. This makes it easier for Hyper-V Administrators to automate and script virtual machine management and configuration. For more information about PowerShell Direct, read [Manage Windows virtual machines with PowerShell Direct](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/manage/manage-windows-virtual-machines-with-powershell-direct).

- Linux:

    - Requires Hyper-V Integration Services to be installed.

    - Requires a running SSH server. For more information about configuring SSH, see [Terminal Access to Virtual Machines](terminal-access.md)

    - Refer to the [Microsoft Linux support information](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/supported-linux-and-freebsd-virtual-machines-for-hyper-v-on-windows) to see if a distribution is supported on Hyper-V and instructions on installing any additional integration components
        - Network information needs to be communicated over the VMBus via Hyper-V integration services, currently RedHat, CentOS, FreeBSD, and most Debian distributions support this
        
    - Confirmed supported Linux distros:
     
        - Ubuntu 18.04 
        - CentOS-7-x86_64-1804 
        - Kali Linux 2019.2
        - Debian-10.0.0.0
        - FreeBSD-11.2
        - openSUSE-Leap-15.1
        - Oracle R6U10
        - Oracle R7U7
        - Security-Onion-16.04.6.1
     


**VMware**: 

- VMware Tools must be installed.

- PowerShell must be installed on the VM.

- Supported  Windows Operating Systems:
    - Windows 7
    - Windows 7 
    - Windows 8 
    - Windows 10
    - Windows Server 2008
    - Windows Server 2012
    - Windows Server 2016
    - Windows Server 2019

- Linux 

    - Requires VMware Tools to be installed

    - Requires a running SSH server. For more information about configuring SSH, see [Terminal Access to Virtual Machines](terminal-access.md)

    - Linux VMs must support the open-vm-tools package. On most builds, this is installed by default. It is recommended to verify this is installed using the following commands: 
        - On **Debian/Ubuntu** builds this can be installed with ```sudo apt-get install open-vm-tools```.
        - On **RHEL or CENTOS** ```sudo yum install open-vm-tools -y```.

### Automated Activity Syntax

Along with traditional syntax, there is additional syntax that can be used to interact with Lab on Demand.

- Setting Lab Variables: sets a variable that can be recalled in subsequent lab instructions using @lab replacement tokens, as many times as necessary. 

- Sending Lab Notifications: Sends a a popup notification to the lab, using the text specified in the syntax.

- Scoring: used to determine how much of the score value the lab user will receive for the activity by setting the Activity result. This can be used to award partial score values for the automated activity. The partial score is dictated by a numerical value in the syntax, that represents the percentage of the score value that will be awarded. For Windows Command Shell and Bash, you can also display a message in the lab instructions with text specified scoring syntax.

    - [PowerShell Syntax](#powershell)
    - [Python Syntax](#python)
    - [JavaScript Syntax](#JavaScript)
    - [C# Syntax](#C#)

For more information about the available languages and which versions are supported, see our [Lab on Demand Scripting documentation](scripting-home.md).

#### **PowerShell** 

- **Return a Boolean value**

    ```PowerShell
    //do stuff... all good
    return true
    ```

    ```PowerShell
    //do stuff... uh oh
    return false
    ```

- **Use setActivityResult**

    ```PowerShell
    //do stuff... all good
    Set-ActivityResult -Correct
    ```

    ```
    //do stuff... uh oh
    Set-ActivityResult -Incorrect
    ```

    You can also report the result as a score percentage:

    ```PowerShell
    //do stuff... we want to report success and set the score value as 50%
    Set-ActivityResult -Score .5
    ```

- **Send a Notification to the User**

    Notifications appear as real-time toast notification in the lab client.

    ```PowerShell
    Send-LabNotification -Message "Hello from a script"
    ```

- **Lab Variables**

    Lab variables are always string name/value pairs. Variable values are scoped    to the lab instances and become avaialble within the lab instructions as   well as subsequent script executions. 

    ```PowerShell
    Set-LabVariable -Name firstName -Value John
    ```

    You can "receive" a variable in your script: 

    ```PowerShell
    #a variable set elsewhere in the lab, but we can use it in our script
    $myVariable1 = "@lab.Variable(myVariable1)"
    ```

#### **Python**

- **Return a Boolean value**

    ```Python
    //do stuff... all good
    return true;
    ```

    ```Python
    //do stuff... uh oh
    return false;
    ```
- **Use setActivityResult**

    ```Python
    //do stuff... all good
    setActivityResult(true);
    ```

    ```Python
    //do stuff... uh oh
    setActivityResult(false);
    ```

    You can also report the result as a score %...

    ```Python
    //do stuff... we want to report success and set the score value as 50%
    setActivityResult(0.5);
    ```

- **Send a Notification to the User**

    Notifications appear as real-time toast notification in the lab client.

    ```Python
    sendLabNotification("A notification from Python!");
    ```

- **Lab Variables**

    Lab variables are always string name/value pairs. Variable values are scoped to the lab instances and become avaialble within the lab instructions as well as subsequent script executions. 

    ```Python
    setLabVariable("myVariable1", "This was set by Python in the cloud!");
    ```

    You can "receive" a variable in your script...

    ```Python
    #a variable set elsewhere in the lab, but we can use it in our script
    const myVariable1 = "@lab.Variable(myVariable1)";
    ```

<!--
- **Setting Variables**

    Prepend your command with the parameter defined in your function. In the example below the parameter is `param1`.

    ```Python
    def run(param1):
        param1.setLabVariable('Name','John')
        return True,'output shown to the user in lab instructions'
    ```

- **Sending Lab Notifications**

    ```Python
    def run(param1):
        param1.sendLabNotification('message shown in the notification popup')
        return True,'output shown to the user under the activity'
    ```

- **Custom Python Script**

    Define your script inside of a Python function using the template below.

    - **Template**

    ```
    def run(param1):
        your command here
        return Boolean,"output shown to the user in lab instruction"
    ```

    - **Example**
    ```
    def run(param1):
        if 1 == 1:
            outcome = True
            outcomeText = '1 equals 1'
        else:
            outcome = False
            outcomeText = 'Please check statement'
        return outcome,outcomeText
    ```
-->

#### JavaScript

- **Return a Boolean value**

    ```JavaScript
    //do stuff... all good
    return true;
    ```

    ```JavaScript
    //do stuff... uh oh
    return false;
    ```

- **Use setActivityResult**

    ```JavaScript
    //do stuff... all good
    setActivityResult(true);
    ```

    ```
    //do stuff... uh oh
    setActivityResult(false);
    ```

    You can also report the result as a score percentage:

    ```JavaScript
    //do stuff... we want to report success and set the score value as 50%
    setActivityResult(0.5);
    ```

- **Send a Notification to the User**

    Notifications appear as real-time toast notification in the lab client.

    ```JavaScript
    sendLabNotification("A notification from Node.js!");
    ```

- **Lab Variables**

    Lab variables are always string name/value pairs. Variable values are scoped    to the lab instances and become avaialble within the lab instructions as well  as subsequent script executions. 

    ```JavaScript
    setLabVariable("myVariable1", "This was set by Node.js in the cloud!");
    ```

    You can "receive" a variable in your script:

    ```JavaScript
    #a variable set elsewhere in the lab, but we can use it in our script
    const myVariable1 = "@lab.Variable(myVariable1)";
    ```

#### C#

- **Return a Boolean value**

    ```C#
    //do stuff... all good
    return true;
    ```

    ```C#
    //do stuff... uh oh
    return false;
    ```

- **Use setActivityResult**

    ```C#
    //do stuff... all good
    #Set-ActivityResult -Correct -Message 'Nice job'
    ```

    ```C#
    //do stuff... uh oh
    #Set-ActivityResult -Correct -Message 'Please try again'
    ```

    You can also report the result as a score percentage.

    ```C#
    //do stuff... we want to report success and set the score value as 50%
    Set-ActivityResult -Percentage .5 -Message "You received half credit"
    ```

- **Send a Notification to the User**

    Notifications appear as real-time toast notification in the lab client.

    ```C#
    Send-LabNotification 'Hello from Azure CLI'
    ```

- **Lab Variables**

    Lab variables are always string name/value pairs. Variable values are scoped    to the lab instances and become avaialble within the lab instructions as   well as subsequent script executions. 

    ```C#
    Set-LabVariable -Name 'firstName' -Value 'John'
    ```

    You can "receive" a variable in your script...

    ```C#
    #a variable set elsewhere in the lab, but we can use it in our script
    var myVariable1 = "@lab.Variable(myVariable1)";
    ```

### Automated Activity Creation

1. If you would like the lab to be scored, Click the **switch** next to _Enable Scoring_. If you would not like the lab to be scored, simply leave the **Switch** turned off. 

1. Click **New Automated Activity**.

![](../lod/images/new-automated-activity.png)

- **Name**: this will be the title of the automated Activity, and will be displayed in the lab instruction editor, in the activities menu.

- **Replacement Token Alias**: this allows you to change the token to something more identifiable when reviewing the IDLx of the lab.

- **Instructions**: this is where instructions for the Activity are entered, and will be displayed to students, in the lab instructions. 

- **Group**: You can choose to add this to a Activity Group by selecting from the dropdown. This option is only displayed if a group is active.

- **Scored**: enables the question to be scored. Scoring must be enabled in your lab. [Scoring is covered below in this document](#scoring).

- **Display Scripts as Task List**: enables the script to be displayed as a Task List. This is useful when there is more than one script configured on an Activity. *Display Scripts as Task List* will take the **Text** field from each *Script* created within the activity and insert it in to the Instructions page with a box next to it that has a question mark. This is where users are able to manually run a check against those scripts to see if they are correct or not.  The boxes will then change to Green with a check for correct or Red with an X for incorrect and report any script output associated with them.

    > [!KNOWLEDGE] If **Display Scripts as Task List** is checked, On-Demand Evaluation will no longer be available for this Activity. 

- **On-Demand Evaluation**: enables a button that the user can click to check their answer to a question, or to score their answer if Activities are set to be scored.
 
- **Allow retries**: allows the user to retry a question if they enter or select an incorrect answer. This option is not available when On-Demand Evaluation is disabled. 

- **Required for submission**: requires the student to perform the Activity, to submit their lab for grading.

- **Blocks page navigation until evaluated**: checking this box prevents the student from navigating to the next page in the lab instructions unless they have entered or selected an answer to this question. 

- **Blocks page navigation until passed**: checking this box prevents the student from navigating to the next page in the lab instructions until the objective in the automated activity is completed.

- **Show Results in Reports**: check this box to show the results of the script on the lab instance. If this is unchecked, the result of the script will not be displayed on the lab instance. Leaving this unchecked is useful for scripts that are automating a task that doesn't require reporting or feedback. 

- **Correct answer feedback**: this will be displayed to the user upon entering or selecting a correct answer to a question. 

- **Incorrect answer feedback**: this will be displayed to the user upon entering or selecting a incorrect answer to a question. 

- **Script 1**:
    - **Target**: The virtual machine, cloud subscription, or custom target that the script will target. 
        - Cloud subscriptions can be targeted by PowerShell, Python, C# or JavaScript.
        - virtual machines running on Hyper-V or VMware can be targeted by PowerShell or Windows Command Shell. 
        - Linux-based VMs running Hyper-V or VMware can be targeted by Bash. 
        - **Custom Target**: Scripts can be executed against a custom target, using specific package for the selected language. Scripts can use packages that are hosted by supported package providers. 

            - PowerShell: [PowerShell Gallery](https://www.powershellgallery.com/)
            - Python: [PyPi](https://pypi.org/)
            - JavaScript: [NPM](https://www.npmjs.com/)
            - C#: [Nuget](https://www.nuget.org/)
    
            In the lab instructions, you can configure a custom target by doing the following: 

            1. From the Activities menu, click **New Automated Activity**.
            1. Complete the fields at the top of the dialog, and then **Scroll to the Script 1 section**. 
            1. Select the **Target drop-down menu** and change it to **Custom**.
            1. Select the **Language drop-down menu** and select the    **Language** that the script will use. 
            1. On the next line, a button will appear to add a custom module    or package. The text on the button will reflect the language   selected and display the name of the supported package provider. Select **Click to add a module or package**.
            1. **Enter the name of the package** exactly as it appears in the   package provider repository. 
            1. **Enter the version** of the package you wish to use.
            1. Next, **Enter the script** in the script field. 

    - **Language**: the scripting language that will be used.Enabling Bash scripting or terminal connections will not take effect on running lab instances, users will have to relaunch their lab. Supported languages include: 
        - Windows Command Shell (VM based labs)
        - Bash (VM based labs)
        - PowerShell (Azure, AWS and VM based labs)
        - Python (Azure and AWS labs)
        - C# (Azure only)
        - JavaScript (AWS only) 

        For more information about the available languages, see our [Lab on Demand Scripting documentation](scripting-home.md).
    
    - **Version**: **(Cloud subscription execution only)** select the scripting language version that the script will use. 

        - **Legacy PowerShell**: uses PowerShell version 5.1. 
            - **Azure**: Azure RM 6.8.1.
            - **AWS**: AWSPowerShell.netcore 4.1.3.0.            
        - **PowerShell**: uses PowerShell version 7.1.3.  
            - **Azure**: 
                - Azure AZ 5.7.0.
                - Azure-CLI 2.22.1.
            - **AWS**: 
                - AWS CLI 2.1.39.
                - AWS.Tools 4.1.10.0.
        - **Python**: uses Python version 3.9.4.
            - **Azure**: AZ SKY 1.13.0.
            - **AWS**: AWS Boto3 1.17.50.
        - **C#: (Azure Only**) uses C# .NET 5.
            - **Azure**: Azure.Core 1.13.0.
        - **JavaScript (AWS Only)**: uses node.js 14
            - **AWS**: AWS SDK for JS 3

    - **Score Value**: the score value the student will receive for completing the Activity correctly. This score contributes to their overall score in the lab.
    - **Show Output To User**: this will show the output of the script to the user when enabled. If this is not enabled, the user will be shown the Correct Answer Feedback or the Incorrect Answer Feedback. 
    - **Enable**: check the box to enable the script. If the script is not enabled, it will not be executed in a Task list or during on-demand evaluation.
    - **Script**: enter the script that will be executed. @lab replacement tokens that are used in scripts will be replaced in the lab instructions when the lab is launched.

    - **New Script**: click to add an additional script to this Activity. The new script will be represented by a button, in a Task List. 

    >[!knowledge] @lab Replacement Tokens can be used in Activity scripts, to replace data in the lab instructions that is not known at the time of authoring the lab instructions, by inserting a Replacement Token in the lab instructions where you want data to be replaced in the lab.

    The following two options are **only available if Display Scripts as Task list is checked**, and are located in the section for the script they belong to. This allows you to provide custom feedback on each Automated Activity. 

    - **Correct answer feedback**: you can enter text here, or you can use scripts to generate a response to the student.  

    - **Incorrect answer feedback**: you can enter text here, or you can use scripts to generate a response to the student.  

### Automated Activity Output

You can optionally store automated activity output separately from a script message that the student receives in the lab when they complete the automated activity. This allows you to display a message to the student in the lab, but leave more detailed evidence for reporting or remediation. 

An example, if you wanted to capture a list of all running services in a virtual machine, at a specific point in the lab. You could create an automated that uses PowerShell to target a Windows virtual machine with the following script:

```linenums
Get-Service | Format-List *
Set-ActivityResult -Correct -Message 'You got it!'
```

When the student clicks the button in the lab to trigger the automated activity, the script will capture a list of running services and store them on the lab instance details page, and will display "You got it!" to the student in the lab. 

### Activity Based Assessment Outcomes 

Activity Based Assessments (ABA) Outcomes offer adaptive learning experienced based on the result of an automated activity or a question activity. This allows lab authors to provide additional guidance based on how a student interacts with an activity in the lab instructions.  For example, an ABA could be configured to direct the lab user to more learning resources if they do not answer an ABA correctly, or they could be directed to a page further in the lab instructions if they do not need the additional learning material. 

An ABA Outcome consists of an event, condition, action, and target. 

- **Event**: When a question is Answered or Evaluated, or when a script is Evaluated.
- **Conditions**: 
	- Correct
	- Incorrect
	- Correct or Incorrect
	- Answer = (Question only)
	- Score Value =
	- Score Value >
	- Score Value >= 
	- Score Value <
	- Score Value <=
- **Actions**: Can set either a variable or progress the student to a different page within the lab.
- **Target**: The variable to set or page number the student will be directed to.

## Configuring Outcomes 

To configure ABA Outcomes in a lab profile, your lab instructions must have a Question activity or an Automated activity with On-demand Evaluation enabled.

- [Question Activities](#question-activities)
- [Automated Activities](#automated-activities)

### Question Activities

1. Navigate to the lab profile. 

1. Edit the lab instructions. 

1. Open the Activity Editor at the top of the Instructions Editor. 

    ![Activities Menu](images/activities.menu.png)

1. Edit the activity you wish to add Outcomes to, or add a new activity. 

1. Scroll to the bottom of the Activity dialog to the Outcomes section. 

1. Click **Add Outcome**. 

1. There are multiple options to configure, to determine what will happen when a lab user interacts with an activity and when that action will executed. 

    ![Add Outcomes](images/add-outcomes.png)

1. The first option to configure is the Event, **When**. The options available are **Answered** and **Evaluated**. 

    - **Answered**: this means the lab user selected or typed an answer in the activity. 
    - **Evaluated**: this means the lab user clicked the on-demand evaluation button on the activity. 
    
1. The next option to configure is the Condition, **And**. Some options available may be grayed out, based on if scoring is enabled in the lab activity. 

    When scoring is **not enabled**, the options available are Correct, Incorrect, Correct or Incorrect, and Answer =. 

    - **Correct**: correct answer.

    - **Incorrect**: incorrect answer.

    - **Correct or Incorrect**: correct or incorrect answer.

    - **Answer =**: answer is equal to a specified value. When this option is selected, a field will be available to specify a value that the answer has to be equal to. 

    When scoring **is enabled**, the options available are the same as when scoring is not enabled, but there are more to choose from. When any of these options are selected, a field will be available to specify a value that the answer has to be equal to. 

    - **Score =**: score value equals a specified value. 

    - **Score >**: score value is greater than a specified value. 

    - **Score > =**: score value is greater or equal to a specified value. 

    - **Score <**: score value is less than the specified value. 

    - **Score <=**: score value is less than or equal to the specified value. 

1. Next, you must set the action that will occur when the lab user answers or evaluates a question, and is correct or incorrect. The options available are **Set Variable** and **Go to Page**. 

    - **Set Variable**: sets a variable that can be used anywhere in the lab instructions.

    - **Go to Page**: directs the user to a specific page in the lab instructions.

1. After selecting Set Variable, select a variable that is already set in the lab instructions or select _New Variable_. 

1. Set the value of the variable in the _To_ field. If you are using an existing variable and enter a value that is different than the value that is set on the existing variable, the value will be replaced with the value entered in the _To_ field.

### Automated Activities

ABA Outcomes are only available on Automated Activities that have On-Demand Evaluation enabled. Once On-Demand Evaluation is enabled on the Activity, the Add Outcomes button will be displayed below each script in the activity. 

1. Navigate to the lab profile. 

1. Edit the lab instructions. 

1. Open the Activity Editor at the top of the Instructions Editor. 

    ![Activities Menu](images/activities.menu.png)

1. Edit the activity you wish to add Outcomes to, or add a new activity. 

1. Enable On-Demand Evaluation if it is not enabled already. 

1. Scroll to the bottom of the activity below the Script, to the Outcomes section. If the activity has multiple scripts, there will be an Add Outcomes button under each script. 

1. Click **Add Outcome**. 

1. There are multiple options to configure, to determine what will happen when a lab user interacts with an activity and when that action will execute. 

    ![Add Outcome](images/aba-outcomes-automated.png)

1. The first option to configure is the Condition, **When**. Some options available may be grayed out, based on if scoring is enabled in the lab instructions or not. 

    When scoring is **not enabled**, the options available are Correct, Incorrect, Correct or Incorrect, and Answer =. 

    - **Correct**: correct answer.

    - **Incorrect**: incorrect answer.

    - **Correct or Incorrect**: correct or incorrect answer.

    - **Answer =**: answer is equal to a specified value. When this option is selected, a field will be available to specify a value that the answer has to be equal to. 

    When scoring **is enabled**, the options available are the same as when scoring is not enabled, but there are more to choose from. When any of these options are selected, a field will be available to specify a value that the answer has to be equal to. 

    - **Score =**: score value equals a specified value. 

    - **Score >**: score value is greater than a specified value. 

    - **Score > =**: score value is greater or equal to a specified value. 

    - **Score <**: score value is less than the specified value. 

    - **Score <=**: score value is less than or equal to the specified value. 

1. Next, you must set the action that will occur when the lab user answers or evaluates a question, and is correct or incorrect. The options available are **Set Variable** and **Go to Page**. 

    - **Set Variable**: sets a variable that can be used anywhere in the lab instructions.

    - **Go to Page**: directs the user to a specific page in the lab instructions.

1. After selecting Set Variable, select a variable that is already set in the lab instructions or select _New Variable_. 

1. Set the value of the variable in the _To_ field. If you are using an existing variable and enter a value that is different than the value that is set on the existing variable, the value will be replaced with the value entered in the _To_ field.

### Automated Activity Best Practices and Guidelines

- Use Automated Activities in areas of your lab when students are prone to making mistakes. A PowerShell script, such as the example shown below, helps students to make sure their lab is configured appropriately so that they do not get an error when trying to complete steps later in the lab.  

- Provide the student feedback with your scripts where possible, to help them complete the lab instructions correctly. An if/else statement in your script works very well in this situation, to provide unique feedback depending on if the student gave the correct answer or not. 

- If more than one script is configured on an Activity, the scripts will execute in sequential order. If one of your scripts is relying on another script to be completed, make sure you order the scripts appropriately to prevent your Automated Activity from not working correctly. 

- Automated Activities support PowerShell Windows Command Shell, and Bash. Cloud Subscriptions must be targeted by a PowerShell script, and virtual machines running on Hyper-V or VMware can be targeted by PowerShell or Windows Command  Shell. Linux-based VMs running Hyper-V or VMware can be targeted by Bash.

### Automated Activity Notifications and Variables

Automated activity scripts can set a variable and send notifications to the student, to draw attention to some information or to notify the student of the outcome of the script once it is completed. This allows the student to progress through the lab instructions, without waiting for the result from the script. 

You can also use @lab replacement tokens, to replace information in the notification. This allows the lab author to provide more specific information to the student.  

You can set a variable and send a notification using the the variable in the following example. This example uses 2 PowerShell scripts. 

**Script 1**

```linenums
Set-LabVariable -Name Directory -Value C:/users/student/documents
Set-ActivityResult -Correct
```

**Script 2**

```linenums
Send-LabNotification -Message "Use this directory: @lab.Variable(Directory)!"
Set-ActivityResult -Correct
```

_Student view in the lab of automated activity_

![](images/automated-activity-student-view.png)

_Student view of the notification in the lab_

![](images/automated-activity-student-view-notification.png)

### Example Automated Activities

^[PowerShell Samples][powershell-samples]

> [powershell-samples]:
>
> !INSTRUCTIONS[][ps-simple-explanation]
>
> !INSTRUCTIONS[][ps-simple-code]
>
> !INSTRUCTIONS[][ps-complex-explanation]
>
> !INSTRUCTIONS[][ps-complex-code]


^[Bash Samples][bash-samples]

> [bash-samples]:
>
> !INSTRUCTIONS[][bash-simple-explanation]
>
> !INSTRUCTIONS[][bash-simple-code]
>
> !INSTRUCTIONS[][bash-complex-explanation]
>
> !INSTRUCTIONS[][bash-complex-code]

## Questions

Activities in your lab can be configured to use the following types of questions:
- Multiple choice
    - Single answer
    - Multiple answers
- Short answer
    - Exact match
    - Regex match

Optionally, you can enable scoring for Questions in your lab. Once scoring is enabled:

- You will be presented with a text field where you can enter the passing score the student will need to achieve in the lab. 
- You can enable scoring only on the questions you wish to be scored. Questions that are not scored, are considered practice or review and do not contribute to the student's overall score in the lab. 
- Each question that is scored is given a score value, and that value is awarded to the student by selecting the correct answer to the question.   
- If Scoring is not enabled, you do not need to decide which questions will be scored and which will not be scored.

### Multiple Choice Questions 

1. If you would like the lab to be scored, Click the switch next to _Enable Scoring_. 

1. Click **New Question**.

![](../lod/images/activities-menu.png)

![](../lod/images/multiple-choice-question.png)

- **Text**: This is where the multiple choice question is entered. This will also be the text that is displayed in the Activities editing menu.

- **Format**: the format can be changed by clicking the drop-down menu. Format options for multiple choice include:
    - Multiple choice, single answer:
    - Multiple choice, multiple answer

- **Add Answer**: click to add an answer to the multiple choice question. 

- **Group**: You can choose to add this to a Activity Group by selecting from the dropdown. This option is only displayed if a group is active.

- **Randomize Answer Sequence**: When selected, the answers provided will be displayed to the student in random order.

- **Scored**: enables the question to be scored. Scoring must be enabled in your lab. [Scoring is covered below in this document](#scoring).

- **Score Value**: the value the student will receive upon selecting a correct answer.

- **On-Demand Evaluation**: enables a button that the user can click to check their answer to a multiple choice question in the lab, or to score their answer if Activities are set to be scored.

- **Custom Evaluation Button Text**: allows you to customized the text displayed on the evaluation button. 

- **Allow retries**: allows the user to retry a question if they select an incorrect answer. This option is not available when On-Demand Evaluation is disabled. 

- **Blocks page navigation until answered**: checking this box prevents the student from navigating to the next page in the lab instructions, unless they have selected an answer to this question. 

- **Blocks page navigation until passed**: checking this box prevents the student from navigating to the next page in the lab instructions until the question is answered correctly.

- **Required for submission**: click to make this multiple choice question required, for the student to submit their lab. 

- **Correct answer feedback**: this will be displayed to the user upon selecting a correct answer to a multiple choice question. 

- **Incorrect answer feedback**: this will be displayed to the user upon selecting a incorrect answer to a multiple choice question. 

### Short Answer Questions

1. If you would like the lab to be scored, Click the switch next to _Enable Scoring_. 

1. Click **New Question**.

![](../lod/images/activities-menu.png)

![](../lod/images/new-question-scoring-enabled-window.png)

- **Text**: This is where the short answer question is entered. This will also be the text that is displayed in the Activities editing menu.

- **Group**: You can choose to add this to a Activity Group by selecting from the dropdown. This option is only displayed if a group is active.

- **Format**: the format can be changed by clicking the drop-down menu. Format options include:
    - Short answer, exact match
    - Short answer, regex match

- **Answer**: the answer to a short answer question.

- **Case-sensitive**: enables case-sensitivity on the students answer to short answer questions. 

- **Scored**: enables the question to be scored. Scoring must be enabled in your lab. [Scoring is covered below in this document](#scoring).

- **Score Value**: the value the student will receive upon entering a correct answer.

- **On-Demand Evaluation**: enables a button that the user can click to check their answer to a short answer question in the lab, or to score their answer if Activities are set to be scored.

- **Custom Evaluation Button Text**: allows you to customized the text displayed on the evaluation button. 
 
- **Allow retries**: allows the user to retry a question if they enter an incorrect answer. This option is not available when On-Demand Evaluation is disabled. 

- **Blocks page navigation**: checking this box prevents the student from navigating to the next page in the lab instructions, unless they have entered an answer to this question. 

- **Required for submission**: click to make this short answer question required, for the student to submit their lab. 

- **Correct answer feedback**: this will be displayed to the user upon entering a correct answer to a short answer question. 

- **Incorrect answer feedback**: this will be displayed to the user upon entering a incorrect answer to a short answer question. 

## Scoring

Scoring allows the student to be given a score for each Activity they complete correctly, and those scores contribute to the student's overall score in the lab. As the lab author, you set the passing score for the lab after you enable scoring in the lab. 

> [!KNOWLEDGE] When Scoring is enabled, it is not required to make each question scored. As a lab author, you are free to decide which Activities have a score value associated, and only score the questions that you wish to.

To enable Scoring in your lab:

1. Click the **Activities icon** to enter the settings menu for Activities.

1. Click the **switch** to enable Scoring. 

1. Enter a **passing score** for the lab. You may change this at anytime, as often as you would like. 

    ![](../lod/images/activities-menu-scoring-enabled.png)

1. After Scoring is enabled, you will see the Score checkbox available to select on all Activities you have created, while editing that Activity.

1. Click the checkbox to enable scoring, and enter a score for that Activity. 

    ![](../lod/images/score-scored-checkboxes.png)

1. The student will be given the score value upon completing the Activity correctly. 

### Scoring Methods

There are two methods to return a scoring result from an automated activity.

- **A binary value**: a value indicating pass or fail. A binary result allows for very simple script authoring. A binary result from a script means that the score value defined in the activity will be used. If the activity is completed correctly, the student will receive the score value defined in the LOD instructions editor for the activity. 
    - If the last value encountered in the script output is a **true** value, then the script will be considered to have **passed** and the student will receive the score value of the activity. 
    - If the last value encountered in the script output is a **false** value, then the script will be considered to have **failed** and the student will not receive the score value of the activity.

- **Explicit Score Value** Set score in the script for more complex scenarios. This method requires knowledge about scripting languages, such as PowerShell or Bash. An explicit value in a script means that the score value for each script is defined in the script itself, or multiple scores can be configured for each part of the script that is completed correctly. The score value is set in the script using [Automated Activity Syntax](#automated-activity-syntax). An explicit score value can be given after each section of the script that should be scored or at the end of a script. 

Additionally, text output (logging) can be configured on a script. Any text output from the script is captured along with the script result. This allows for capture of meaningful information along with the pass/fail result. The captured data will be sent in the `ScriptResponse` line of the API response. 

#### Example Scoring Methods

**Binary example**

When the script returns `$true` in a PowerShell script or `True` in a Bash script, the student will receive the score value configured in the activity in the lab editor. When the script returns a false binary result, the student will receive a score value of 0 for the activity. 

This sample is gauging a file's size on the Windows file system. If the file is less than 1000 bytes the user is successful, otherwise they are unsuccessful.

- PowerShell

    ```PowerShell-linenums
    $result = $false
    $file = (Get-Item C:\Users\LabUser\file.txt).length
    if($file -lt 1000){
        echo "Success, filesize is $file"
        $result = $true
    }
    $result
    ```

- Bash

    ```Bash-linenums
    RESULT=False
    file=$(stat --format=%s /etc/passwd)
    if [ $(echo $file) -lt 1000 ]
    then 
     echo "success, filesize is $file"
     RESULT=True
    fi
    echo $RESULT
    ```

**Explicit score value Example**

When a section of a script is completed correctly, the student is given the score value declared in PowerShell as `Set-ActivityResult` and `set_activity_result` in Bash. In the examples below, the student will receive 5 points for the first part, 2.5 points for the second part or 0 points if they do not complete the first or second part of the script. 

- PowerShell

    ```PowerShell-linenums
    $result = $False
    $hostname = [System.Net.DNS]::GetHostEntry('')
    if ($hostname.HostName -eq "LabVM" -and $hostname.AddressList.IPAddressToString     contains "192.168.1.4"){
         Set-Activity-Result 1 "Success"
         $result = $True
     }elseif($hostname.AddressList.IPAddressToString -contains "192.168.1.4"){
         Set-Activity-Result .5 -Correct  
     }else{
         "Value not found"    
     } 
     $result
    ```

- Bash

    ```Bash-linenums
    RESULT=False
    host=$(cat /etc/hosts | grep 192.168.1.2)
    if [[ $(echo $host) == "192.168.1.2 linuxvm"* ]]
    then
     set_activity_result 1 "Success"
     RESULT=True
    elif [[ $(echo $host) == "192.168.1.2"* ]]
    then 
     set_activity_result .5 "Partially correct"
    else 
     echo "value not found"
    fi
    echo $RESULT
    ```

### Partial Scoring

Partial scoring allows a student to receive partial credit for a task in the lab, instead of the score for the question being all or nothing. 

For example, if the lab instructions had a task to create a directory and name it "MyDirectory", and the student created the directory but didn't name it properly -- they could receive partial credit for creating the directory, even though they didn't name it properly. 

Partial scoring is achieved with automated Activities in IDLx. To configure partial scoring for the example above:

1. Edit the **lab instructions**.
1. **Enable scoring** from the Activities menu.
1. **Add** an automated Activity.
1. In the **Script 1** field, enter a PowerShell script to check for the directory the student created.
1. Assign a score value for script 1. This will be the partial score the student will receive if the directory is created. 
1.  Click _New Script_.
1. In the **Script 2** field, enter a PowerShell script to verify the directory is named properly. 
1. Assign a score value for script 2. This will be the partial score the student will receive if the directory is name properly.
1. Alternatively, the score value can be set for the activity using the `Set-ActivityResult` syntax discussed in the previous section. 

### Performance Based Testing 

Labs can be scored with a performance based testing scenario by leaving the _On-demand_ checkbox unchecked, when creating automated activities. When activities are configured this way, they are scored when the lab is completed by the student. The score can be obtained by viewing the lab instance details. 

![](images/display-as-task-list.png)

## Group Management

Activities can be sorted into groups so that they are easier to manage. Multiple groups can be specified. By default, the activities will be displayed in the order they are added to the group, but may be rearranged using the caret on the far right of the activity row.  

![](../lod/images/activities-edit-menu.png)

**The following options apply to activity groups:**

![](../lod/images/group-management.png)

- **Name**: Human readable, this makes it easier to distinguish activities.

- **Replacement Token Alias**: this allows you to change the token to something more identifiable when reviewing the IDLx of the lab.

- **Randomize**: When selected, the activities within the group will be displayed to the student in random order.

- **# Activities to Display**: All activities within the group will be displayed by default, but you can set the lab to randomly display a subset of activities by specifying an integer here.

- **Scored**: this controls whether the activities in the group will be scored. If all activities are shown, scoring will default to what is specified in the individual activity rather than what is specified at the group level.

- **Activity Score Value**: when displaying only a subset of activities from the group and scoring enabled, a score must be specified for all activities within the group. Due to the randomization, all activities within the group will have the same score to normalize the outcome across all deliveries of the exam.

- **On-Demand evaluation**: when any activities within the group are configured for On-demand evaluation, selecting this option will allow the student to select just one button to evaluate all applicable activities. Activities belonging to the group but configured without On-Demand evaluation set on the activity level will be evaluated only when the exam is submitted. 

- **Custom Evaluation Button Text**: allows you to customized the text displayed on the evaluation button. 

## Activity Management

After Activities are created, they can be modified at any time, using the Activity editing menu. 

To access this menu, simply click the **Activities Icon**

![](../lod/images/activity-icon.png)

![](../lod/images/activities-edit-menu.png)

- **Enable Scoring**: this enables Activities to be given a score value that will be given to the student by selecting the correct answer, or completing the Activity correctly. 

- **Activity**: this will display the text you entered as the Name of your Activity. 

- **Type**: this displays the type of Activity. 

- **Score**: this displays the score value of the Activity. This will display _Practice_ for non-scored Activities, and a the score value of the Activity for scored Activities. 

- **Token**: this is the replacement token that is used in lab instructions to represent this Activity in the lab. Simply place this Replacement Token where you would like the Activity to appear in the lab instructions. 

- **Edit**: click this to edit the Activity. 

- **Delete**: click to delete the Activity. Once it is deleted, there is no way to recover the Activity. 

- **Insert**: click to insert the Activity in your current position in the lab instruction editor. 

[Back to Top](#activities)

> [ps-simple-explanation]:
> **Binary**  (Simple Script (Pass/Fail)
>
> This sample is gauging a file's size on the Windows file system. If the file is less than 1000 bytes the user is successful, otherwise they are unsuccessful.

> [ps-simple-code]:
> ```PowerShell-linenums
> $result = $false
> $file = (Get-Item C:\Users\LabUser\file.txt).length
> if($file -lt 1000){
>     echo "Success, filesize is $file"
>     $result = $true
> }
> $result
> ```

> [ps-complex-explanation]:
> **Explicit Score Value Example** (Complex Script - Partial Credit/Multiple Conditions)
>
> This sample actually reads the host entry on a Windows machine, and identifies both the hostname and any IPs associated with it. From there it validates if it has both the correct IP and hostname. With this design the user can get variable scores based on the following:
> 
> - Full credit if both the IP and hostname are found.
> - Partial credit if the IP is found, but not the hostname
> - No credit if the IP is not found

> [ps-complex-code]:
>```PowerShell-linenums
>$result = $False
>$hostname = [System.Net.DNS]::GetHostEntry('')
>if ($hostname.HostName -eq "LabVM" -and $hostname.AddressList.IPAddressToString -contains "192.168.1.4"){
>     #set_activity_result 1 "Success"
>     $result = $True
> }elseif($hostname.AddressList.IPAddressToString -contains "192.168.1.4"){
>     #set_activity_result .5 "Partially correct"  
> }else{
>     "Value not found"    
> } 
> $result
> ```

> [bash-simple-explanation]:
> **Binary**  (Simple Script (Pass/Fail) 
>
> This sample is gauging a file's size on the linux file system. If the file is less than 1000 bytes the user is successful, otherwise they are unsuccessful.

> [bash-simple-code]:
> ```Bash-linenums
> RESULT=False
> file=$(stat --format=%s /etc/passwd)
> if [ $(echo $file) -lt 1000 ]
> then 
>  echo "success, filesize is $file"
>  RESULT=True
> fi
> echo $RESULT
> ```

> [bash-complex-explanation]:
> **Explicit score value Example** (Complex Script - Partial Credit/Multiple Conditions)
>
> This sample actually reads the /etc/hosts file on a Linux machine, and searches for a line that contains a specific IP. From there it if the IP has the correct hostname. With this design the user can get variable scores based on the following:
> 
> - Full credit if both the IP and hostname are found.
> - Partial credit if the IP is found, but not the host name
> - No credit if the IP is not found

> [bash-complex-code]:
> ```Bash-linenums
> RESULT=False
> host=$(cat /etc/hosts | grep 192.168.1.2)
> if [[ $(echo $host) == "192.168.1.2 linuxvm"* ]]
> then
>  set_activity_result 1 "Success"
>  RESULT=True
> elif [[ $(echo $host) == "192.168.1.2"* ]]
> then 
>  set_activity_result .5 "Partially correct"
> else 
>  echo "value not found"
> fi
> echo $RESULT
> ```

[Back to Top](#activities)
