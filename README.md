![alt text][logo]

# Socure ID+ Identity Verification Integration Guide

Trusted by 1,000+ top financial institutions, government agencies, and enterprises, Socure is the only graph-defined identity verification platform that utilizes every element of identity—delivering the most accurate fraud detection and identity verification in real time.

# Identity Verification Integration Guide

To begin using Socure ID+, register online with Socure to obtain an API key, configure the API key, and then set up the ID+ module. This guide walks you through the required steps.

## Step 1: Register with Socure

1. Open https://admin.socure.com and select Create Account.

2. Enter your name and contact information. Create a password, select an industry, and click Submit when ready. You will receive a confirmation email from Socure.

3. Contact Socure’s Customer Service team to confirm your account has been set up.
Log in to your account at https://admin.socure.com.

4. Select **Settings**. Note the three option tabs: **Production** and **Certification** and **Sandbox**.
 * Use the Production settings for regular API transactions.
 * Use the Sandbox settings to configure ID+ when testing API calls.

5. Socure provides a set of API keys for the Sandbox, Certification, and Production environments. These keys are shared across the organization. Users must have the correct permissions enabled for their account to access them.

Log in to Admin Dashboard.
Select an environment from the Account/Environment menu on the upper-right corner of the page.
Go to Developers > ID+ Keys, then click the vertical ellipsis and select Copy Key.

6. For security purposes, Socure requires you to specify the IP addresses that you will use to call the ID+ API. Socure will block any IP address not on the list. See Allowed Domains for more information.

7. As the account administrator, you are responsible for managing your organization's users. When you add a user, you assign them roles that grant or restrict access to pages in Admin Dashboard, as well as access to the Production, Certification, and Sandbox environments.

Log in to Admin Dashboard.

Go to Users & Roles > Users, then click New User.

Enter the user's personal information.

Under Account & Roles, click New Permissions.

On the Role Settings menu, select the account from the dropdown menu.

Select the roles you want to assign to the user, then click Save.

Repeat steps 4-6 to assign the user to additional accounts.

Click Create.

After you create their account, the user will receive an email with a link to set their account password. The link automatically expires after seven days.

## Step 2: Certify the Integration

Setup is now complete; you may begin using Socure’s ID+ Identity Verification service. For assistance, please contact your Socure Customer Service representative using the information received in the registration email. 



[logo]: https://raw.githubusercontent.com/Socure/fr-releases/master/SOC_Logo_VT.png "Socure Logo"

[dashboard]: https://raw.githubusercontent.com/Socure/fr-releases/master/socure_dash.png "Socure Dashboard Settings page"

[idplus_stage]: https://raw.githubusercontent.com/Socure/fr-releases/master/forgerock_id_plus_stage.png "ID+ Stage Form"
