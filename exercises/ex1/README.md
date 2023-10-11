# Exercise 1 - Configure multifactor authentication for applications

In this exercise, we will show how to configure risk based authentication for applications in a subaccount. In your company you can configure the riskbased authentication additionally for the access to the SAP BTP Cockpit. In the trial version this is not possible, because there is no possility to set up a trust configuration to your BTP account on Global account level. This would be necessary to configure the trust for [platform users](https://help.sap.com/docs/btp/best-practices/basic-platform-concepts). 
The configuration in the SCI cockpit is the same, only for a different application. You will use SAP Build Apps as application to configure the riskbased authentication.

# Relevant Security Recommendations
- BTP-UAA-0001


## Exercise 1.1 - Subscribe to SAP Build Apps and enter the application with your trail identity provider user


1. Open the SAP BTP Cockpit and navigate to your global account. You should have bookmarked the URL in the Getting started excercise.

2. Navigate to Boosters

<br><img src="/exercises/ex1/images/GA-Boosters.png" width="70%">

4. Enter SAP Build Apps in the search field. Click on **Get started with SAP Build Apps**.

<br><img src="/exercises/ex1/images/gBoostergetstartedsapbuild apps.png" width="70%">

5. Now a wizzard opens and you follow the wizzard and click next after each entry.

Check prerequisites
<br><img src="/exercises/ex1/images/booster2.png" width="70%">

Select Scenario - select your subaccount

<br><img src="/exercises/ex1/images/booster3.png" width="70%">

Configure subbaccount - enter your trail subaccount

<br><img src="/exercises/ex1/images/Booster4.png" width="70%">

Add Users - enter your email adresss as logon ID for Administrators and Developers

<br><img src="/exercises/ex1/images/Booster5.png" width="70%">

Review your entries - Finish

<br><img src="/exercises/ex1/images/booster6.png" width="70%">

Progressing -takes a bit

<br><img src="/exercises/ex1/images/Booster 7.png" width="70%">

Sucess - Navigate to the Subaccount 

<br><img src="/exercises/ex1/images/Boostersuccess.png" width="70%">

Go to Instance and Subscriptions in your Subaccount - Click on the tile to open SAP Build Apps 

<br><img src="/exercises/ex1/images/openSAPBulidApps.png" width="70%">

A Logon page opens. Use your Trial Account Identity Provider to logon. There is the Default Identity Provider ( SAP ID Service ) shown and your Trail Account Identity provider.

<br><img src="/exercises/ex1/images/openSAPBulidApps.png" width="70%">

The Logon should be succesfull as your user is assigned to the role collections needed during the booster creation process.
You will see the entry page of the SAP Build App application.

<br><img src="/exercises/ex1/images/SAP Build App.png" width="70%">



## Exercise 1.2 - Configuring mutlifactor authentication to access SAP Build Apps

In exercise 1.1 we enabled SAP Build Apps and the configured users are now able to authenticate with the custom identity provider when they try to access the application. However, we want to restrict the access to the application and only allow access with a second authentication factor.

1. Logout of the SAP Build application and close the Browser window.

<br><img src="/exercises/ex1/images/Singoutsapbuild.png" width="70%">

2. Open the SCI Trail cockpit, either from yor bookmark or from the BTP cockpit - Instances and Subscriptions - click on the Tile next to Cloud Identity Services

<br><img src="/exercises/ex1/images/openSCItenant.png" width="70%">
  

4. Review the list of users associated with the global account. Only users from the default identity provider are listed.
<br><img src="/exercises/ex1/images/Global_Account_Users_Blurred.png" width="70%">

5. Click on the "Create" button

6. In the "New User" dialog, choose your custom identity provider, enter the username and e-mail address of your user in the custom identity provider and click on "Create".
<br><img src="/exercises/ex1/images/New_User.png" width="70%">

7. The user is added to the list and is now associated with the global account. However, the user does not yet have any authorizations. To change this, click on the ">" character at the right end of the row for the new user. A dialog with the user details is displayed. So far, no role collections were assigned to the user. Click the "Assign Role Collection" button.
<br><img src="/exercises/ex1/images/Assign_Role_Collection_Button.png" width="70%">

:bulb: If your browser window is rather small, the "Assign Role Collection" button may not be visible. It becomes available if you click on the button with the tooltip "More" to the right of the search field in the "Role Collections" section.
<br><img src="/exercises/ex1/images/Assign_Role_Collection_More.png" width="70%">

6. In the "Assign Role Collection" dialog, select the entry "Global Account Administrator" and click on "Assign Role Collection".
<br><img src="/exercises/ex1/images/Assign_Role_Collection.png" width="70%">

7. The role collection "Global Account Administrator" is now shown in the list of the user's role collections

8. In the SAP BTP Cockpit, choose the menu item Security --> Trust Configuration and click on "Open" in the row for your custom identity provider

9. On the logon page of the custom identity provider, authenticate with your credentials for the custom identity provider. This time the SAP BTP Cockpit for the global account is displayed

10. Click on your username in the upper right corner of the cockpit and choose the menu item "User Information". You are indeed signed in with the user from your custom identity provider, who is now administrator of the global account.

:bulb: How does the browser know, which identity provider to use for authentication? It is specified in the URL! 
- To use the default identity provider, in this case SAP ID Service, call a URL like https://cockpit.eu10.hana.ondemand.com/cockpit#/globalaccount/...
- To use a specific custom identity provider, call a URL like https://cockpit.eu10.hana.ondemand.com/cockpit/?idp=bestrun01.accounts.ondemand.com#/globalaccount/...


## Exercise 1.3 - Giving a user access to a subaccount

In the previous exercise, the user from the custom identity provider was given access to the global account. However, this does not mean that the user can access any subaccount. In this exercise we will enable the user to also access a subaccount.

1. From the previous exercise you are still signed into the cockpit with the user from the custom identity provider. Choose the menu item "Account Explorer" and click on the subaccount tile. 
<br><img src="/exercises/ex1/images/Subaccount_Tile.png" width="70%">

2. You receive an error message that your user is not a member of the subaccount. The user from the custom identity provider is only associated with the global account, no subaccount
<br><img src="/exercises/ex1/images/Error_Not_Subaccount_Member.png" width="70%">

3. Logoff from the SAP BTP Cockpit. Open the SAP BTP Cockpit URL again in the browser and authenticate with your SAP ID Service credentials. Make sure that you use the URL in the format https://cockpit.eu10.hana.ondemand.com/cockpit#/globalaccount/. If the "?idp=" parameter was in the URL, you would be taken to your custom identity provider instead.

4. In the account explorer, click on the subaccount again. As your SAP ID Service user is already a member of the subaccount, you can access the subaccount overview page
<br><img src="/exercises/ex1/images/Subaccount_Blur.png" width="70%">

5. Just like for the global account, click on the menu item Security --> Users of the subaccount overview. You will see the list of subaccount members. Click on "Create".

6. The "New User" dialog looks just like for the global account. Choose your custom identity provider and enter the user name and e-mail address for your user in the custom identity provider. Then click on "Create".

7. When the new entry is displayed in the list of members, click on the ">" character to display the details of the new subaccount member. As for the global account, the user initially has no role collections assigned.

8. Click on "Assign Role Collection", select the following 4 entries: "Cloud Connector Administrator", "Connectivity and Destination Administrator", "Destination Administrator" and "Subaccount Administrator" and click on "Assign Role Collection"
<br><img src="/exercises/ex1/images/Assign_Role_Collection_Subaccount.png" width="70%">

9. To test the configuration, switch to the user from the custom identity provider. Choose the menu item Security --> Trust Configuration. Click on the "Open" link in the row for your custom identity provider in the section "Custom Identity Provider for Platform Users".

10. The logon page for the custom identity provider is shown. Enter your credentials for this identity provider.

11. After authentication, the subaccount overview page is displayed as the user from the custom identity provider is now also a member of the subaccount and has the necessary access.

## Summary

In this exercise you learned how to use a custom identity provider to authenticate the administrators that access the global account and subaccounts. You saw how a URL parameter can be used to choose the identity provider for authentication. Afterwards, you learned how to associate a user with a global account or subaccount, and how to assign the relevant role collections to give the user access to the cockpit functions. 



## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

