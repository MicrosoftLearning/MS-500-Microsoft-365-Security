# Module 9 - Lab 9 - Exercise 1 - Implement Azure Information Protection  


In your role as Holly Dickson, Adatum’s Security Administrator, you have Microsoft 365 deployed in a virtualized lab environment. As you proceed with your Microsoft 365 pilot project, your next steps are to implement Azure Information Protection (AIP) and Windows Information Protection (WIP) at Adatum. You will begin by configuring AIP and then using AIP on a client and verifying an AIP policy. You will then perform similar steps for WIP by configuring it for Adatum and then implementing WIP.

### Task 1 – Install the Azure Information Protection client

To implement Azure Information Protection as part of your pilot project at Adatum, you must first install the AIP client from the Microsoft Download Center.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson** with a password of **Pa55w.rd**. 

2. In **Microsoft Edge**, open a new tab and enter the following URL in the address bar: **https://aka.ms/aipclient**

3. On the **Download Center** page, scroll down to the **Microsoft Azure Information Protection** section and select **Download**.

4. In the **Choose the download you want** window, select **AzInfoProtection.exe** and then select **Next.**

5. In the taskbar that appears at the bottom of the page, select **Save**.

6. Once the download has successfully completed, in the taskbar that appears at the bottom of the page, select **Run.**

7. If the first page of the **Microsoft Azure Information Protection installation wizard** does not display, select the icon for it on the taskbar to display the wizard.

8. On the license and terms page, uncheck the **Help improve Azure Information Protection by sending usage statistics to Microsoft** option, and then select **I agree**.

9. On the **Completed Successfully** window, select **Close**. 

10. Leave your VM and browser open and proceed to the next task.

You have successfully installed the AIP client on the Client 1 VM (LON-CL1).


### Task 2 – Configure Azure Information Protection

In this task you will create an AIP label and add it to the default policy so that it’s valid for all users of the Adatum tenant.

1. You should still be logged into your Client 1 VM as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In **Microsoft Edge**, open a new tab and enter the following URL in the address bar: **https://portal.azure.com/**

3. If a **Welcome to Microsoft Azure** dialog box appears asking whether you want a tour before you get started, select **Maybe later.**

4. In the **Azure portal**, if a window displays indicating **You have free Azure Advisor recommendations**, then close the window now.

5. In the **Azure portal**, select **More services.**

6. In the **All services** window, in the **Search** box at the top of the page, enter **Azure Information**, and in the right pane, select **Azure Information Protection**. 

7. In the **Azure Information Protection – Quick start** window (which may take a minute or so to load), in the middle pane under **Classifications**, select **Labels**.

8. In the **Labels** window, select **Add a new label.**

9. In the **Label** window, enter the following information:

	- Enabled: select **On**

	- Label display name: **PII**

	- Description **Documents, Files and emails with PII**

	- Color: **Black** is selected by default, so leave it as is

	- Set permissions for documents and emails containing this label: select **Protect**

		- In the Protection page that appears on the right, select **Set user-defined permissions (Preview)**. Note the options that are selected be default (leave them as is), and then select **OK**.

	- Set visual marking (such as header or footer):

		- Documents with this label have a header: **Off**

		- Documents with this label have a footer: **Off**

		- Documents with this label have a watermark: **On**

			- Watermark text: **Personal Identifiable Information (PII)**

			- Watermark font size: **Auto**

			- Watermark font name: **Custom**, and then enter **Segoe UI** in the font name field

			- Watermark color: **Custom**, and then enter **#B22222** in the color field

			- Watermark layout: **Diagonal**

10. Select **Save** in the upper left corner.

11. In the **Save settings** pop-up window that appears asking if you’re sure about saving and publishing the changes, select **OK.**

12. In the **Azure Information Protection - Labels** window, under **Classifications** in the middle pane, select **Policies**.

13. In the list of policies, select the **Global** policy to edit it.

14. In the **Policy: Global** window, below the list of labels, select **Add or remove labels**.

15. In the **Policy: Add or remove labels** pane that appears on the right, under **Label display name**, select the check box to the left of **PII** and then select **OK**. 

