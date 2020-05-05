# Module 2 - Lab 3 - Exercise 1 - Setting up your organization for identity synchronization 

You are Holly Dickson the security administrator for Adatum Corporation, and you have Microsoft 365 deployed in a virtualized lab environment. In this lab, you will implement identity synchronization between your Microsoft 365 tenant accounts and your local active directory accounts.

### Task 1 - Configure your UPN suffix

1.	On LON-DC1, log on as **adatum\Administrator** and password assigned from your lab hoster.
2.	Using Windows PowerShell as administrator, update the UPN suffix for the domain and on the UPN on every user in AD DS with “@zzzzzzz.onmicrosoft.com” (where zzzzzzz is your unique UPN name) for the domain name. To do this, run the following command (remember to change zzzzzzz to your unique UPN name):

    	Set-ADForest -identity "adatum.com" -UPNSuffixes @{replace="zzzzzzz.onmicrosoft.com"}  
3.	Next type the follow command (remember to change zzzzzzz to your unique UPN name): 

		Get-ADUser –Filter * -Properties SamAccountName | ForEach-Object { Set-ADUser $_ -UserPrincipalName ($_.SamAccountName + "@zzzzzzz.onmicrosoft.com" )}
4.	At the Windows PowerShell prompt, type the following command, and then press Enter:

		Set-ExecutionPolicy Unrestricted  
5.	To confirm the execution policy change, enter **A** for Yes to All press Enter key.
 
### Task 2 - Enable Directory Synchronization

1.	Open your browser and go to https://portal.office.com/   
2.	Sign in as **holly@<your tenant here>.onmicrosoft.com** with the password **Pa55w.rd** .    
3.	Click **Admin** to go to the Microsoft 365 admin center.
4.	If asked about **update your admin contact information **click the Cancel button to skip this request.  
	**Note:** If you see the Active Directory synchronization is being activated warning, you can ignore it at this time, but you will not be able to run directory synchronization later in this exercise. You must wait until directory synchronization is activated. However, you can complete the following steps, even if you do see the warning message.  
5.	In the left navigation, select **users** icon and select **Active users**, click on the ellipses at the top menu and choose **Directory Synchronization**.   
6.	Click on the **Go to the Download center to get the Azure AD Connect tool**.   Download and Run the download once prompted.
    
### Task 3 - Run Azure AD Connect

1.	On the Azure AD Connect setup wizard, proceed through the wizard. 
2.	Agree to the license terms and privacy notice.
3.	Click on **Use express settings**.   
4.	On the **Connect to Azure AD** screen enter your Office 365 admin username of 
**Holly@<your tenant here>.onmicrosoft.com** with password **Pa55w.rd** and click Next.   
5.	On the **Connect to AD DS** screen enter your domain administrator **ADATUM\Administrator** and password **Pa55w.rd** and click **Next**.   
6.	Select **Continue without matching all UPN suffixes to verified domains** checkbox. Click **Next** on the Azure AD sign-in configuration screen.   
7.	On the **Ready to configure** screen mark the check box for **Start the synchronization process when configuration completes** and click **Install**.   
8.	Wait for the installation to complete (this may take several minutes).   
9.	Select **Exit**.   

### Task 4 - Validate the results of directory synchronization and license a user. 

1.	To verify the new user you created open the Office 365 Admin Center in the browser by typing **https://portal.office.com** in the address bar.  
2.	Sign in as Holly Dickson with the following credentials:  User name: **holly@<your tenant here>.onmicrosoft.com**, Password: **Pa55w.rd**  
3.	Navigate to the **Active Users**.  
4.	You should now see many users that have become synced from the local Active Directory.  Select Abbie Parsons.  Abbie is a user that was only in the AD DS domain prior to our synchronization. 
5.	Edit Abbie Parsons Product licenses as follows: 
	- Location = United Kingdom
	- Product License = Enterprise Mobility + Security E5
6.	Click **Save changes** to make the changes. Close the window.

You have successfully synced local ADATUM users into Office 365 and licensed the synced user Abbie Parsons.

# End of lab  

 