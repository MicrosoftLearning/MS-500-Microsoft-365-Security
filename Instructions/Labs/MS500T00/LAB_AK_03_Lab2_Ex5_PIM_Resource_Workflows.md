# Module 3 - Lab 2 - Exercise 5 - PIM resource workflows


### Task 1:  Configure the Global Administrator role to require approval.

1.  You should still be logged in as Holly from the previous exercise.  Open **Azure AD Privileged Identity Management**.

1.  Click **Azure AD roles**.

1.  Click **Settings** 

1.  Select **Global Administrator**.

1.  Click **Edit**, scroll down and mark **Require Approval to activate**.  

2.  Click **Select approver(s)** and assign Holly Dickson as the approver and click **Select**.  Then click **Update**.


### Task 2: Enable Patti for Global Administrator privileges.

1.  Open **Azure AD Privileged Identity Management**.

1.  Click **Azure AD roles**.

1.  Click the **Quick Start** and select **Assign eligibility**.

     ![Screenshot](../Media/ae3755ac-bd82-4e70-a102-ccbfc3aee48f.png)

1.  Select **Global Administrator**.

1.  Select **+ Add assignments**, select **Select member(s)**, and then select **Patti Fernandez**. Click **Select**.

2.  Click **Next** and then click **Assign**.

1.  Open an in Private Browsing session and login to https://portal.azure.com as Patti Fernandez.  You might still have this browser open from earlier exercise.

1.  Open **Azure AD Privileged Identity Management**.

1.  Select **My Roles**.

     ![Screenshot](../Media/e84f0715-c71e-4b1c-87ed-4e5c0c38d501.png)

1.  **Activate** the Global Administrator Role.

     ![Screenshot](../Media/55eb14b5-540a-4d26-aed7-0b96d162fb31.png)

1.  Verify Patti's identity using the wizard if necessary.

1.  Return back to **My Roles** in **Azure AD Privileged Identity Management**.

1.  Click **Activate** near the Global Administrator Role.

1.  Enter a reason for the activation **I need to carry out some administrative tasks** and click **Activate**.

Eventually you should see a notice that your request is "pending approval".


### Task 3: Approve or deny requests for Azure resource roles in PIM


With Azure AD Privileged Identity Management (PIM), you can configure roles to require approval for activation, and choose one or multiple users or groups as delegated approvers. Follow the steps in this article to approve or deny requests for Azure resource roles.


###### View pending requests


As a delegated approver, you will receive an email notification when an Azure resource role request is pending your approval. You can view these pending requests in PIM.


1.  Switch back to the browser you are signed in with your Global Administrative account Holly Dickson.

1.  Open **Azure AD Privileged Identity Management**.

1.  Click **Approve requests**.

     ![Screenshot](../Media/fbc2f18d-f5a2-4139-b92d-7c19311aec1c.png)

1.  Select the request from Patti and click **Approve**.

1.  Enter a reason **Granted for this task** and click **Confirm**.

1.  A notification appears that Patti is approved.

1.  Switch back to the In Private Browsing session where Patti is signed in and click **My Roles** and then select **Active assignments** note the status is now activated for Global Administrator.

     ![Screenshot](../Media/fe734263-57c8-4cc9-b79f-848d7d4f9488.png)


# continue to exercise 6

