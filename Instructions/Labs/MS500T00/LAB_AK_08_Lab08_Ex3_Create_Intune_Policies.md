# Module 8 - Lab 8 - Exercise 3 - Create Intune Policies 

Many mobile device management (MDM) solutions help protect organizational data by requiring users and devices to meet some requirements. In Intune, these requirements are referred to as compliance policies. Compliance policies define the rules and settings that users and devices must meet to be compliant. When combined with Conditional Access, administrators can block users and devices that don't meet the rules.

### Task 1: Create and apply compliance policy

In this task you will create a compliance policy that governs Windows 10 devices at Adatum Corporation. This policy will dictate what the minimum requirements are for accessing Adatum&#39;s environment. It will also control how long a device can stay out of compliance before it&#39;s locked out from use; thereby, requiring administrator assistance to make it operational again. The policy will also control who it&#39;s assigned to, which in this case will be all devices enrolled in Microsoft Intune.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, in the **Azure** portal, select **All services** from the left navigation pane, type **Intune** in the search field, and then select **Intune** in the detail pane on the right.

3. On the **Microsoft Intune – Overview** window, in the middle pane under the **Manage** section, select **Device compliance**.

4. On the **Device compliance** window, in the middle pane under the **Manage** section, select **Policies**.

5. On the **Device compliance – Policies** window, in the details pane on the right, select **+Create Policy**.

6. On the **Create Policy** window, enter the following information:

    - Name: **Compliance1**
    - Platform: **Windows 10 and later**

7. On the **Windows 10 compliance policy** pane that appears on the right, select **Device Health**, review the available settings, and then select the X in the upper right corner to close the pane.

8. On the **Windows 10 compliance policy** pane, select **Device Properties**.

9. On the **Device Properties** pane, in the **Minimum OS version** field, enter **10.0.16299.15** and then select **OK**.

10. On the **Windows 10 compliance policy** pane, review the other available options and then select **OK**.

11. On the **Create Policy** pane, select the **Actions for noncompliance** section.

12. In the **Actions** pane, in the list of actions, note that there is already a **Mark device noncompliant** action assigned to this policy by default, and the action is scheduled for immediate implementation. Let&#39;s review the parameters for this action so that you can see why **Schedule** is set to **Immediately**. Select the **Mark device noncompliant** action.

13. In the **Action parameters** pane, the **Schedule (days after noncompliance)** field is set to **0** by default. Setting this field 0 days after noncompliance is what triggers the **Schedule** to display **Immediately** for this action. Select **OK** to return to the **Actions** pane.

14. In the **Actions** pane, select **OK** to return to the **Create Policy** pane.

15. In the **Create Policy** pane, select **Create**.

16. On the **Compliance1** window, in the middle pane under the **Manage** section, select **Assignments**.

17. In the **Compliance1 – Assignments** window, in the details pane on the right, select **Select groups to include.**

18. In the **Select groups to include** pane, select the **Enrolled Devices** group that you created in the prior task and then select **Select** at the bottom of the pane.

19. In the **Compliance1 – Assignments** window, select **Save**.

20. In the **Azure portal**, in the left navigation pane, select **Azure Active Directory.**

21. In the **Adatum Corporation – Overview** window, in the middle section under **Manage**, select **Mobility (MDM and MAM).**

22. In the **Adatum – Mobility (MDM and MAM)** window, in the pane on the right, select **Microsoft Intune.**

23. In the **Configure** window, in the **MAM User scope** row, select **All**.

24. Select **Save** in the menu bar at the top of the window, and then select the **X** to close the **Configure** window.

25. Leave the Azure portal open for later tasks.


### Task 2: Manually create an EFS DRA Certificate

EFS is the Encrypted File System that is built into Windows. It allows anyone to encrypt a file. The encryption is done using digital **certificates**, and as part of that process, Windows assigns something called a Data Recovery Agent (DRA). In most cases a DRA will be the Administrator.

In this task, you're going to run a command prompt in which you enter the cipher command with a /R parameter. By default, /R creates a 2048 bit RSA recovery key and certificate and writes them both to a .PFX file, and it writes the certificate to a .CER file. An administrator can then add the contents of the .CER file to the EFS recovery policy to create the recovery key for users and import the .PFX file to recover individual files.

The purpose of this task is to create this RSA recovery key so that if the device on which they reside becomes compromised, you can recover the files with this certificate from Intune.

1. In your Client 1 VM (LON-CL1), in the Search field on the taskbar at the bottom of the screen, enter **cmd,** and in the menu that appears, select **Command Prompt**.

