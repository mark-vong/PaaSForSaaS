# Lab 400: Securing Oracle ERP with Identity Cloud Service & Cloud Access Security Broker (INTERNAL ONLY)

<!-- Comment out table of contents
## Table of Contents
[Introduction](#introduction)
-->

## Introduction

This lab walks you through registering a Fusion apps demo environment. From there you will be able to start integrating the demo with Identity Cloud Service (IDCS) and Cloud Access Security Broker (CASB). 
*In addition to the workshop*, feel free to watch the walk-through companion video by clicking on the following link:
[Lab 400 Walkthrough Video](<INSERT LINK HERE>)



### Objectives
-   Learn how to request a demo instance of ERP Cloud
-   Understand the capabilities of Oracle's Identity Cloud Service and Cloud Access Security Broker and how they provide an extra layer of security for ERP Cloud.

### Required Artifacts
-   ERP Cloud Instance from [demo.oracle](https://demo.oracle.com/)
-   IDCS Instance
-   CASB Instance
-   The estimated time to complete this lab is 60 minutes.

### Extra Resources
-   To learn more about Identity Cloud Service (IDCS), feel free to explore the capabilities by clicking on this link: [IDCS Documentation](https://docs.oracle.com/en/cloud/paas/identity-cloud/)
-   To learn more about Cloud Access Security Broker (CASB), feel free to explore the capabilities by clicking on this link: [CASB Documentation](https://docs.oracle.com/en/cloud/paas/casb-cloud/)
-   To learn more about , Oracle ERP Cloud feel free to explore the capabilities by clicking on this link: [ERP Cloud](https://go.oracle.com/LP=85331?elqCampaignId=48423&src1=ad:pas:go:dg:erp&src2=wwmk160606p00030c0001&SC=sckw=WWMK160606P00030C0001&mkwid=%7cpmt%7ce%7cpdv%7cc%7c&GOOGLE&oracle+erp+cloud&Cj0KCQjw7qn1BRDqARIsAKMbHDaSJX4r2woRQrLHIFTCk3imWrf6ORbhp3f1czxUvvxVTsz8Votd7TQaAhggEALw_wcB&gclid=Cj0KCQjw7qn1BRDqARIsAKMbHDaSJX4r2woRQrLHIFTCk3imWrf6ORbhp3f1czxUvvxVTsz8Votd7TQaAhggEALw_wcB&gclsrc=aw.ds)


## Part 1. Requesting an ERP Cloud Instance

### **STEP 1**: Login to Demo Central and Request an Environment

-   Once at the [homepage](https://demo.oracle.com/apex/f?p=DEMOWEB:HOME::::::), navigate to the "Demos" section. 

![](./images/demo-home.jpg " ")

-   Click the **Register a Demo**.

![](./images/register.jpg " ")

-   Search or select the Demo Title called **FUSION GSI - ERP, SCM, HCM & Engagement Cloud**.

![](./images/demo-title.jpg " ")

-   Fill in the details, demo resource details, activity dates, and any additional information. 

-   The select **Next** in the bottom right corner.

![](./images/details.jpg " ")

-   In the additional information section select the Horizontal or Industry-Specific category that is most applicable. 

-   The next field will ask if you want to add other to this Demo, if applicable please enter the Oracle email of the person you want to add to the demo.

-   Next, select the product you plan to include in your demo. This should be **Products -> Cloud Apps -> Fusion Apps -> ERP Cloud**.

-   Click **Next**.

-   Confirm your details and click **Submit**.

![](./images/submit.jpg " ")

### **STEP 2**: Access ERP Cloud Environment

-   Once the environment has been approved you will receive an email from **demo-central-noreplies_ww@oracle.com**, this will have a **link** where you can access your registration details and environment information. 

-   Make sure to save the access details and copy the password as we will be using it in the next part. Please **Note** that the environment password will change weekly. 

-   Then click on **Launch Demo**

![](./images/env-details.jpg " ")

-   Click on **ERP and SCM Cloud Login** and you will be taken to the **Sign In** page for your ERP instance.

![](./images/erp1.jpg " ")

-   Here you can sign-in with a few different users using the same password, but in this workshop we will be exploring two different personas. 

## Part 2. Provision a user from IDCS to ERP Cloud

### **STEP 1**: Access the IDCS console

-   Navigate to the **IDCS console** sign-in page provided by your lab facilitator. Enter the provided administrator username and password. **If you do not have the URL or the credentials, please contact your lab facilitator.**

![](./images/erp2.jpg " ")

-   Once logged in, you will see the IDCS console page displaying all of the relevant information (users, groups, passwords, etc.) that an identity domain administrator would be interested in.  

![](./images/da1.jpg " ")

-   In the **Users** module, click on the profile icon silhouette to navigate to the list of users in IDCS.

![](./images/da2.jpg " ")

### **STEP 2**: Create a new user in IDCS

-   We are now seeing the list of users in the current IDCS instance.

-   Click on the **Add** button to add a new user to IDCS.
    
![](./images/da3.jpg " ")

-   A window will pop up prompting us to enter the new user's information. Go ahead and fill out the required fields then click **Finish**.

![](./images/da4.jpg " ")

-   We're now prompted to assign this user to a group. For the purpose of this lab, the facilitators have already created the group for us. Assign the user to **ERP_FA_Users** then click **Finish**.

-   The new user is created and we can see the user's current information, groups and application access. If you explore the groups and access tabs, we can see that the user belongs to **ERP_FA_Users** group and has access to **two** applications. These applications allow us to provision the user from IDCS to ERP Cloud using a pre-built connector. 

![](./images/da5.jpg " ")

### **STEP 3**: Verify new user creation in ERP Cloud
-   Sign in to the demo ERP Cloud instance as **DEMOFAADMIN** and use the password copied previously from the clipboard. This user, Harry Hooper, is the security administrator for the ERP Cloud instance.

![](./files/receipt.jpg)

-   Navigate to the **home page** of the ERP Cloud instance.

-   Click on the upper left menu.

-   Expand the **Tools** submenu.

-   Click on **Security Console**.

![](./images/da7.jpg" ")

-   Here we see the security configuration settings available to the administrator. 

-   Click on **Users**.

![](./images/da8.jpg " ")

-   Now, we want to verify that the user we created in IDCS also exists in the ERP Cloud system.

-   In the **Search bar**, type the username of the user created in IDCS.

-   If the provisioning was successful, we will see the new user under **Search Results** as shown.

## Part 3. Change persona

### **STEP 1**: Sign out kerry.lane

-   Click the top right icon and then click on **Sign Out**

![](./images/signout.jpg " ")

### **STEP 2**: Sign in using brian.joseph

-   Enter the username **brian.joseph** and the **password** you copied earlier in the workshop.

![](./images/signin-brian.jpg " ")

### **STEP 3**: Interact with the Digital Assistant 

-   We are going to switch to the perspective of a new hire. This new hire was told to procure a laptop and business cards through his employer's pre-built Digital Assistant that has been integrated with ERP Cloud Procurement module. **Click** on the **Digital Assistant** icon in the bottom right hand corner and type in **I need a new laptop**

![](./images/laptop.jpg " ")

-   The Digital Assistant will prompt you if you would like it to recommend a laptop based on your job role. Type in **Yes**.

-   Browse what is available by clicking on the **Yellow side arrow** and select **more details** on your favorite option.

![](./images/browse.jpg " ")

-   The Digital Assistant will provide you with more details and ask if you would like more details on any other laptops.

-   Type in **No**

![](./images/no.jpg " ")

-   The Digital Assistant will ask if you have made a choice. Type in **Yes** and select the **Laptop** you would like to procure.

![](./images/select.jpg " ")

-   The Digital Assistant will create the purchase requisition and route the req. to your manager for approval. 

![](./images/purchase.jpg " ")

-   The next thing we need to do is procure business cards. To do this type in **Order business cards**

-   The Digital Assistant will respond and give you a preview. Select **Tap here**.

-   Select **Tap here**

![](./images/bc.jpg " ")

-   This will open up a new tab where you can preview your business cards, select the quantity, and submit the order.

![](./images/wb-1.jpg " ")

-   Select the quantity you want to order and select submit. **Close** the tab and open up the tab where you are logged into *ERP Cloud**.

![](./images/wb-2.jpg " ")

-   The Digital Assistant will create the requisition, display the status of the order, and give you the requisition number.

![](./images/fin.jpg " ")

-   When a new tab opened up, the application you were viewing is what's called a **WebView**. A WebView is an application that enables structured data entry through UI element and is able to integrate with the Digital Assistant. The WebView can validate user input and can be built using Oracle Visual Builder Cloud Service, like the one seen earlier, Oracle JET, or React. 


## Part 3. Mobile Application and Oracle's AI Voice

### **STEP 1**: Initial Setup

-   Follow the steps [here](https://demo.oracle.com/apex/f?p=GO:PAGE:0:DSD:NO:1:ID:53992) to install on iOS or Andriod mobile device. 

### **STEP 2**: Interact with ODA

-   In this portion of the workshop we are going to get a few updates on the Finance Manager's account.

-   You can interact with the ODA by typing in the chat box or by clicking the microphone icon in the bottom right.

-   Press the microphone button and say **What is the account balance for cleaning?**

![](./images/mobile-1.jpg " ")

-   Press the microphone button and say **How much do we owe our suppliers office depot?**

![](./images/mobile-2.jpg " ")

-   Press the microphone button and say **Which account has the largest budget surplus?**

![](./images/mobile-3.jpg " ")

-   Press the microphone button and say **Which project has the highest margins?**

![](./images/mobile-4.jpg " ")

-   Oracle’s Digital assistant provides broad channel support like slack, teams, sms, mobile apps, text-to-speech, and speech to text capabilities. In this portion of the workshop Oracle's AI Voice is being used with no risky exposure to 3rd party api's.

## BONUS: Create a twilio, slack, and/or Facebook channel route to Demo Services ODA

-   [Click here](https://demo.oracle.com/apex/f?p=GO:PAGE:0:DSD:NO:1:ID:76473) to do so.


## Summary

-   In this lab, you requested a demo ERP Cloud instance and interacted with the pre-built Digital Assistant skill for ERP. Oracle Digital Assistant pre-built skills showcase easy, interactive, intuitive and meaningful information without the need to login and open ERP applications.


-   **You are ready to move on to the next lab!**

[Back to top](#introduction)


