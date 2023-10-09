# Accessing the BTP services

After you did activate your TRIAL Account for SAP BTP with access to the BTP Cockpit and the SAP Cloud Identity TRAIL with access to the SAP Cloud Identity Cockpit you are set for the next steps.

We can expect that you did create a **Trail subccount** in your SAP BTP Trail Account cockpit.

We also expect that you did enable the **Cloud Foundry Environment**.

Follwing the blog to setup the SAP Cloud Identity Services Trail you did already establish the Trust configration in your BTP Trail Subaccount, which adds the TRIAL Identity Provider (Identity Authentication Service tenant) for applications to enable users from your TRAIL Identity Provider (Identity Atuentication Service tenant) to log on to applications consumed in this subaccount.

## Level 2 Heading

After completing these steps you will have....

1.	Click here.
<br>![](/exercises/ex0/images/00_00_0010.png)

2.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
