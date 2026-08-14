# Lab 2 - Configure and Import your Webex CI User

## **Objectives**

In this lab you will:

 - Know how to create a user on Control Hub and add them to the PCCE synced Group.
 - Know how to configure your PCCE deployment for periodic/manual sync with the Control Hub
 - Know how to import users into CCE as Webex CI users.
 - Know how to configure an imported Webex CI user as an Agent on CCE.

??? question "What are the prerequisites for Webex Common Identity(CI)?"

     - Install ICM_ES202511 or later.
     - Order for Webex Common Identity is placed on Cisco Commerce Workspace (CCW).
     - Install Cloud Connect ES202511 COP or later.
     - Cloud Connect is added to Inventory and registered on Webex Control Hub.
     - Install Cisco Finesse 15.0(1) SU1 or later.
     - Webex CI endpoints is enabled in your proxy settings. See [CCE 15.0 Security Guide](https://www.cisco.com/c/en/us/support/customer-collaboration/unified-contact-center-enterprise/products-installation-and-configuration-guides-list.html){:target="_blank"}.


## **Task 1. Create users on Webex Control Hub**

**Step 1:**
On **WKSTN1**, using Chrome log into **Webex Control Hub** - [admin.webex.com](https://admin.webex.com){:target="_blank"} - using the credentials below:

 - ***Username:*** CiscoWxConnect2+tenant03@gmail.com
 - ***Password:*** CXNativeAI2025!

   ![Webex Control Hub Login](./assets/Lab2_CI_Config/L2-01.png)


**Step 2:**  <span class="read-only-badge">Read Only</span><br>
From the left-side menu, navigate to **Users** -> and click on the **Add Users** button.<br>

   ![Add Users](./assets/Lab2_CI_Config/L2-03.png)

**Step 3:**  <span class="read-only-badge">Read Only</span><br>
Enter in the **First Name**, **Last Name**, **Email Address** and then click **Next**.<br>
***Note:*** *You cannot add existing users in your organization or users that already have a Webex account.*<br>


   ![Add](./assets/Lab2_CI_Config/L2-04.png)

<br>

**Step 4:**  <span class="read-only-badge">Read Only</span><br>
Click Next in the **Assign license for users** page 

   ![Add](./assets/Lab2_CI_Config/L2-05.png)

<br>

**Step 5:**  <span class="read-only-badge">Read Only</span><br>
In the **Review** page, review the details and click the **Add Users** button.<br>
At this point the User is successfully created on Control Hub with a status of **Not Verified**.<br>

   ![Add](./assets/Lab2_CI_Config/L2-06-01.png)
   ![Add](./assets/Lab2_CI_Config/L2-06-02.png)
   ![Add](./assets/Lab2_CI_Config/L2-06-03.png)

<br>

**Step 6:**  <span class="read-only-badge">Read Only</span><br>
Verify the user using the **Activation email** sent to the email id entered and set the password.<br>
The status on Control Hub will now show **Active** for the user account added.<br>

   ![Add](./assets/Lab2_CI_Config/L2-07-01.png){ width="50%" height="50%" }
   ![Add](./assets/Lab2_CI_Config/L2-07-02.png){ width="50%" height="50%" }
   ![Add](./assets/Lab2_CI_Config/L2-07-03.png)

<br>

**Step 7:**  <span class="read-only-badge">Read Only</span><br>
Click on the created user account on Control Hub; and under the **Summary** tab, find the **Groups** section and click on **Add to Webex groups**.<br>

   ![Add](./assets/Lab2_CI_Config/L2-08.png)

<br>

**Step 8:**  <span class="read-only-badge">Read Only</span><br>
Next, select **PCCE Users** group -> **Save**.<br>

??? question "What are these Webex groups seen in the drop-down?"

    • When an Org is created in a PCCE solution, a **PCCE Users** group is created automatically by the System.<br>
    • When an Org is created in a UCCE solution, a **UCCE Users** group is created automatically by the System.<br>
    • Similarly, for a WxCCE solution, a **WxCCE Users** group is created automatically by the System.<br>

   ![Add](./assets/Lab2_CI_Config/L2-09-01.png)
   ![Add](./assets/Lab2_CI_Config/L2-09-02.png)

<br>

## **Task 2. Import Users into CCE**

**Step 1:**<br>
On WKSTN1, using Chrome log into the **CCEAdmin** page - [ccedata.dcloud.cisco.com/cceadmin](https://ccedata.dcloud.cisco.com/cceadmin){:target="_blank"} - using the credentials below.<br>

 - ***Username:*** administrator@dcloud.cisco.com<br>
 - ***Password:*** C1sco12345<br>


   ![Add](./assets/Lab2_CI_Config/L2-10.png)

<br>

**Step 2:**  <span class="read-only-badge">Read Only</span><br>
Navigate to **Features** -> **Single Sign-On** -> click on the **Webex Common Identity** tab.<br>Under the **Configuration** tab, you have option to enable auto-sync and/or perform a manual sync on demand.

 - Using the **Auto/Periodic Sync** or the **Manual Sync**, the users created on Control Hub & added to the **PCCE Users** group will be imported into CCE.

   ![Add](./assets/Lab2_CI_Config/L2-11-01.png)
   ![Add](./assets/Lab2_CI_Config/L2-11-02.png)

<br>

??? note "Webex CI Configuration Fields and their descriptions"

    **Last Sync:** Displays the timestamp of the latest sync and sync completion status.<br>
    
    
    **Sync Details:** Displays number of Webex CI users synced from Common Identity to the CCE database.<br>
    - **Created:** Number of newly synced Webex CI users.<br>
    - **Updated:** Number of existing Webex CI users whose information is updated.<br>
    - **Failed:** Number of Webex CI users that failed to sync. You can click “Failed” to see the list of failed users that are not synced to the CCE database.<br>
    
    
    **Current Sync Status:** Displays the sync status, whether the sync is in progress or scheduled.
    
    
    **Enable Sync:** Switch the toggle ON to enable Periodic / Auto sync. To disable Periodic / Auto sync, toggle this option OFF.
    
    
    **Frequency:** Displays the defined timestamp at which the Webex CI users sync must occur. 30mins is the default timestamp.<br>
    - **All day:** Select the All day radio button to sync users every day.<br>
    - **Custom:** Select the Custom radio button to sync users based on the required start and end time on the From and To fields.
    
    
    **Manual Sync:** Click ***Sync Now*** to trigger the manual sync process. This can be triggered at any point when the ***Enable Sync*** option is enabled. 
    
    
    **NOTE:** ***Sync Now*** button is available only when ***Enable Sync*** button is turned ON. Manual Sync is disabled during an active automatic sync.

<br>

**Step 3:**  <span class="read-only-badge">Read Only</span><br>
To view the list of users successfully imported, click on the **Users** tab.

   ![Add](./assets/Lab2_CI_Config/L2-12.png)

<br>

## **Task 3. Configure the imported Users as Agents in CCE**


**Step 1:**<br>
Now, navigate to **Users** -> **Agents** and click on the **New** button to add the imported user as an Agent on CCE.<br>

   ![Add](./assets/Lab2_CI_Config/L2-13.png)






**Step 2:**<br>
On the New Agent configuration page:<br>

a. Uncheck the **Set Password** option.<br>
<span style="background-color:#f7f305; color:black; padding:2px 8px; border-radius:4px; font-weight:bold;">Note: Ensure to clear out the Auto-Filled entries.</span>

b. Check the **Enable SSO** box and select **Webex Common Identity** radio button.<br>

c. Search for your Agent name - *in this case, enter your seat number - example seat00*.

 - This will then auto populate the **Username**, **First Name** and **Last Name** fields.<br>

   ![Add](./assets/Lab2_CI_Config/L2-14-01.png)
   ![Add](./assets/Lab2_CI_Config/L2-14-02.png)

<br>

d. Next, assign the agent to the **Webex_AI_Team** team.<br>

e. Set the Desk Settings as **UWFDeskSettings**.<br>

   ![Add](./assets/Lab2_CI_Config/L2-15.png)

<br>

f. Under the **Attributes** tab, add the attribute **CumulusInbound** and set the value as 5 or higher.<br>

   ![Add](./assets/Lab2_CI_Config/L2-16.png)

<br>

g. Now, click the **Contact Center AI** tab and select the following features and the click **Save**.<br>

 - Virtual Agent Transcript
 - Call transcript
 - Virtual agent transfer summaries
 - Real-time Assist
 - Wrap-up summaries 

   ![Add](./assets/Lab2_CI_Config/L2-17.png)

<br>



## **Task 4. Review Agent Desk Setting and assign Wrap-Up reason to the Agent Team**

??? question "What's the purpose of this task?"

     - Wrap-up Summary requires Wrap-up to be set to **Required** or **Required with wrap-up data**.
     - When Wrap-up is set to Required or Required with wrap-up data, at least 1 wrap-up reason must be assigned to the team.


**Step 1:**<br>
Navigate to **Desktop** -> **Desk Settings** -> Select the Desk Setting **UWFDeskSettings**

 - Ensure the parameters **Wrap-up on Incoming** and **Wrap-up on Outgoing** are both set to **Required**.

   ![Add](./assets/Lab2_CI_Config/L2-17-01.png)
   ![Add](./assets/Lab2_CI_Config/L2-17-02.png)   

<br>

**Step 2:**<br>
Lastly, navigate to **Organization** -> **Teams** -> Select the team **Webex_AI_Team**.<br>

   ![Add](./assets/Lab2_CI_Config/L2-18.png)
   ![Add](./assets/Lab2_CI_Config/L2-19.png)

<br>


**Step 3:**<br>
Select the **Team Resources** tab -> **Wrap-up Reasons** -> add at least one **Wrap-Up Reason** -> and click **Save**.

   ![Add](./assets/Lab2_CI_Config/L2-20.png)

<br>



<p align="center"><strong>This now completes Lab 2!</strong></p>