16. In the **Policy: Global** window, scroll down towards the bottom of the pane and in the **Users must provide justification to set a lower classification label, remove a label, or remove protection** option, select **On**.

17. Select **Save** in the menu bar at the top of the page.

18. In the **Save settings** pop-up window that appears asking if you’re sure about saving and publishing the changes, select **OK.**

19. Close the **Policy: Global** window by selecting the **X** in the upper right corner (you may have to scroll to the right to see the **X**).

20. Close the **Azure Information Protection - Policies** window by selecting the **X** in the upper right corner (you may have to scroll to the right to see the **X**).

21. This takes you back to the **All services** window. Leave this Azure portal tab open as you will use it in the next exercise when you configure Windows Information Protection. 

You have now configured a new custom AIP label named PII and added it to the default AIP policy.


### Task 3 – Assign an AIP label to a document

In this task you will use the AIP label that you created in the previous task to classify a document.

‎For this task, you will sign into Microsoft Azure Information Protection as Alex Wilber, who is a regular user without any elevated privileges.

1. You should still be logged into your Client 1 VM as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In the **Search** box on the taskbar at the bottom of the window, type **Word**. In the menu that appears, select **Word**.A 

3. After **Microsoft Word** opens, a **Microsoft Azure Information Protection Sign-in** page appears. Enter **AlexW@M365xZZZZZZ.onmicrosoft** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) and then select **Next**.  

4. On the **Enter password** window, enter the Alex's password from your lab hoster (hint: it's probably the same as MOD Admin's password) and select **Sign in**. Note, you may be prompted to passthrough multi-factor authentication as a result of an earlier lab.

5. You may be prompted to "Use this account everywhere on your device". If so click **Yes**.

5. In **Word,** select **Blank document**.

6. If the **What’s New** pane appears on the right, close it.

7. In the **Home** ribbon, locate the **Protection** group. This group appears as a result of having installed AIP at the start of this exercise.

8. In the **Word** document, type **Testing personally identifiable information (PII).**

9. The **Azure Information Protection** bar should appear by default below the ribbon, and since you created a label titled **PII** in the prior task, **PII** will appear in the middle of the AIP bar. Select **PII**.

10. In the **Microsoft Azure Information Protection** window that appears, select the following options:

	- Select permissions: **Viewer – View Only**

	- Select users, groups, or organizations: If Outlook is running, select the **address book** icon and then select **Joni Sherman** as the **To** address. If Outlook is not running, enter **JoniS@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)

	- Expire access: Select the **Calendar** icon and then select the next day

11. Select **Apply** to finish the protection process.

12. Scroll down through the document and note the watermark that was applied. This is based on the PII label that you created in the prior task that you then applied to this document.

13. Select **File** from the top menu bar.

14. Select **Save As** on the left menu.

15. Under the **Save As** pane, select **Browse**. 

16. In the **File Explorer** window, you should see the **Documents** folder by default; if not, navigate to **Documents** folder. Enter **ProtectedDocument** as the name of the file and then select **Save**.

17. In the **Word** doc, note how the **RESTRICTED ACCESS bar** displays below the ribbon at the top of the page. This is a result of the **Protect** option you set for the **Permissions** parameter in the **PII label** that you created earlier. In this bar, select **Change Permission…**

18. In the **Permissions** window that appears, note how Joni Sherman (**JoniS@M365xZZZZZZ.onmicrosoft.com**) has been assigned **Read-only** permissions, but no one has been assigned the ability to change the document. In the next task, you will test out this policy. Select **OK** to close the Permissions window. 

19. Close Word.

20. Leave the Client 1 VM and your browser open and proceed to the next task.

You have just successfully created an AIP protected Word document that expires the next day, is read-only protected, and is accessible only by its creator, Alex Wilber, and Joni Sherman (with Read-only permission).


### Task 4 – Verify AIP policy

