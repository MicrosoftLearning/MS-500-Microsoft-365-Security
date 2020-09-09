# Module 1 - Lab 1 - Exercise 2 - Manage users and groups 

In the following lab exercise, you will take on the role of Holly Dickson, Adatum Corporation’s Security Administrator. In this exercise, you will perform several user and group management functions within Microsoft 365. You will create two Office 365 groups and assign existing Microsoft 365 users as members of those groups. You will then delete one of the groups and then use PowerShell to recover the deleted group.

**Note:** The VM environment provided by your lab hosting provider comes with ten existing Microsoft 365 user accounts, as well as a number of existing on-premises user accounts. Several of these existing user accounts will be used throughout the labs in this course. This will save you from having to perform the tedious task of creating user accounts, which is typically not a task performed by Security Administrators. It will also provide you with the experience of creating a Microsoft 365 user account in case you are not familiar with the process.


### Task 2 – Create and Manage Groups  

In this task, you will begin implementing Adatum’s Microsoft 365 pilot project as Holly Dickson, Adatum’s new Security Administrator. Therefore, you will begin this task by logging out of Microsoft 365 as the MOD Administrator and you will log back in as Holly.<br/>

In this task, you will create two new groups and then manage the groups by assigning users to them. One group will be an Office 365 group and the other a Security group; this will enable you to see some of the differences in the two types of groups. After creating the groups, you will then delete one of them. This will set up the next task, which examines how to recover a deleted group using Windows PowerShell.

1. You should still be logged into your domain controller 1 VM as the **LON-DC1\admin** account, and you should be logged into Microsoft 365 as **MOD Administrator**. On the **Microsoft 365 admin center** tab, select the user icon for the **MOD Administrator** (the **MA** circle) in the upper right corner of your browser, and in the **My account** pane, select **Sign out.** <br/>
	
	**Important:** When signing out of one user account and signing in as another, you should close all your browser tabs except for your current tab. This is a best practice that helps to avoid any confusion by closing the windows associated with the prior user. Take a moment now and close all other browser tabs except for the **Sign out** tab. 
	
2. In Internet Explorer browser, navigate to **https://portal.office.com**. 

3. In the **Pick an account** window, only the admin account that you just logged out from appears. Select **Use another account**. 

4. In the **Sign in** window, enter **Holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider). Select **Next**.

5. In the **Enter password** window, enter **Pa55w.rd** and then select **Sign in**.

6. If a **Get your work done with Office 365** window appears, select the **X** to close it. 

7. In the **Office 365 home page**, select **Admin** to open the Microsoft 365 admin center (if **Admin** is covered by an **Office 365 apps** box, select **Got it!** to close the box).

8. If a survey window appears, select **Cancel**.

9. In the **Microsoft 365 admin center**, select **Groups** in the left navigation pane, and then under it, select **Groups**. 

10. In the **Groups** page, select **Add a group** that appears on the menu bar above the list of groups.  

11. In the **Choose a group type** window, select **Office 365 (recommended)** and then select **Next**. 

12. In the **Set up the basics** window, enter **Inside Sales** in the **Name** field, and then enter **Collaboration group for the Inside Sales team.** in the **Description** field. Select **Next**.

13. In the **Assign Owners** window, you will assign Allan Deyoung and Patti Fernandez as owners of this group. 
	- Enter **Allan** in the **Owners** field. In the drop-down menu that appears, select **Allan Deyoung**. 
	- Enter **Patti** in the **Owners** field. In the drop-down menu that appears, select **Patti Fernandez**. 
	- Select **Next**.

14. In the **Edit settings** window, enter **insidesales** in the **Group email address** field. Under the **Privacy** section, verify the **Public** option is selected (select it if need be), and under the **Add Microsoft Teams to your group** section, verify the **Create a team for this group** checkbox is selected (select it if need be). Select **Next**.

15. In the **Review and finish adding group** window, review the content that you entered. If everything is correct, select **Create group**; otherwise, select **Back** and fix anything that needs correction (or select **Edit** under the specific area that needs adjustment).

16. On the **New group created** window, note the comment at the top of the page that it may take 5 minutes for the new group to appear in the list of groups. </br>

	Select **Close**. This returns you to the **Groups** page. 

17. Repeat steps 10-16 to add a new group with the following information:

	- Group type: **Security**

	- Name: **IT Admins**

	- Description: **IT administrative personnel**<br/>

	**Note:** there is no owner, email address, or privacy setting for Security groups

18. If either of the two new groups do not appear in the **Groups** list, wait a minute or so and then select the **Refresh** option on the menu bar (to the right of **Add a group**). You may need to wait an additional few minutes for both groups to appear.

	**Note:** The IT admins group does not have a group email address because it's a Security group. Two additional group types are Mail-enabled Security groups and Distribution groups. We did not use either of these group types in this lab because it can take up to an hour for these two types of groups to appear in the Groups list; whereas, Office 365 groups and Security groups usually take just a matter of minutes to appear. 

19. You’re now ready to add members to the groups. In the list of **Groups**, select the **Inside Sales** group, which opens a window for the group. 