2. In the **Command Prompt** window, you are going to enter a **cipher** command, which displays or alters the encryption of file directories on NTFS partitions. The /R parameter generate an EFS recovery key and certificate and writes them to a .pfx file, which, for the purpose of this lab, you&#39;re going to name **DRAcert** (in the real-world, you can name it anything).

    Enter the following command and press Enter:
  
   **cipher /R:DRAcert**

3. You will be prompted to type in a password to protect your .PFX file. Enter **Pa55w.rd** and press Enter.

    **Note:** The cursor will NOT move when you type in the password, so you will not see what you&#39;re typing. You should also write down the password for future use; you will need this in a later task when you try to recover an encrypted file.

4. You will be prompted to type in the password again to confirm it. Press Enter when done.

5. You should receive messages indicating that your .CER and .PFX files were created successfully.

6. Close the Command Prompt window.


### Task 3: Create an App Protection Policy

You're now going to create an app protection policy that will protect selected applications from intrusion; that is, the apps will be protected so that they can only be accessed by individuals who are authorized to do so, such as employees from your company and other users from your Microsoft 365 tenant.

In this lab, you will be creating a WIP policy that protects an entire collection of recommended apps, as well as an app from the Microsoft Store, which in this case is **Microsoft Power BI**. Since this app produces reports and queries of company trends that may be confidential, Adatum wants to restrict access to it to selected individuals.

1. In the **Microsoft Azure** portal, in the left navigation pane, select **All services**.

2. On the **All services** window, enter **Intune** in the **Search** box, and then in the details pane on the right, select **Intune**.

3. In the **Microsoft Intune – Overview** window, in the middle pane under the **Manage** group, select **Client apps**.

4. In the **Client apps** window, in the middle pane under the **Manage** group, select **App protection policies.**

5. In the **Client apps – App protection policies** window, in the right pane, select **+Create Policy.** select the Windows 10 platform.

6. In the **Create policy** window, enter the following information:

    - Name: **Win10Policy**
    - Description: **Windows Information Protection Policy for Windows 10 computers**
    - Enrollment state. **With Enrollment**

7. Select **Next** Select the **Protected apps** group.

8. In the **Protected apps** area, select **+ Add.** You're first going to add all the recommended apps.

9. In the **Add apps** window, select the check box to the left of the **NAME** column heading to select all app, select **OK.**

10. In the **Protected apps** area, select **Add apps.** In the remaining steps, you&#39;re going to add a Store app, which in this case is **Microsoft Power BI**.
11. In the **Add apps** window, the drop-down field at the top of the page displays **Recommended apps**. Select this field, and in the drop-down menu, select **Store apps**.
12. In the **Add apps** window, enter the following information:

    - Name: **Microsoft Power BI**
    - Publisher: **CN=Microsoft Corporation, o=Microsoft Corporation, L=Redmond, S=Washington, C=US**
    - Product Name: **Microsoft.microsoftpowerBIforWindows**

13. Select **OK.**

14. On the **Create policy** window, Targeted apps area select **Next**

15. On the **Create policy** window, Required settings area select **Next**

16. On the **Create policy** window, Advanced settings area select **Next**

17. On the **Create policy** window, Assignments area select **Next**

15. On the **Create policy** window, Review + create tab select **Create.**

You have just created a new App Protection Policy (APP), also called a Windows Information Protection Policy (WIP).


### Task 4: Add the EFS DRA Certificate to your WIP Policy

You now want to use Microsoft Intune to add your EFS DRA certificate to the WIP policy you created in the prior task (Win10Policy). This will make the certificate available for use in unencrypting protected files.

1. In the **Microsoft Azure portal**, in the navigation thread at the top of the, select **Microsoft Intune**.

2. On the **Microsoft Intune – Overview** window, in the middle pane under the **Manage** section, select **Client apps**.

3. In the **Client apps** window, in the middle pane under the **Manage** section, select **App protection policies**.

4. In the **Client apps – App protection policies** window, in the detail pane on the right, select **Win10Policy**.

5. In the **Intune App Protection** window for **Win10Policy**, in the middle pane under the **Manage** section, select **Properties**.

6. In the **Intune App Protection – Properties** window under Advanced settings select **Edit**, in the detail pane, under the **Data protection** section, select the field under **Upload a Data Recovery Agent (DRA) certificate to allow recovery of encrypted data**.

7. In the **File Explorer** window that appears, expand **Local Disk (C:)**, expand **Users**, and then select the **Administrator.ADATUM** Scroll down through the files in the Admin folder, select **DRAcert.CER**, and then select **Open**.

    **Note:** DRAcert.CER should now appear in the certificate field in the Data protection section.

8. Select **Review + Save**.  In the Edit Policy windows select **Save**.

The DRAcert certificate has been uploaded to the App Protection policy titled Win10Policy. This certificate is now available for use in unencrypting protected files.

