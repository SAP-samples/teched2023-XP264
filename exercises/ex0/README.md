# Accessing the BTP services

After you did activate your TRIAL Account for SAP BTP with access to the BTP Cockpit and the SAP Cloud Identity TRAIL with access to the SAP Cloud Identity Cockpit you are set for the next steps.

We can expect that you did create a **Trail subccount** in your SAP BTP Trail Account cockpit.

We also expect that you did enable the **Cloud Foundry Environment**.

Following the blog to setup the SAP Cloud Identity Services Trail you did already establish the Trust configration in your BTP Trail Subaccount, which adds the TRIAL Identity Provider  for applications to enable users from your TRAIL Identity Provider to log on to applications consumed in this subaccount.

## Result of the preparation

Now logon to your personal SAP BTP Trail account cockpit with the user you used to activate the Account.

Go to the [**SAP BTP Trial page**](https://account.hanatrial.ondemand.com/trial/#/home/trial)) and click **Log On**.

You will see one main button on the welcome screen of the SAP BTP Cockpit. Click on **Go To Your Trial Account** to navigate to your global account. Bookmark the link for fast and quick access to the cockpit.

Navigate to the subaccount and check if the Cloud Foundry runtime is enabled. If it is not enabled, click on Enable Cloud Foundry. This may take some seconds.

<br>![](/exercises/ex0/images/Subaccount%20Overview.png)

Check the Trust Configuration for application users

Navigate in the  BTP Cockpit to TRAIL HOME -> your initial subaccount (e.g. Trail Subaccount 1 ) -> Security -> Trust Configuration

Check if the Custom Identity Provider for Applications is configured. If not go back to the preparations and follow the blog on how to configure it.

<br>![](/exercises/ex0/images/Subaccoount1_TrustConfiguration.png)




## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