20. In the **Inside Sales** group window, select the **Members** tab.

21. Under the **Members** section, you can see the two owners (Allan and Patti), but you can also see that there are zero (0) members. Select **View all and manage members** to add members to the group. 

22. In the **Inside Sales** group window, select **+ Add members**. This displays the list of current users.

23. In the list of users, select **Diego Siciliani** and **Lynne Robbins**, and then scroll to the bottom and select **Save**. 

24. Select **Close**. This displays the list of users for this group. Select **Close** again. 

25. On the **Inside Sales** window, Diego and Lynne should now appear as members of the group. Select the **X** in the upper right corner to close the window. 

26. Repeat steps 19-25 to add **Isaiah Langer**, **Megan Bowen**, and **Nestor Wilke** as members of the **IT admins** group.

27. You now want to test the effect of deleting a group. In the list of **Groups,** select the vertical ellipsis icon (**More actions**) that appears to the right of the **Inside Sales** group. In the menu box that appears, select **Delete group**. 

28. In the **Delete Inside Sales** window, select the **Delete group** button.

29. Once the group is deleted, select **Close**. 

30. This will return you to the list of **Groups** in the **Microsoft 365 admin center**. The **Inside Sales** group should no longer appear. If the Inside Sales group still displays, wait a couple of minutes and then select the **Refresh** option on the menu bar. The updated **Groups** list should no longer include the Inside Sales group.

31. To verify whether deleting this group affected any of its owners or members, select **Users** and then **Active Users** in the left navigation pane. 

32. In the **Active users** list verify that the two owners (**Allan Deyoung** and **Patti Fernandez**) and the two members (**Diego Siciliani** and **Lynne Robbins**) of the Inside Sales group still appear in the list of users. This verifies that deleting a group does not delete the user accounts that were owners or members of the group.

33. Remain logged into the domain controller VM with the Microsoft 365 admin center open in your browser for the next task.


### Task 3 – Recover Groups using PowerShell 

In this task, you will use Windows PowerShell to recover the Inside Sales group that you previously deleted. To use Windows PowerShell to perform this Azure AD-related task, the Windows Azure Active Directory PowerShell Module must be installed. 

**NOTE:** You should have installed the Windows Azure Active Directory PowerShell Module in the prior lab.   

1. If you’re not logged into the LON-DC1 VM as **ADATUM\Administrator** and password **Pa55w.rd**, then please do so now.

2. If Windows PowerShell is still open from the previous exercise, select the **Windows PowerShell** icon on the taskbar; otherwise, you must open an elevated instance of Windows PowerShell just as you did before. Maximize your PowerShell window.

3. In **Windows PowerShell**, type the following commands (press Enter after each command):

	- You must run the following command to connect with an authenticated account to use Active Directory cmdlet requests: <br/> 
	
		‎**Connect-AzureAD**   

	- A new window will appear requesting your credentials. Sign in using Holy's Microsoft 365 account of **Holly@M365xZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) and **Pa55w.rd** as the Password.  

	- You should then run the following command to display the repository of deleted groups (this should display the **Inside Sales** group that you earlier deleted):<br/>  
	
		‎**Get-AzureADMSDeletedGroup**   

	- Before you can restore this deleted group, you must first copy the Object ID of the Inside Sales group that appears in the table of deleted groups. When you perform the next command to restore the group, you will use this ID to identify the group that you want restored. <br/>
	
		To copy the ID, select the entire ID and then press Ctrl-C.

	- You should then run the following command to retrieve and restore the deleted group whose Object ID matches the value you enter:<br/>  

		‎**Note:** Replace the {objectId} in the following command with the ID number for the Inside Sales group that you copied in the prior step. When you enter the following Restore command and you get to the point of pasting in the {objectId} parameter, press Ctrl-V to paste in the Id. Then press Enter to run the command. **NOTE:** If nothing happens when you hit Enter, then extraneous hidden characters may have been pasted in following the object ID. If this occurs, retype the command and hit the Delete key a couple of times after pressing Ctrl-V, and then press Enter again.  <br/>

		‎**Restore-AzureADMSDeletedDirectoryObject -Id {objectId}**  
		
4. Leave your Windows PowerShell window open for the next exercise; simply minimize the PowerShell window for now.

5. You should now validate that the **Inside Sales** group has been recovered. To do this, go to the **Microsoft 365 Admin Center** in your Internet Explorer browser, select **Groups** from the left-hand navigation pane, and then under it select **Groups** to display the list of groups. 

6. Verify that the **Inside Sales** group has been restored and is present in the list of groups. If the Inside Sales group does not appear, wait a minute or two and then select the **Refresh** icon to the right of the URL in Internet Explorer.

7. You now want to verify that the recovery process correctly updated the group's membership. From the **Groups** windows, select the **Inside Sales** group.

8. In the **Inside Sales** window, select the **Members** tab. **Allan Deyoung** and **Patti Fernandez** should appear as owners of the group, and **Diego Siciliani** and **Lynne Robbins** should appear as members of the group.

9. Close the **Inside Sales** window.

10. Leave your browser windows open so that they’re ready for the next task. 


# End lab

