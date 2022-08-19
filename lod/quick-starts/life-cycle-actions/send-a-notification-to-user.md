# Send a notification to the user

This is the first in a Series of Quick Starts about Life Cycle Actions in Skillable Studio.

In this Quick Start, you will configure a notification to popup for the user, in their lab environment

Configuring a life cycle notification is simple, and can be changed later to display a different message on the popup. Life Cycle Actions are used to notify the user of important information or display a message, at specific stages within the lab. 

> [!ALERT]You must have a lab profile created before you can configure a life cycle action. If you have not created a lab profile, have a look at our [documentation for creating a lab profile](URL).

Estimated time to completion: **5 minutes**

1. First, **navigate to the lab profile**, that you wish to configure a life cycle action for.

1. Click **edit profile** in the upper-right corner.

1. Click the **Life Cycle** tab.

    !IMAGE[](\docs\lod\images\life-cycle-tab.png)

1. Click **Add Life Cycle Action**.

    !IMAGE[](\docs\lod\images\add-life-cycle-action.png)

1. From the **Action** drop-down menu, select **Send Notification to User**.

    !IMAGE[](\docs\lod\image\send-notification-to-user.png)

1. From the **Event** drop-down menu, select **Built**. The is allow the notification to be displayed once the lab is fully built.

    !IMAGE[](\docs\lod\images\built.png)

1. In the **Name** field, leave this blank. 

    > [!KNOWLEDGE] Entering a name allows only one notification with that name to be executed in the lab. If there are two life cycle actions with the same name, on the same event, the action created last will be executed in the lab. 
    >
    >Leaving the name field blank will allow multiple notificaitons to popup, during the same event. 
    >
    >For example, you could have a notification welcoming the user to the lab, and another notification telling them to log in once the lab is launched, that executes when the lab is built, as long as the Life Cycle Actions were not configured with a name. 

1. Leave the **Delay** at 0. 

    >[!KNOWLEDGE] The **Delay** field is **optional**, and is used to introduce a delay between the moment the life cycle event occurs and the action is executed. 

1. Leave the **Error Action** as _Default_.

    > [!KNOWLEDGE] The **Error Action** drop-down menu is used to set how errors will be handled in the lab. The default setting is to save errors to the lab instance in Skillable Studio. Alternatively you can set errors to notify the user, or end the lab.

1. Check the **Enabled** box. If this is unchecked, the life cycle action will not be executed.

1. Click to copy this message and paste into the text field; +++Welcome to the Lab Environment, are you ready to learn something new?+++. The welcome message that will be displayed to the user when the lab is launched. 

1. Click **OK**, and then click **Save**. 

1. **Add a note**, describing the changes you've made to the lab profile, and **click OK**.

1. Click **launch**, to launch the lab.

Did you see the notification pop up in the lower-right corner of the lab interface? If you missed it, you can cancel the lab and launch it again. The notification will pop up once the lab is built, on all launched of this lab. If your lab is deploying resources, it may take a few minutes for the notification to appear, since it is configured to display once the lab is completely built. 

Now that you have configured your first Life Cycle Action to send a notification, click on the link below to go through the next Quick Start where you will configure a Life Cycle Action to send an email to the user. 

[Send E-mail to User](/lod/quick-starts/life-cycle-actions/email-student.md)
