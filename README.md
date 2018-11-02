![alt text][logo]

# Socure ID+ Identity Verification Integration Guide

Socure provides the most accurate identity verification solution on the market. Socure’s ID+ Platform combines dozens of online and proprietary data sources, proprietary machine learning and AI, and traditional offline/credit header data to allow more financial inclusion for underbanked consumers, while delivering real-time intelligence that brings clients on board faster, reduces fraud, improves false positive rates, and meets KYC regulatory requirements. 

# Identity Verification Integration Guide

To begin using Socure ID+, register online with Socure to obtain an API key, configure the API key, and then set up the ID+ module. This guide walks you through the required steps.

## Step 1: Register with Socure

1. Open https://admin.socure.com and select Create Account.

2. Enter your name and contact information. Create a password, select an industry, and click Submit when ready. You will receive a confirmation email from Socure.

3. Contact Socure’s Customer Service team to confirm your account has been set up.
Log in to your account at https://admin.socure.com.

4. Select **Settings**. Note the two option tabs: **Production** and **Development**.
 * Use the Production settings for regular API transactions.
 * Use the Development settings to configure ID+ when testing API calls.
 
![alt text][dashboard]

5. In the API Keys section, all API Keys associated with either your production or development account are shown. Copy the production key.

6. In the Security section, update the Allowed Domains field with any domains associated with your account that should be placed on a whitelist. The address must be Internet-routable. This field supports comma-separated lists, and may contain domain names, single IP addresses, IP addresses with wildcards, and CIDR ranges.

7. Click **Update** to save your changes.

## Step 2: Configure Your API Key

Next, add the API Key as a stage in the openidm file. Update `selfservice-registration.json`, which can be found at:

```
/path/to/tomcat/webapps/openidm/conf
```

Add a new array including class and apiKey to the file.

```
{
    "stageConfigs" : [
        {
            "name": "parameters",
            ...
        },
        {
            "name" : "userQuery",
            ...
        },
        {
            "name" : "validateActiveAccount",
            ...
        },
        {
           "name" : "emailValidation",
            ...
        },
        {
           "class": "me.socure.forgerock.stage.idplus.IdPlusStageConfig",
           "apiKey": "a5b62fdf-1234-lkjh-48j3-d1639d4f72c7"
        },
        {
            "name" : "kbaSecurityAnswerVerificationStage",
            ...
        },
        {
            "name" : "resetStage",
            ..
        }
    ],
    ...
}
```

Also, if enabled, make sure to disable All In One Registration. When a registration process consists of more than one stage, it may include an optional **super stage** named `allInOneRegistration`. This stage is set outside of the stageConfigs array.

In `selfservice-registration.json`, confirm allInOneRegistration is set to false:

```
"allInOneRegistration" : false
```

## Step 3: Install the ID+ Module

1. Download the jar file containing the ID+ module code.

2. Copy idplus-stage-23.0.0.jar to the server: `/path/to/tomcat/webapps/openidm/bundle`

3. Restart IDM. The ID+ Verification stage will now display in the order in which it was configured in Step 2. For example, if added after the emailValidation stage, it will display as follows.
![alt-text][idplus_stage]

Setup is now complete; you may begin using Socure’s ID+ Identity Verification service. For assistance, please contact your Socure Customer Service representative using the information received in the registration email. 



[logo]: https://raw.githubusercontent.com/Socure/fr-releases/master/SOC_Logo_VT.png "Socure Logo"

[dashboard]: https://raw.githubusercontent.com/Socure/fr-releases/master/socure_dash.png "Socure Dashboard Settings page"

[idplus_stage]: https://raw.githubusercontent.com/Socure/fr-releases/master/forgerock_id_plus_stage.png "ID+ Stage Form"