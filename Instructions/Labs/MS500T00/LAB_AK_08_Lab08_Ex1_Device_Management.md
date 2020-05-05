# Module 8 - Lab 8 - Exercise 1 - Enable Device Management


You are Holly Dickson the security administrator for Adatum Corporation, and you have Microsoft 365 deployed in a virtualized lab environment. In this lab, you will manage user devices using Intune.

In this exercise you will verify that Adatum has installed the Enterprise Mobility + Security E5 product. You will then verify that it has been assigned to your test user accounts, and you will assign a license to Holly Dickson. You will then enable device management with Intune.

### Task 1: Verify and assign Enterprise Mobility + Security licenses

In this task you will verify that Adatum has installed the Enterprise Mobility + Security E5 product and you will check how many licenses are available. You will then verify that a license has been assigned to your test user accounts, and you will assign a license to Holly Dickson.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **lon-cl1\admin** account and into Microsoft 365 as Holly Dickson **(holly@M365xZZZZZZ.onmicrosoft.com)** with a password of **Pa55w.rd**.

2. In **Microsoft Edge**, you should still have a tab open to the **Microsoft 365 admin center**; if so, select that tab now. If not, enter **https://portal.office.com**, sign in as **Holly**, and in the **Microsoft Office Home** page, select **Admin**.

3. In the **Microsoft 365 admin center**, select **Billing** in the left navigation pane, and then under it, select **Licenses**.

4. On the **Licenses** page, select **Enterprise Mobility + Security E5.**

5. In the **Enterprise Mobility + Security E5** page, under the list of users, verify that your pilot team members – **Alex Wilber**, **Joni Sherman**, **Lynne Robbins**, and the **MOD Administrator** – were each assigned a license.

    **Note:** These user accounts were created as part of your Office 365 tenant, and during that process, they were each assigned an Office 365 E5 license and an Enterprise Mobility + Security E5 license.

6. The one user who was not assigned an Enterprise Mobility + Security E5 license is your Global Administrator, Holly Dickson. When you created Holly&#39;s user account in an earlier lab, you may have been instructed at that time to only assign her an Office 365 E5 license. You will now assign her an Enterprise Mobility + Security E5 license.  If Holly already has an Enterprise Mobility + Security E5 license you can skip to the next task.

    To assign Holly a license, select **+Assign licenses**.

7. On the **Assign licenses to users** page, select the **Enter a name or email address** field, and in the list of users that appears, select **Holly Dickson**.

8. Select **Assign**.

9. Close the **You assigned a license to Holly Dickson** window.

10. Leave your Client 1 VM open for the remainder of this lab.

You have now verified the available Enterprise Mobility + Security E5 licenses in your tenant and assigned an EMS E5 license to Holly.


### Task 2: Enable device management with Intune

Devices must be managed before you can give users access to company resources or manage settings on those devices. This begins with enabling device management with Intune.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **Admin** account and into Microsoft 365 as Holly Dickson **(holly@M365xZZZZZZ.onmicrosoft.com)** with a password of **Pa55w.rd**.

2. In **Microsoft Edge**, you should still have a tab open to the **Microsoft Azure portal**; if so, select that tab now. If not, open a new tab and enter the following URL in the address bar: **https://portal.azure.com**.

3. In the **Microsoft Azure portal**, select **More services**.

4. On the **All services** window, enter **Intune** in the **Search** box, and then in the details pane on the right, select **Intune**.

5. In the **Microsoft Intune – Overview** page, in the middle left under the Manage section, select **Device enrollment**.

6. In the **Choose MDM Authority** window that appears, select **Intune MDM Authority** and then select **Choose** if it appears.

7. On the **Device enrollment** page, note the information at the top of the detail pane. Intune is now Adatum's MDM authority.

8. In the navigation thread at the top of the page (**Home > Microsoft Intune > Device enrollment**), select **Microsoft Intune**.

9. In the **Microsoft Intune – Overview** page, in the middle under Manage, select **Device compliance**. Even though no data is currently available, review the information that will be presented for this option regarding device management.

11. Leave your Client 1 VM and the Azure portal tab open and proceed to the next exercise.

You have now successfully selected Intune as the preferred MDM solution for your tenant and ensure Holly Dickson has the appropriate license.


# Proceed to Exercise 2