**Important:** At this point in a real-world scenario, to maintain device integrity, you should copy your data recovery certificate to an offline location on a thumb drive or stored in a program for keys and passwords. You should also create a backup of this file and store it at another location. The certification is how you recover files using Intune. If the certificate is not saved, then you cannot recover the file using Windows Information Protection if the device ever becomes compromised. For the purpose of this lab, you will not be storing this certificate to an offline device.


### Task 5: Create a packaged App rule for the store apps

Packaged apps, also known as Universal Windows apps, are based on an app model that ensures that all the files within an app package share the same identity. Therefore, it is possible to control the entire app using a single AppLocker rule as opposed to the non-packaged apps where each file within the app could have a unique identity. An AppLocker rule for a packaged app controls both the installation as well as the running of the app.

1. In your Client 1 VM (LON-CL1), in the Search field on the taskbar at the bottom of the screen, enter **SecPol** and in the menu that appears, select **Local Security Policy**.

2. In the **Local Security Policy** window, in the left pane, expand **Application Control Policies**, expand **Applocker**, select **Packaged App Rules**, right-click on **Packaged App Rules**, and in the menu that appears, select **Create New Rule.**

3. The **Create Packaged app Rules** wizard appears.

4. On the **Before You Begin** page, select **Next.**

5. On the **Permissions** page, make sure the **Action** is set to **Allow** and the **User or group** is set to **Everyone**, and then select **Next**.

6. On the **Publisher** page, under the **Use an installed packaged app as a reference** option, select **Select**.

    **Note:** It may take 20 seconds or more for the **Select applications** window to appear.

7. In the **Select applications** window, pick the app that you want to use as the reference for your rule. For this lab, select the check box to the left of **OneNote**, and then select **OK**.

8. On the **Publisher** page, select **Create**.

9. If a dialog box that appears asking if you want to create the default rules, select **No**. You must not create default rules for your WIP policy.

10. In the **Local Security Policy** window, in the left pane, right-click on **AppLocker** and select **Export policy.**

11. In the **Export policy** File Explorer window, you will export and save your new policy as an XML Select the **Documents** folder, enter **apprule1** in the **File name** field, verify the **Save as type** field displays **XML (\*.xml)**, and then select **Save**.

12. An **AppLocker** dialog box appears displaying a message that **1 rules were exported from the policy**, select **OK.**

13. In the **Local Security Policy** window, under **AppLocker**, select **Executable Rules**, and then right-click on **Executable Rules** and select **Create New Rule.**

14. On the **Before You Begin** page, select **Next.**

15. On the **Permissions** page, make sure the Action is set to **Allow** and the **User or group** is set to **Everyone**, and then select **Next.**

16. On the **Conditions** page, select the **Path** option and then select **Next**.

17. On the **Path** page, select **Browse Folders....**.

18. In the **Browse for Folder** window, scroll down and under **Local Disk (C:)**, select **Program Files**, and then select **OK**. Select **Next**.

19. On the **Exceptions** page, you are not adding any exceptions, so select **Next**.

20. On the **Name and Description** page, select the **Name** field and enter **exerule1** and then select **Create**.

21. If a dialog box that appears asking if you want to create the default rules, select **No**.

22. In the **Local Security Policy** window, in the left pane,right-click on **AppLocker** and select **Export policy.**

23. In the **Export policy** File Explorer window, you will export and save your new policy as an XML Select the **Documents** folder, enter **exerule1** in the **File name** field, verify the **Save as type** field displays **XML (\*.xml)**, and then select **Save**.

24. An **AppLocker** dialog box appears displaying a message that **2 rules were exported from the policy**, select **OK.**

25. Close the Local Security Policy window.

26. After you've created your XML files, you need to import them by using **Microsoft Intune**, which you will do in a later task.

### Task 6: Import a list of protected apps using Microsoft Intune

The purpose of this task is to show you how to use Intune to push an app to a device just like a group policy object. In this task, you will use Notepad. In a previous task, Notepad was included as one of the recommended apps in the App protection policy that you created. In this task you will import the App protection policy (**apprule1.xml**) into Intune that you exported in the prior task.

1. In your Client 1 VM (LON-CL1), select your **Edge** browser, which should display the **Microsoft Azure** portal and the **Client apps – App protection policies** window under the Intune blade.

2. In the right pane, select **Win10Policy**.

3. In the **Intune App Protection** window for **Win10Policy**, in the middle pane under **Manage**, select **Properties**.

4. In the right pane, in the Targeted apps area select **Edit** scroll down and select **Import** under protected apps.

5. In the **Import apps** window, select the folder icon that appears to the right of the **Select a file** field.

