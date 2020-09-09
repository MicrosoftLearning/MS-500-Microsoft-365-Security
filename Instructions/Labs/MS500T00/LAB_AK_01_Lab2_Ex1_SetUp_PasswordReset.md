# Module 1 - Lab 2 - Exercise 1 - Configure Self-service password reset (SSPR) for user accounts in Azure AD


### Scenario

The Help Desk has indicated that a large number of support tickets are related to password resets. You have been asked to setup a way for users to reset their password on their own. 



#### Task 1: self-service password reset

1.  Switch to **LON-CL1** and sign in as **Adatum\\Administrator** with the password **Pa55w.rd**.

2.  On the task bar select **Microsoft Edge**, open Azure by going to (https:/portal.azure.com).  Login as Holly Dickson from the previous lab. Navigate to **Azure Active Directory**
    

3.  In the navigation pane under **Manage** select **Users**, then select **Password reset**.

4.  In the **Password reset | Properties** window, select **All** to enable self-service password reset to all users. Select **Save**.

5.  On the **Password reset | Properties** blade, select **Authentication methods**.

6.  For the methods available to users, ensure that **Mobile Phone (SMS only)** and
    **Email** are selected, and then select **Security Questions**.

7.  For the **Number of questions required to register**, select **3**.

8.  For the **Number of questions required to reset**, select **3**.

9.  In the **Select security questions** section, select **No security questions configured**, then select **Predefined**. Select three questions of your choice, and then select **OK** twice.

10. Select **Save**.

11. Select **Registration** Select **No** for **Require users to register when signing in**, and the select **Save**.


#### Task 2: Test self-service password reset

1.   In Microsoft Edge at the upper right of the page, select your account name, and then select
    **Sign in with a different account**. 

2.  Sign in as **AllanD@yourtenant.onmicrosoft.com** with the password that was assigned by your lab hosting service.   

3.  Browse to **https://myapps.microsoft.com**. 

4.  On the **Microsoft** page, select on the **Allan** account in the top right corner, and then select **Profile**.

5.  On the **Profile** page, select **Edit security info**.

6.  On the **Security info** page, select **+ Add method**.

7.  On the **confirm your current password** page, if it appears, select **re-enter my password**, enter the password assigned by your lab hoster and select **Sign in**.

8.  On the **Add a method** window, select **Phone** and then select **Add**.

9.  On the **Phone** window, choose your **country or region**, type your **mobile phone number**, select the **Text me a code** radio button, and then select **Next**.

10.  Type the number that you receive in the text message in the text box below **Enter the code below.**, select **Next** and then select **Done**.

11. On the **Security info** page, select **+ Add method**. 

12. On the **Add a method** window, select **Email** and then select **Add**.

13. On the **Email** window, type your email address that you can easily access and select **Next**.

    _Note: you will need to use an e-mail address other than the tenant domain provided for this lab. If one is not available, you can skip the e-mail verification and continue with the next step._

14. Sign in to your email account, read the code, type it in the **Enter code** verification field, and then select **Next**. 
    
    _Note: If you don’t find a message with a code in your inbox, check the junk folder._

15. On the **Security info** page, select **+ Add method**.

16. On the **Add a method** window, select **Security questions** and then select **Add**.

17. On the line for **Security questions** window, select the three questions you chose in the previous steps and enter in any answers. Select **Done**.

18. On the **My Sign-ins** page, select on the **Allan** account, and then select **View my account**.

19. On the **Profile** page, select **Change password**.

20. On the **change password** page, in the **Old password** text box, type Allan's password assigned by your lab hoster, in the **Create new password** and the **Confirm new password** text boxes, type **Pa55w.rd1234** and then select **Submit**.

21. Wait until the Microsoft Azure profile portal appears, and then close the Microsoft Edge browser window.

# Continue to Exercise 2

