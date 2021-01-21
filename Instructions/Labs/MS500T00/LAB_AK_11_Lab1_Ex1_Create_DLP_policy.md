# Module 11 - Lab 11 - Exercise 1 - Manage DLP Policies  


In your role as Holly Dickson, Adatum’s Security Administrator, you have Microsoft 365 deployed in a virtualized lab environment. As you proceed with your Microsoft 365 pilot project, your next steps are to implement Data Loss Prevention (DLP) policies at Adatum. You will begin by creating a custom DLP policy, and then you will test DLP policies related to email message archiving and emails with sensitive data. 

### Task 1 – Create a DLP policy with custom settings

In this exercise you will create a Data Loss Prevention policy in the Security & Compliance Center to protect sensitive data from being shared by users. The DLP Policy that you create will inform admins if users want to share content that contains U.S. Social Security addresses.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**. 

2. In **Microsoft Edge**, navigate to **https://compliance.microsoft.com/**.

3. In the **Microsoft 365 Compliance**, in the left navigation pane, select **Policies** and then select **Data Loss prevention**.

4. In the **Policy** window, select **+ Create Policy** to start the wizard for creating a new data loss prevention policy.

5. On the **Start with a template or create a custom policy** page, you want to select **Custom** in the left pane and **Custom policy** in the middle pane; however, by default, both these options should already be selected (if not, then select them now), so simply select **Next**.

6. In the **Name your policy** page, type **Social Security DLP Policy** in the **Name** field and **Protect social security numbers from being shared.** in the **Description** field. Select **Next**.

7. On the **Choose locations to apply the policy** page, enable protection for every location (default settings) and then select **Next**.

1. On the **Define Policy settings** click **Next**

1. On the **Customize advanced DLP rules** click **+ Create Rule**

1. On the ** Create Rule** Name your first rule **SSN Low volume**

1. Click on the **+ Add Conditions** and select **Content is shared from Microsoft 365**. Veryfy that **Only with people inside my organization** is selected.

1. Click on the **+ Add Conditions** and select **Content contains**.

1. Click **Add** and select **Sensitive info types**

1. In the search field type **social** and press *Enter*.

1. In the list of search results, select the **U.S. Social Security Number (SSN)** check box, and then click **Add**.

1. On the new sensitive info type line, change the **Instance Count** to "**1** to **1**"

1. In the **Incident Report** section, click **Select an option** and set the severity level to **Low**

1. Set the **Send an alert to admins when a rule match occurs** to **On**

1. Click **Save**

1. On the **Customize advanced DLP rules** click **+ Create Rule**

1. On the ** Create Rule** Name your first rule **SSN High volume**

1. Click on the **+ Add Conditions** and select **Content is shared from Microsoft 365**. Veryfy that **Only with people inside my organization** is selected.

1. Click on the **+ Add Conditions** and select **Content contains**.

1. Click **Add** and select **Sensitive info types**

1. In the search field type **social** and press *Enter*.

1. In the list of search results, select the **U.S. Social Security Number (SSN)** check box, and then click **Add**.

1. On the new sensitive info type line, change the **Instance Count** to "**2** to **Any**"

1. In the **Actions** section click on **+ Add an action** and select **Restrict access or encrypt the content in Microsoft 365 locations**

1. Check the **Restrict access or encrypt the content in Microsoft 365 locations** box

1. In the newly created action, select **Block everyone**.

1. In the **Incident Report** section, click **Select an option** and set the severity level to **Medium**

1. Set the **Send an alert to admins when a rule match occurs** to **On**

1. Click **Save**

1. On the **Customize advanced DLP rules** click **Next**

1. On the **Test or turn on the policy** page, **Yes, turn it on right away** and click **Next**.

22. Check the configuration on the **Review your settings** page, select **Back** if you need to correct any settings, and then select **Submit** once you’re satisfied with the settings.

You have now created a DLP policy that scans for US Social Security numbers in emails and documents that are sent or shared in your organization.


# Proceed to Exercise 2 
