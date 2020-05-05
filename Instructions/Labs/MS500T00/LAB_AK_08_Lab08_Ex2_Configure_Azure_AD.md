# Module 8 - Lab 8 - Exercise 2 - Configure Azure AD for Intune 

In this exercise you will activate the automatic client enrollment to Intune for Mobile Device Management (MDM). This will allow you to manage mobile device access and set policies for restricting access to devices unless certain actions are adopted, such as strong passwords and screen timeouts.

### Task 1: Integrate Azure AD with Intune

1. You should still be logged into your Client 1 VM (LON-CL1) as the **Admin** and in Microsoft 365 as **Holly Dickson**.

2. In the **Azure portal** , in the **All services** box, search for and select **Azure Active Directory**.

3. On the **Adatum Corporation - Overview** window, in the middle pane under **Manage** select **Mobility (MDM and MAM),** and then in the details pane on the right, select **Microsoft Intune**.

    **Note:** If you see a notification that automatic enrollment is available only for Azure AD Premium, press F5 to refresh the page in your web browser and then select **Microsoft Intune**.

4. On the **Configure** window, in the **MDM user scope** row, select **All**.

    **Note:** By setting this parameter to **All**, you are allowing all users who join their devices to Azure AD to automatically enroll them to Intune as well.

5. Select **Restore default MDM URLs** to ensure the correct URLs for client enrollment are configured.

6. In the menu bar at the top of the **Configure** window, select **Save**.

7. Leave the Azure portal open for the next task.

You have now configured your tenant so that all users can enroll their clients to Intune as soon they log in to their Windows 10 Client with their Azure AD account credentials.


### Task 2: Configure Azure AD join

1. In the **Azure portal** , in the left navigation pane, select **Azure Active Directory.**

2. In the **Adatum Corporation – Overview** window, in the middle section under **Manage**, select **Devices**.

3. In the **Devices – All devices** window, in the details pane on the right, verify that no devices are listed. This is because no device has yet to be joined to Azure Active Directory.

4. In the **Devices – All devices** window, in the middle pane under **Manage** , select **Device settings**.

5. In the details pane that appears on the right, in the **Users may join devices to Azure AD** row, verify that **All** is selected. This means that all Azure AD users can join their devices to Azure Active Directory.

6. The **Additional local administrator on Azure AD joined devices** row is currently set to **None**. Select **Selected**.

7. Below this field, in the **Selected** section (where it displays **No member selected),** select this section.

8. In the **Local administrators on devices** window, select **+Add**

9. In the **Add members** pane on the right, select **Alex Wilber** , select **Select** at the bottom of the screen, and then select **Ok**.

10. Back in the **Device settings** detail pane on the right, scroll down and verify that **Require Multi-Factor Auth to join devices** is set to **No**. The **Maximum number of devices per user** is currently set to **50.** Select this field and in the menu that appears, select **10.**

11. In the menu bar at the top of the detail pane, select **Save**.

12. Leave the Azure portal open for the next task.

You have changed the default settings for users to join their devices to your Azure AD tenant.


### Task 3: Create dynamic Azure AD device group

1. In the **Azure portal** , in the left navigation pane, select **Azure Active Directory.**

2. In the **Adatum Corporation – Overview** window, in the middle section under **Manage,** select **Groups**.

3. In the **Groups – All groups** window, in the details pane on the right, select **+New group** on the menu bar.

4. In the **New Group** window, enter the following information:

    - Group type: **Security**
    - Group name: **Enrolled Devices**
    - Membership type: **Dynamic Device**
    - Owner: select the right **>** arrow, then in the **Add Owners** window, select **Alex Wilber** and select **Select**.

5. At the bottom of the window, select the **Dynamic device members**

6. On the **Dynamic membership rules** pane, configure the following fields for this expression:

    - Property: select the drop-down arrow and select **managementType**
    - Operator: select the drop-down arrow and select **Equals**  
    - Value: enter **MDM**

3. Select the **Rule syntax** field. It should display the following rule:

    **(device.managementType -eq  &quot;MDM&quot;)**

7. Select **Save** in the menu bar at the top of the window.

8. In the **New Group** window, select the **Create** button at the bottom of the window.

9. The **Enrolled Devices** group should now appear in the list of groups.

10. Leave the Azure portal open for the next task.


# Proceed to Exercise 3
