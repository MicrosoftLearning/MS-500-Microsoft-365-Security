# Module 9 - Lab 9 - Exercise 2 - Implement Windows Information Protection  

Now that you have implemented Azure Information Protection as part of your pilot project at Adatum, you’re now ready to implement Windows Information Protection. In this exercise, in your role as Holly Dickson, you will create a WIP policy (Client App protection policy for Windows) that is applied to any member of the WIP Users group who has an MDM enrolled device in Intune.


### Task 1 - Create a Group for Compliance Testing

To test features in your Adatum pilot project, you will create a new mail-enabled security group and assign two users to the group – Joni Sherman and Lynne Robbins. These will be your two test users involved in the Windows Information Protection (WIP) pilot program. This group will then be used in the next task when you configure MDM auto-enrollment for new devices in your tenant. 

1. You should be logged into the LON-CL1 VM. You should still be logged into LON-CL1 as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**. 

2. In **Microsoft Edge**, select the **Microsoft 365 admin center tab** or open a new tab and go to **https://admin.microsoft.com**.

3. the **Microsoft 365 admin center**, in the left navigation pane, select **Groups** and then select **Groups** below it.

4. Select **Add a group** to create a new group for compliance testing. 

5. In the **Add a group** window, enter the following information:

6. Fill all the fields to create the **WIP Users** group:

	- Type: **Mail-enabled security**

	- Name **WIP Users**

	- Group email address: Set to **wipusers** for the alias of the group email address.

	- Group email address domain: to the right of the group email address alias is the email address domain. **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) should be displayed here.

7. Select **Next**, and then select **Create Group**. Once the group is created select **Close**.

8. In the **Microsoft 365 admin center** tab, refresh the page to display the WIP users group in the list of Groups. You may have to wait a few minutes before you see the WIP users group.  Click Refresh to check if the group is ready.

9. Once **WIP Users** appears In the **Groups** window, select it.

10. In the **WIP Users** window, select the **Members** tab. 

11. In the **Members** tab, under the **Members** section, select **View all and manage members**.

12. In the **View members** window, select **+Add members**. This displays the list of users.

13. In the list of users, select **Joni Sherman** and **Lynne Robbins**, then scroll to the bottom of the list and select **Save**, and then select **Close**.

	‎**Note:** It may take a few minutes for both Joni and Lynne to display in the list of users. Simply refresh the list until both users appear.

14. Close the **WIP users** window.

15. Leave your browser open to the Microsoft 365 admin center and proceed to the next task.

### Task 2 – Configure Mobile Device Management Auto-enrollment

In this task you will activate MDM auto-enrollment for new devices in your Adatum Corporation tenant. The devices will belong to members of the WIP Users group that you created in Azure AD in the prior task. You will also configure Intune as your mobile device management authority. Activating MDM auto-enrollment is required so that you can implement Windows Information Protection in a later lab.

1. In **Microsoft Edge**, select a new tab and enter the following URL in the address bar: **https://portal.azure.com**.

2. On the **Welcome to Azure** page, select **Continue to Azure Portal website.**

3. If a **Welcome to Microsoft Azure** dialog box appears, select **Maybe later** and then select **More Services**. 

4. In the **Microsoft Azure** portal, in the left navigation pane, select **All Services**.

5. In the **All services** window, type **Azure Active Directory** in the search box, and then select **Azure Active Directory**, which will appear in the right pane.

6. This returns the **Adatum Corporation – Overview** page. Under the **Manage** section in the middle of the page, scroll down and select **Mobility (MDM and MAM)**.

7. In the right pane, select **Microsoft Intune**.

8. This returns the **Configure** window. For the **MDM User scope** option, select **Some.** This will display a **Groups** section. 

9. Select the **Groups** section and then select the arrow on the right side of the section. 

10. In the **Select groups** pane, scroll down through the list of groups, select **WIP Users**, and then at the bottom of the pane select **Select**.

11. This returns the **Configure** window. Select **Restore default MDM URLs** to ensure the correct URLs are set.

12. Select **Save** on the menu bar at the top of the page.

13. In the left navigation pane in the Azure portal, select **All Services.**

14. In the **All services** window, type **Intune** in the search box, and then select **Intune**, which will appear in the right pane.

15. This returns the **Microsoft Intune – Overview** page. Under the **Manage** section in the middle of the page, select **Device enrollment.**

16. In the middle of the screen you should see "MDM authority" is set to Intune.

17. In your Microsoft Edge browser, you can close the Azure portal tab, which should return you to the Microsoft 365 admin center tab.

You have configured automatic enrollment in Intune for devices of users in the WIP Users security group.


### Task 3 – Configure Windows Information Protection

In this task you will create a WIP policy and assign it to the WIP Users group that you just created. 

1. You should be logged into Client 1 VM (LON-CL1). You should still be logged into your Client 1 VM as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson.** 

2. In **Microsoft Edge**, if you have the Azure portal open in a tab, then select it now; otherwise, enter **https://portal.azure.com/** and, if necessary, sign in as **holly@M365xZZZZZZ.onmicrosoft.com.**

3. In the **Azure portal**, if a window displays indicating **You have free Azure Advisor recommendations**, then close the window now.

4. In the **Azure portal**, in the left navigation bar, select **All services.**

5. In the **All services** window, enter **client** in the **Search** box at the top of the window, and then in the right pane, select **Client apps.**

6. In the **Client apps** window, in the middle pane under **Manage**, select **App protection policies**.

7. In the **Client apps – App protection policies** window, in the right pane, select **+Create policy** from the top menu bar.

8. In the **Create policy** window, select **Windows 10** enter the following information:

	- Name: **WIP Client Protection**

	- Description: leave blank

	- Enrollment state: **With enrollment**

	- Protected apps: select the **Next**, and in the **Targeted apps** tab, select **+ Add** in the Protected Apps area. In the **Add apps** window, scroll to the bottom and select **Office-365-ProPlus-1810-Allowed.xml** (this file may be difficult to find in the list because the file name is cut off in the display) and then select **OK**. 

	- Exempt apps: leave blank as there are no exempt apps in this policy. On the **Targeted apps** tab, select **Next**.

	- Required settings: in the **Windows Information Protection mode** setting, select **Block**. In the **Corporate identity** field, verify that it says **M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your tenant ID provided by your lab hosting provider) and then select **Next**.

	- Advanced settings: do not change the default value.  Select **Next**.

9. Select **Next** until you get to the **Review + Create** tab. Select **Create** on the bottom of the screen.

10. On the **Client apps - App protection policies** window, in the right pane, note the value of the **Deployed** column is **No** for the **WIP Client Protection** policy that you just created. You are now going to deploy this policy. Select the **WIP Client Protection** policy.

11. In the **Intune App Protection** window, in the middle pane under the **Manage** section, select **Properties**.

12. In the **Intune App Protection - Properties** window, in the right pane, under the **Assignments** section, select **Edit**.  

13. In the **Edit policy** window, select **+ Select groups to include**. Select the **WIP Users** group and then select **Select** at bottom of the screen.

14. In the menu bar at the top of the right pane, select **Review + Save** tab. And then select **Save**.

15. In the navigation thread at the top of the window (above the **Intune App Protection - Properties** title), select **Client apps – App protection policies**. In the list of policies in the right pane, note the value of the **Deployed** column has now changed from **No** to **Yes** for the **WIP Client Protection** policy.

16. Leave your Client 1 VM and browser open for the next lab.

You have now created an **App protection policy** (which is a Windows Information Protection policy) that protects files in Office 365 ProPlus for users with enrolled devices in the **WIP Users** group.


# End of Lab
