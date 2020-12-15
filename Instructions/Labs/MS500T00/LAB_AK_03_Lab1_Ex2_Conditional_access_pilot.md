# Module 3 - Lab 1 - Exercise 2 -  MFA Conditional Access (Complete an Azure Multi-Factor Authentication pilot roll out)


In this exercise you will configure a conditional access policy enabling Azure Multi-Factor Authentication (Azure MFA) when logging in to the Azure portal. The policy is deployed to and tested on a specific group of pilot users. Deployment of Azure MFA using conditional access provides significant flexibility for organizations and administrators compared to the traditional enforced method.

- Enable Azure Multi-Factor Authentication
- Test Azure Multi-Factor Authentication


### Task 1: Enable Azure Multi-Factor Authentication

1.  Return to the the Azure portal that is logged in as your Global Admin Holly Dickson.

1.  On the Hub go to **Azure Active Directory**,

1.  Click **Groups** and click **+ New group**.

     ![Screenshot](../Media/cb9c5324-cbb6-476e-9c7d-1920de301d40.png)

1.  Enter the following information then select **Create**:

      * Group type; **Security**
      * Group Name: **MFA Pilot**
      * Group description: **MFA Pilot Group**
      * Membership type: **Assigned**
      * Owners: Select **Holly Dickson**
      * Members: Select **Lynne Robbins**
  
  
      ![Screenshot](../Media/5457b62d-dc78-4043-bd72-3d7901bbcd71.png)
  
2.  Browse to **Azure Active Directory**, click **Security** and select **Conditional access** under the **Protect** section.


3.  Select **+ New policy**


4.  Name your policy **MFA Pilot**
5.  Click **users and groups**, select the **Select users and groups** radio button.  Check the box for **Users and groups** and click **Select**.
    * Select your pilot group **MFA Pilot**
    * Click **Select**

6.  Click **Cloud apps or actions**, select the **Select apps** radio button.
    * Click **Select**. The cloud app for the Azure portal is **Microsoft Azure Management** select it.
    * Click **Select**

7.  Skip the **Conditions** section
8.  Click **Grant**, make sure the **Grant access** radio button is selected
    * Check the box for **Require multi-factor authentication**
    * Click **Select**

9.  Skip the **Session** section
10. Set the **Enable policy** toggle to **On**
11. Click **Create**

### Task 2: Test Azure Multi-Factor Authentication


To prove that your conditional access policy works, you test logging in to a resource that should not require MFA and then to the Azure portal that requires MFA.


2.  Open a new browser window in InPrivate or incognito mode and browse to **`https://portal.azure.com`**

       * Log in with the Lynne Robbins user (Lynne's username is LynneR and the password is likely the same as the MOD Administrator password provided by your lab hoster) and note that you should now be required to register for and use Azure Multi-Factor Authentication.
       * Close the browser window.



# End of lab
