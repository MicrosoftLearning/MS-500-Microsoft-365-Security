# Module 3 - Lab 2 - Exercise 2 - Assign Directory Roles


### Task 1:  Make a user eligible for a role


In the following task you will make  a user eligible for an Azure AD directory role.


1.  Sign in to Azure portal

1.  In the Azure Portal, click **All services** and search for and select **Azure AD Privileged Identity Management**.

     ![Screenshot](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  Select **Roles** under the **Manage** section. If this is option is still greyed you may need to refresh your browser.

1.  Select **Billing Administrator**.

1.  Select **+ Add assignments** to open Select a member. In the Add assignments screen click **No member selected**.

1.  In the **Select a member screen** select **Patti Fernandez** and then click **Select**, then click **Next**.

1.  In Add assignments screen on the Setting tab verify the **Eligible** checkbox. Click **Assign**.  Review the added member in the assignment window.

1.  When the role is assigned, the user you selected will appear in the members list with a Start and End date for the role. 


### Task 2: Make a role assignment permanent


Follow these steps if you want to make a role assignment permanent.



1.  In the Azure Portal, click **All services** and search for and select **Azure AD Privileged Identity Management**.

     ![Screenshot](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  Click **Azure AD roles**.

1.  Click **Assignments** under the **Manage** section.
 
1.  Click the entry for Patti, click **Update** and then mark the **Permanently eligble** box.  In Membership settings click **Save**.

**Results**: The Billing Administrator role is now listed as **permanent** for Patti Fernandez.  In other words Patti is permanently eligible to be elevated to the Billing Administrator role.


### Task 3: Remove a user from a role


You can remove users from role assignments, but make sure there is always at least one user who is a permanent Global Administrator.



1.  In the Azure Portal, click **All services** and search for and select **Azure AD Privileged Identity Management**.

     ![Screenshot](../Media/a52510a3-b2a2-4b21-91a8-ee7f34b39a72.png)

1.  Click **Azure AD roles**.

1.  Click **Assignments** under the **Manage** section.

1.  Select Patti Fernandez.
 
1.  In the top menu, click **Remove**.
 
1.  In the message that asks you to confirm, click **Yes**. The role assignment will be removed.


# Continue to exercise 3



