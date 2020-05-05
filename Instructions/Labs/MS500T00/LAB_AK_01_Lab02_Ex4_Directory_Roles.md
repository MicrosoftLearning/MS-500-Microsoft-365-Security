# Module 1 - Lab 2 - Exercise 4 - Directory Roles (General)


### Task 1: Start an access review for Azure AD directory roles in PIM


Role assignments become "stale" when users have privileged access that they don't need anymore. In order to reduce the risk associated with these stale role assignments, privileged role administrators or global administrators should regularly create access reviews to ask admins to review the roles that users have been given. This task covers the steps for starting an access review in Azure AD Privileged Identity Management (PIM).


1.  Return back to the browser that is logged in as your Global Admin Account Holly Dickson.

1.  From the PIM application main page click **Azure AD Roles** under the **Manage** section click **Access reviews** and click > **New**.

     ![Screenshot](../Media/1704b3b2-05a7-47c8-a3e3-20ba6546b9d6.png)

1.  Enter the following details and click **Start**:

      - Review name:  **Global Admin Review**
      - Start Date:  **Today's Date** 
      - Frequency: **One time**
      - End Date:  **End of next month**
      - Review role membership:  **Global Administrator**
      - Reviewers:  **Holly Dickson**
 
 
     ![Screenshot](../Media/84274ed2-be53-4b3f-853a-c85f0dcfeab2.png)
 
1.  Once the review has completed and has a status of Active, click on the **Global Admin Review**. You may need to refresh the view in Azure.

1.  Select **Results** and see the outcome of **Not reviewed**.

     ![Screenshot](../Media/04c32a26-be67-48dd-bf3d-7b60e81e2fff.png)

### Task 2: Approve or deny access


When you approve or deny access, you're just telling the reviewer whether you still use this role or not. Choose Approve if you want to stay in the role, or Deny if you don't need the access anymore. Your status won't change right away, until the reviewer applies the results. Follow these steps to find and complete the access review:


1.  In the PIM application, select **Review access**. 

2.  Select the **Global Admin Review**.

     ![Screenshot](../Media/3f5a8e6a-05a7-4cc0-96ea-d1a10d23c38f.png)

3.  Unless you created the review, you appear as the only user in the review. Select the check mark next to Holly Dickson.

     ![Screenshot](../Media/081d9886-8482-4d62-827c-68eb380c00a0.png)

5.  Close the **Review Azure AD roles** blade.

### Task 3: Complete an access review for Azure AD directory roles in PIM


Privileged role administrators can review privileged access once an access review has been started. Azure AD Privileged Identity Management (PIM) will automatically send an email prompting users to review their access. If a user did not get an email, you can send them the instructions in how to perform an access review.

After the access review period is over, or all the users have finished their self-review, follow the steps in this task  to manage the review and see the results.



1.  Go to the Azure portal and select the **Azure AD Privileged Identity Management**.

1.  Select **Azure AD Roles**.

2.  Select the **Access reviews**.


3.  Select the Global Admin Review.


1.  Review the blade.

     ![Screenshot](../Media/1e6f3ff2-0797-4903-98ef-fc9cf2fccaad.png)


### Task 4: Configure security alerts for Azure AD directory roles in PIM


You can customize some of the security alerts in PIM to work with your environment and security goals. Follow these steps to open the security alert settings:



1.  Open **Azure AD Privileged Identity Management**.

1.  Click **Azure AD roles**.

1.  Click **Alerts** and then **Settings**.


1.  Click an alert name to configure the setting for that alert.


# continue to exercise 5
