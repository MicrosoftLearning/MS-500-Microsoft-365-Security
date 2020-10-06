# Module 8 - Lab 1 - Exercise 3 - Creating compliance and conditional access policies 

### Scenario

A. Datum would like to ensure that enrolled Windows 10 devices meet a minimum configuration specification.  The following are required:

* Minimum OS version: 10.0.17763.615
* Windows Defender Antimalware required
* iOS and MacOS platforms blocked

If the device does not meet these requirement, the device should be marked as non-compliant.

#### Task 1: Create and apply compliance policy and enrollment restrictions

1.  Sign in to **LON-CL1** as **ADATUM\\Administrator** with the password **Pa55w.rd**. 

2.  In Microsoft Edge, type **https://endpoint.microsoft.com** in the  address bar, and then press **Enter**. Sign in as as **admin\@yourtenant.onmicrosoft.com** with the default tenant password.

3.  From the navigation pane select **Devices**, then select **Compliance Policies**.

4.  On the **Compliance policies | Policies** blade, in the details pane select **Create Policy**.

5.  On the **Create a policy** blade, provide the following values and select **Create**:

    -  Platform: **Windows 10 and later**

6.  On the Basics tab, provide the following values and select **Next**:

    -  Name: **Compliance1**

7.  On the **Compliance settings** tab, select **Device Health** and review the available settings.

8.  On the **Compliance settings** tab, expand **Device Properties**. In the **Minimum OS version** field, type **10.0.16299.15**.

9.  On the **Compliance settings** tab, expand **System Security**. Set the 
    **Windows Defender Antimalware** setting to **Require**. 

10. Select **Next**. On the **Actions for noncompliance** tab, note the action to Mark device noncompliant default setting is immediately. Review how you can configure the number of days after which the device is marked as noncompliant, and configuration additional actions. 

11. Select **Next**. On the **Assignments** tab, choose **Select groups to include**.  Select **Enrolled Devices**, choose **Select**, and then select **Next**.

12. Select **Create**.

13. From the left menu select **Devices**, then select **Enroll devices**.

14. On the **Enrollment devices | Windows enrollment** blade, select **Enrollment restrictions**.

15. On the details pane, in the **Device Type Restrictions** section, on the **Default** line, select **All Users**.
    
16. On the **All Users** blade, select **Properties**. In the **Platform settings** section, select **Edit**.

17. On the **Platforms settings** tab, in the **Platform** column, on the rows with **iOS/iPadOS** and **macOS**, select **Block**. Select **Review + save** and then select **Save**.

18. Scroll left to the **Enroll devices | Enrollment restrictions** blade. In the **Device Limit Restrictions** section, select **All Users** and then select **Properties**.

19. In the **Device limit** section, select **Edit**, then change the value to **3**.  

20. Select **Review + Save**, and then select **Save**.


## Task 2: Creating a conditional access policy

### Scenario 

When devices are non-compliant, they should not be able to access their e-mail. You've been asked to configure a conditional access policy that enforces this rule, and verify it functions as expected.


1.  On **LON-CL1**, in the **Microsoft Endpoint Manager admin center** select **Devices**, then select **Conditional Access**.

2.  In the **Details** pane, select **New policy**.

3.  On the **New** blade, in the **Name** text box, type **Conditional1** and then select **Users and groups**.

4.  On the **Users and groups** blade, select the **All users** radio button.

5.  On the **New** blade, select **Cloud apps or actions**, select the **Select apps** radio button, select **Select**, select **Office 365 Exchange Online**, and then select **Select**

6.  On the **New** blade, select **Conditions**, select **Device platforms**, in the **Configure** section select **Yes**, select the **Select device platforms** radio button, select the **Windows** check box, and then select **Done**.

7.  On the **New** blade under **Access controls**, select **Grant**, select the **Require device to be marked as compliant** check box, and then select **Select**.

8.  On the **New** blade, select **On** for the **Enable policy** option and then select **Create**.

#### Task 3: Verify that the conditional access policy is working

1.  On **LON-CL2**, open a new Microsoft Edge tab, then and open <https://portal.office.com>.

2.  Select the **Outlook** icon. 

3.  Verify that you receive the message **"You can't get there from here"** or similar warning message.

4.  Select **More details**. You should see more information about why you are blocked. **Note:** This is because LON-CL1 is not joined to Azure AD and not managed by Intune, so not marked as compliant.

5.  **Close** the browser window.

6.  Return to **LON-CL1** and open EndPoint Manager. In Microsoft Edge, type **https://endpoint.microsoft.com** in the  address bar, and then press **Enter**. Sign in as as **admin\@yourtenant.onmicrosoft.com** with the default tenant password.

7.  Select **Devices** and then select **Conditional access**. Select the elipses next to policy "Conditional1" and click **Delete**.  Select **Yes** to confirm deletion.  Note: If you don't delete this policy it will interfere with later labs.



**END OF LAB**
