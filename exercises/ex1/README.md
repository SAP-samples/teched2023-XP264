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

2. Open the SCI Trail cockpit, either from your bookmark or from the BTP cockpit -> Instances and Subscriptions -> click on the Tile next to Cloud Identity Services

<br><img src="/exercises/ex1/images/openSCItenant.png" width="70%">
  

3. In the pop-up window Sing-in with your email and password to the SCI Cockpit.
   
<br><img src="/exercises/ex1/images/SigninSCITRIAL.png" width="70%">

4. In the SCI Cockpit navigate to Applications & Resources -> Applications

<br><img src="/exercises/ex1/images/SCItenantApplications.png" width="70%">

5. On the left side you see Bundled and System Applications. In Bundeled Applications we see the Application XSUAA_trail. Click on it to see the confguriation data of this application. 
6. In the configuration screen of the XSUAA_trail application navigate to Authentication & Access
   
<br><img src="/exercises/ex1/images/SCItrailXSUAA_AuAcc.png" width="70%">

8. Now you can see the line where Risk-Based Authentication can be configured. Click on the little arrow on the right.

<br><img src="/exercises/ex1/images/XSUAA_trial_app_SCI.png" width="70%">

9. In the Risk-Based Authentication frame you have the possiblity to create Authentication Rules and you can see the Default Authentication Rule, which is **Allow**.

 <br><img src="/exercises/ex1/images/SCI_XSUAA_trial_RBA_default.png" width="70%">

10. Now change the Default Atuentication Rule to Default Action = Two-Factor Autnetication and Two-Factor Method = TOTF . Don´t forget to save at the top right of the page the new configuration. Now the access to all applications on SAP BTP which use the XSUAAA for authentication require a Time-based One-time Password Algorithmus (TOTP) as second factor. 
    
<br><img src="/exercises/ex1/images/SCI_XSUAA_trial_RBA_MFA.png" width="70%">




## Exercise 1.3 - Giving a user access to a subaccount

In the previous exercise, the user from the custom identity provider was given access to the global account. However, this does not mean that the user can access any 




## Summary

In this exercise you learned how to use a custom identity provider to authenticate the administrators that access the global account and subaccounts. You saw how a URL parameter can be used to choose the identity provider for authentication. Afterwards, you learned how to associate a user with a global account or subaccount, and how to assign the relevant role collections to give the user access to the cockpit functions. 



## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