In the prior task, you created a Word document and protected it with Azure Information Protection by inserting a watermark and restricted permissions. To verify whether the protection that you assigned to the document works, you will send the document to Joni Sherman and to your own email address (Holly Dickson's email) and then test what functionality is possible for each user in the document.

1. You should still be logged into your Client 1 VM as the **lon-cl1\admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**. 

2. If you have **Outlook on the web** open in a tab in your **Edge** browser, then select it now and proceed to the next step; otherwise, if you have a tab with the **Microsoft Office Home** page, then select the tab, select **Outlook**, and then proceed to the next step**.** If you have neither tab open, then in a new tab enter **https://outlook.office365.com** and sign in as **holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider).

3. In **Outlook on the web**, select **+New Message** in the upper left part of the screen.

4. In the right-hand pane, enter the following email information:

	- To: You will be sending an email to Joni Sherman and to your own email account (Holly Dickson's email). Enter **Joni** and then select her email address from the dropdown list. 

	- CC: Enter your own email address for Holly Dickson.

	- Add a subject: **Protected Document Test**

	- Add a message or drop a file here: **If you can open the protected and restricted document attached to this email, then try to change it.**

	- Select **Attach** from the top menu and select **Browse this computer**. In the File Explorer window that appears, the **Documents** folder should display by default. Select the **ProtectedDocument.docx** file that you created in the prior task and then select **Open.**

5. Select **Send** in the menu bar that appears above the message (or the **Send** button at the bottom of the page).

6. Switch to your Client 2 VM (LON-CL2), which should already be logged into Microsoft 365 as Joni Sherman. 

7. If you have **Outlook on the web** open in a tab in your **Edge** browser, then select it now and proceed to the next step; otherwise, if you have a tab with the **Microsoft Office Home** page, then select the tab, select **Outlook**, and then proceed to the next step. If you have neither tab open, then in a new tab enter **https://portal.office.com**, and after signing in as **JoniS@M365xZZZZZZ.onmicrosoft.com**, select **Outlook**.

8. In **Outlook on the web**, in Joni’s **Inbox**, select the email that Holly just sent her, and then select the attached **ProtectedDocument.docx** file to open it. 

9. You should receive an error message indicating that the file is protected by Information Rights Management (IRM); therefore, you must use Microsoft Word to open it. Select the **X** in the upper right-hand corner of the larger window to close it.

10. This will return you to **Outlook on the web** with the email still displayed in the right pane. In the document tile, select the drop-down arrow, and in the menu, select **Download**.

11. In the notification bar that appears at the bottom of the screen, select **Save.** 

12. Once the file has finished downloading, in the notification bar, select **Open.**

13. **Microsoft Word** should open along with a **Sign in** window (it may open behind the Outlook window, in which case select the Word icon on the taskbar to bring it forward). 

14. Because the file is RMS protected and no AIP client is installed, you need to use the native RMS features of Word ProPlus and register this installation to Joni’s account. <br/>

	‎In the **Sign in** window, enter **JoniS@M365xZZZZZZ.onmicrosoft.com** and then select **Next.** 

15. In the **Enter password** window, enter Joni's password (hint: it's probably the same as MOD admin password) and then select **Sign in.**

16. In the **Use this account everywhere on your device** window that appears, select **This app only** to register this Office 365 ProPlus installation to **Joni Sherman’s** Microsoft 365 account.

17. The file should open in Word, since you assigned Joni with Read-only permission. Review the three notification bars that appear above the document. 

18. Try to change the file. Word should not recognize any keystrokes and you can read the following text in the notification bar in the lower end of the Word window: **You can’t make this change because the selection is locked**. <br/>  

	‎**Note:** You have just verified that the permissions assigned to the file are working properly. Joni can read the file (since she was assigned Read-only permission), but she is unable to change it (no one was assigned Edit permission).

19. Close Word.

20. You will now test what happens when you attempt to open the document. Use your phone or classroom PC to access your personal email address. Open the email that you (in the role of Holly) just sent to yourself, and then attempt to open the attached file. 

21. You should receive a messaging indicating that you are not signed into Office with an account that has permission to access the document. You can optionally sign in with an account that has permission to access the file, or request access from the **AlexW@M365xZZZZZZ.onmicrosoft.com** account, or Cancel out of the operation. Select **Cancel**.  <br/>

	‎Since only Joni was assigned permission to read the document, you just verified that Azure Information Protection protected the document based on the PII policy parameters that you configured.

22. Remain signed into the Client 2 VM signed in as Joni. Do not close your browser.


# Proceed to Exercise 2
