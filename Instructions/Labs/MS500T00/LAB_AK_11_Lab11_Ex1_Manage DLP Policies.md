# Module 11 - Lab 11 - Exercise 1 - Manage DLP Policies  


In your role as Holly Dickson, Adatum’s Security Administrator, you have Microsoft 365 deployed in a virtualized lab environment. As you proceed with your Microsoft 365 pilot project, your next steps are to implement Data Loss Prevention (DLP) policies at Adatum. You will begin by creating a custom DLP policy, and then you will test DLP policies related to email message archiving and emails with sensitive data. 

### Task 1 – Create a DLP policy with custom settings

In this exercise you will create a Data Loss Prevention policy in the Security & Compliance Center to protect sensitive data from being shared by users. The DLP Policy that you create will inform your users if they want to share content that contains U.S. Social Security addresses.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**. 

2. In **Microsoft Edge**, the Office 365 Security & Compliance Center tab should still be open. If so, select it and proceed to the next step. If you closed it, then in a new tab, navigate to **https://protection.office.com**.

3. In the **Security &amp; Compliance Center**, in the left navigation pane, select **Data loss prevention** and then select **Policy**.

4. In the **Policy** window, select **+Create a policy** to start the wizard for creating a new data loss prevention policy.

5. On the **Start with a template or create a custom policy** page, you want to select **Custom** in the left pane and **Custom policy** in the middle pane; however, by default, both these options should already be selected (if not, then select them now), so simply select **Next**.

6. In the **Name your policy** page, type **Social Security DLP Policy** in the **Name** field and **Protect social security numbers from being shared** in the **Description** field. Select **Next**.

7. On the **Choose locations** page, select the **Protect content in Exchange email, Teams chats, and channel messages and OneDrive and SharePoint documents** option and then select **Next**.

8. On the **Customize the type of content you want to protect** page, the option **Find content that contains:** needs to be selected, which it should be by default.

9. Under **You must select at least one classification type**, select **Edit.**

10. In the **Choose the types of content to protect** page, select the **Add** drop-down field, and in the drop-down menu, select **Sensitive info types**.

11. In the Sensitive info types window, select **(+) Add**.

12. In the search field type **social** and wait until the search results are displayed.

13. In the list of search results, select the **U.S. Social Security Number (SSN)** check box, and then select **Add**.

14. Once you receive the message indicating **1 sensitive info type added,** select **Done**.

15. On the **Choose the types of content to protect** window, under the **Content contains** bar, select **Any of these** in the drop-down field (this should be selected by default), and then select **Save**.

16. On the **Customize the type of content you want to protect** page, **U.S. Social Security Number (SSN)** should now appear under the **Find content that contains** option.

17. Verify that the **Detect when this content is shared:** check box is selected.

18. In the field below this, select the drop-down arrow and select **only with people inside my organization**.

19. Select **Next**.

20. On **What do you want to do if we detect sensitive info?** page, check that **Detect when content that's being shared contains** is selected. In the field below this, **10** is entered. Change this to **2**. 

21. Notice that **Send incident reports in email** is marked and **Block people from sharing and restrict access to shared content** is marked.  This configuration means that if Microsoft DLP detects 2 or more US Social Security numbers present in an email, the email will not be delivered and a report will be sent to you and your global admin.  Once you confirm these settings select **Next.**

21. On the **Customize access and override permissions** page, select **Next**.

22. On the **Do you want to turn on the policy or test things out first?** page select **Yes, turn it on right away** and select **Next**.

22. Check the configuration on the **Review your settings** page, select **Back** if you need to correct any settings, and then select **Create** once you’re satisfied with the settings.

You have now created a DLP policy that scans for US Social Security numbers in emails and documents that are sent or shared in your organization.


# Proceed to Exercise 2 