6. In the **File Explorer** window that appears, select the **Documents** folder, select the **apprule1.xml** file, select **Open**, and then select **OK**.

    **Note:** This imports the file and the apps are added to your **Protected apps** list in the right pane.
    
7. You now want to create a file that you're going to encrypt using Windows Information Protection. In the search field on your taskbar, type **Notepad** , and then in the menu, select **Notepad**.

8. In the **Notepad** window, enter some text and then select **File**, select **Save as,** select the **Documents** folder, enter **apptest1** as the **File name**, and then select **Save.**

9. Close Notepad.

10. In the search field on your taskbar, enter **cmd** , and then in the menu, right-click on **Command Prompt** and select **Run as administrator**.

11. In the Command Prompt window, at the prompt, enter the following command to encrypt the apptest1.txt file (the /e parameter directs the cipher command to encrypt the file):cipher

    **cipher /e   C:\Users\Administrator.ADATUM\Documents\apptest1.txt**

12. Leave the Command Prompt window open for the next task.


### Task 7: Recover your data using the EFS DRA certificate in a test environment

The purpose of this task is to show you how to recover a file that has been encrypted using WIP if the Windows 10 device on which it resides has been recovered after having been misplaced or stolen. In this case, you will decrypt the apptest1.txt file that you earlier encrypted.

1. In a real-world scenario, you would start out by copying your WIP-encrypted file (in this case, **apptest1.txt**) to a location where you have admin access. In this lab, we're simply going to point to the apptest1.txt file, so proceed to the next step.

2. You must then install the **DRAcert.PFX** file. To do so, select the **File Explorer** icon on the taskbar at the bottom of the screen. Maximize the **File Explorer** window.

3. In **File Explorer**, expand **Local Disk (C:)**, expand **Users**, and select **Administrator.ADATUM**.

4. In the list of files in the **Admin** folder, double-click on the **DRAcert.PFX** file. This initiates the **Certificate Import Wizard**.

5. On the **Welcome to the Certificate Import Wizard** page, keep the selection **Current User** and select **Next**.

6. On the **File to import** page, select **Next.**

7. On the **Private key protection** page, in the **Password** field, enter the password that you assigned to the DRAcert file that you created in Task 2 (you were instructed to write this down for future use). For this lab, enter **Pa55w.rd**, which was the password that you assigned to the DRAcert file, and then select **Next**.

8. On the **Certificate store** page, select **Next.**

9. On the **Completing the Certificate Import Wizard** page, select **Finish.**

10. On the **Import was successful** dialog box, select **OK**.

11. You should still have a **Command Prompt** window open from the previous task. Select the **Command Prompt** icon on the taskbar to display the window. If you closed the Command Prompt window at the end of the prior task, then open a command prompt with elevated rights.

12. In the Command Prompt window, run the following command to decrypt the apptest1.txt file (the /d parameter directs the cipher command to decrypt the file):

    **cipher /d  C:\Users\Administrator.ADATUM\Documents\apptest1.txt**

13.	Close the Command Prompt and Windows Explorer windows and leave the browser, with the Azure Portal website, open.


### Task 8: Configure enrollment restrictions

1. In your Client 1 VM (LON-CL1), select your **Edge** browser, which should display the **Microsoft Azure** portal.

2. Select **Microsoft Intune** from the navigation thread at the top of the page.

3. In the **Microsoft Intune – Overview** window, in the middle pane under the **Manage** section, select **Device enrollment.**

4. In the **Device enrollment** window, review the available options. In the middle pane under the **Manage** section, select **Enrollment restrictions**.

5. In the **Device enrollment – Enrollment restrictions** window, in the details pane on the right, in the **Device type restrictions** section, select **Default** and click **All users**.

6. In the **All Users** window, in the middle pane under the **Manage** section, select **Properties.**

7. In the detail pane on the right, select **Edit** that appears next to **Platform settings**.

8. In the **Edit restriction** window, select **Block** below **PLATFORM** for the **iOS/PadOS** and **macOS** rows, select **Review + save** and then review your changes. Both platform settings should display Blocked under the **PLATFORM** column. Select **Save.**

9. In the navigation thread at the top of the page, select **Device enrollment – Enrollment restrictions**. 

10. In the **Device enrollment – Enrollment restrictions** window, in the details pane on the right, in the **Device limit restrictions** section, select **Default** and select **All Users**.

11. In the **All Users** window, in the middle pane under the **Manage** section, select **Properties.**

12. In the detail pane on the right, select **Edit** that appears next to **Device limit**.

13. In the **Edit restriction** window, select the **Device limit** field, in the drop-down menu select **3**, and then select **Review + save.** Review your change and then select **Save.**


# End of Lab
