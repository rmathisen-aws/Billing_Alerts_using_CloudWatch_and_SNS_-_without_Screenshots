# Billing Alerts using CloudWatch and SNS

### Introduction:
Controlling costs within AWS is important if you want to avoid any bill-shock at the end of the month.

### Summary:
In this demo, we'll create a billing alarm which will notify you in the event that your estimated monthly costs exceed an agreed amount.

\
\
Account dropdown → My Billing Dashboard \
Preferences → Billing Preferences \
Check (3) boxes for..."Receive PDF Invoice by Email"..."Recieve Free Tier Usage Alerts" (fill in your email address)..."Receive Billing Alerts" \
Save Preferences

<br/>

### Configure the Billing Alert:

CloudWatch → Alarms → Create Alarm

Select Metric → Billing → Total Estimated Charge → Check USD → Select Metric

Conditions: Static...Greater...$XX.XX USD

Look at the Graph \
Notice the Red $10 USD limit line in comparison to the costs up to this point \
Next

Alarm State Trigger: In Alarm \
SNS: Create New Topic \
Name: BillingAlert \
Email: enter your email address \
Create Topic \
Next

Alarm Name: BillingAlert \
Next \
Create Alarm 

Notice your alarm's "Action" status shows "Pending Confirmation" \
Read the email that was just sent to you & confirm subscription \

Refresh the alarm \
State will change from "Insufficient Data" to "OK"

<br/>

### To allow IAM Users to Access the Billing Area:
By default, only the Account Root User can access the Billing area on the AWS Console. \
**We must be logged in as the Account Root User to be able to make this change!**

Account dropdown → My Account

IAM User and Role Access to Billing Information → Edit → Check box "Activate IAM Access" → Update

\
**For an Overview of all Costs on the Account:** \
Account dropdown → My Billing Dashboard \
Cost Management → **Cost Explorer** → Launch Cost Explorer

\
For best practices, explicitly fill out the \
**Billing, Operations & Security Alternate Contact Information:** \
Account dropdown → My Account \
Alternate Contacts → Edit → fill in all fields
