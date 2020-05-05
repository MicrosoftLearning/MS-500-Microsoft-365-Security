# Module 6 - Lab 7 - Exercise 1 - Conduct a Spear phishing attack


Holly Dickson is concerned that some users in her organization may require education about phishing attacks.  In this lab you will use the Microsoft 365 Attack simulator to determine your users' susceptibility to phishing attacks.


### Task 1: Enable Mulit-factor authentication for Holly Dickson


1.  Go to the Office 365 Security & Compliance center (https://protection.office.com) and login as Holly Dickson.

2.  Click **Threat management**, and then click **Attack simulator**.

3.  Notice the warning that you must enable multi-factor authentication (MFA).  You are about to do a simulated attack and the system wants to confirm your credentials. This is a requirement of the attack simulator. Let's enable MFA for Holly Dickson. Go to your browser tab with the Microsoft 365 admin center or open a new browser tab to https://admin.microsoft.com.

	**Note:** You may not get this warning if you enabled MFA for Holly in an earlier lab and are using the same tenant.  If this is the case you may skip ahead to the next task.

4.  On the left select **Users** and then select **Active users**.

5.  On the Active users screen click **Multi-factor authentication**.

7.  In the multi-factor authentication screen mark Holly Dickson and select **Enable** under quick steps.

8.  In the About enabling multi-factor auth screen select **enable multi-factor auth**.

9.  In the Updates successful screen click **Close**.

10.  Close the browser session.  Open a new browser and open the Office 365 Security & Compliance portal and login again as Holly Dickson.  Now you should be asked for multi-factor credentials as part of the login process.

	**Note:** it may take several minutes for this MFA setting to propagate your tenant.  If the **Launch Attack** button is not available in Attack Simulator then wait a few minutes and login again as Holly Dickson. If you are not able to satisfy the MFA requirements with your own mobile device you will not be able to complete this lab.

### Task 2: Configure and launch a Spear Phishing attack
3.  In the Spear Phishing (Credentials Harvest) area select the **Launch Attack** button.

4.  Name the campaign *Spear Simulation* and select **Next**.

5.  In the Target recipients area select the **Address Book** button and select **Patti Fernandez** and then then select  **Next**.

6.  In the Configure email details area enter a creative name in the **From (Name), From (Email)**, and select any Phishing Login Server URL from the drop-down menu.

      **Note**: Ordinarily you would also include a URL link for the target to click into.  This would be entered in the Custom Landing Page URL field.  Since this is just an exercise we won't do that here.  The success rate of the spear phishing attack will be a function of how clever an email you contrive. 

7.  In the **Subject** field for the phishing email type Free Gift Cards and select **Next**.

8.  In the Compose email area enter a creative enticing email message intended to lure users and select **Next**.

9.  In the Confirm area select **Finish**.


### Task 3: Confirm target received phishing email attack

2.  Open a new browser window in InPrivate or incognito mode and browse to **`https://office.com**.
 
3.  Log in as the user Patti Fernandez **PattF@M365xZZZZZZ.onmicrosoft.com** where ZZZZZZ is your specific Office 365 tenant.

4.  Click the Outlook icon to open Microsoft Outlook for Patti. You should see a spear phishing email that includes the details you just entered in the previous task.

### Task 4: Review the results

3. In your browser session where you are logged in as Holly Dickson go back to the Attack simulator.

4. In the Spear Phishing (Credentials Harvest) area click **View Report**.

5. The report lists the current results of the spear phishing campaign including number of users targeted and success rate.  
    
		**Note**: Since you can run multiple spear phishing simulation campaigns simultaneously you could create different simulations for different users and groups.
 

# Continue to exercise 2.
