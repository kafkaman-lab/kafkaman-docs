---
title: 'Okta'
order: 138
updated: 2021-01-20
page_id: 'okta'
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Intro to SSO"
    url: "/docs/administration/sso/intro-sso/"
---

> You must be an admin of your Okta organization in order to create this custom SAML application.

You can set up your custom SAML application by using the available kafkaman app in Okta or by configuring it directly in Okta.

## Contents

* [Setting up a custom SAML application in Okta](#setting-up-a-custom-saml-application-in-okta)
* [Setting up a custom SAML application in Okta by using the kafkaman app](#setting-up-a-custom-saml-application-in-okta-by-using-the-kafkaman-app)

## Setting up a custom SAML application in Okta

To set up custom SAML application, follow the procedure outlined below:

After you login to your Okta account, perform the following steps:

### Okta - Step 1

Select **Admin** as illustrated in the following screen:
[![okta admin](https://assets.kafkaman.com/kafkaman-docs/Okta-SAML1.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-SAML1.png)

### Okta - Step 2

From the Okta Dashboard, select **Add Application**.
[![okta add application](https://assets.kafkaman.com/kafkaman-docs/Okta-Add-Application.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-Add-Application.png)

### Okta - Step 3

Select **Create New App**, as illustrated below:
[![okta_new app](https://assets.kafkaman.com/kafkaman-docs/Okta-Create-Application.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-Create-Application.png)

### Okta - Step 4

In the following screen, ensure **Web** is selected as Platform. Select "SAML 2.0" and select **Create**.
[![okta choose saml](https://assets.kafkaman.com/kafkaman-docs/Okta-Choose-SAML.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-Choose-SAML.png)

### Okta - Step 5

Under the first step "General Settings", enter an application name and then select **Next**.
[![okta app name](https://assets.kafkaman.com/kafkaman-docs/okta_app_name.png)](https://assets.kafkaman.com/kafkaman-docs/okta_app_name.png)

### Okta - Step 6

Under the second step “Configure SAML”, section A “SAML Settings”, enter the kafkaman service provider details which can be found on the kafkaman [Edit Team Details](https://go.kafkaman.co/settings/team/general) page. To update the identity provider details, navigate to _Authentication -> <My_Okta_Integration_Name>_ and select **Edit**. Next, select **Proceed**. Ensure you are in the following screen after the completion of this step:
[![details](https://assets.kafkaman.com/kafkaman-docs/server-provider-details.jpg)](https://assets.kafkaman.com/kafkaman-docs/server-provider-details.jpg)

Now, download the encryption certificate. Select the **Download as file** link (shown in red circle). You will upload this later in the **Okta SAML** configuration section, which is explained below. In the following screen, select **Show Advanced Settings** link to configure advanced SAML assertion settings.
[![!okta service provider](https://assets.kafkaman.com/kafkaman-docs/okta_service_provider.png)](https://assets.kafkaman.com/kafkaman-docs/okta_service_provider.png)

| **Field**                   | **Value**    |
| --------------------------- | ------------ |
| Single Sign On URL          | ACS URL      |
| Audience URI (SP Entity ID) | Entity ID    |
| Name ID Format              | EmailAddress |

### Okta - Step 7

Configure the options as shown below. Ensure your field options reflect these values.
[![okta advanced](https://assets.kafkaman.com/kafkaman-docs/Okta-SAML-Adv-Settings.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-SAML-Adv-Settings.png)

For the Encryption Certificate, upload the encryption file in the **Encryption Certificate** field shown above. Remember, you downloaded the encryption file earlier using the **Download as a file** link in kafkaman's Service Provider Details section. Select **Next** to continue.

### Okta - Step 8

Under the third step “Feedback”, select “I’m an Okta customer adding an internal app”, and check “This is an internal app that we have created”, and then select **Finish**.
[![okta feedback](https://assets.kafkaman.com/kafkaman-docs/okta_feedback.png)](https://assets.kafkaman.com/kafkaman-docs/okta_feedback.png)

### Okta - Step 9

Move over to the **Sign On** tab, and select the **View Setup Instructions** button.
[![okta sign on](https://assets.kafkaman.com/kafkaman-docs/okta_sign_on.png)](https://assets.kafkaman.com/kafkaman-docs/okta_sign_on.png)

The **View Setup Instructions** screen comes populated with values that you should copy and paste in the **Identity Provider Details** section.

**Note:** You will need to come back to this screen to paste the value in _Default Relay State_ that you will generate from the kafkaman's **Identity Provide Details** section.

### Okta - Step 10

Copy the **Identity Provider Single Sign-On URL**, **Identity Provider Issuer** and **X.509 Certificate** from the below screen.
[![okta identity provider](https://assets.kafkaman.com/kafkaman-docs/okta_identity_provider_updated.png)](https://assets.kafkaman.com/kafkaman-docs/okta_identity_provider_updated.png)

And paste them in the corresponding sections of the **Identity Provider Details** screen as shown below:
[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-IDP-Details3.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-IDP-Details3.png)

Once you fill in the details, select the **Generate relay/Regenerate relay** button to create a parameter to send with a SAML response in an IDP-initiated single sign-on. Copy the **relay state** and paste it in the following screen:
[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-Relay-State.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-Relay-State.png)

To paste, select the **Edit** button and paste the value in **Default Relay State** field.

Select **Save Authentication**.

## Setting up a custom SAML application in Okta by using the kafkaman app

To set up custom SAML application using the kafkaman app, follow the procedure outlined below:

After you login to your Okta account, perform the following steps:

### kafkaman - Step 1

Select **Admin**:

[![okta admin](https://assets.kafkaman.com/kafkaman-docs/Okta-SAML1.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-SAML1.png)

### kafkaman - Step 2

From the Okta Dashboard, select **Add Application**.

[![okta add application](https://assets.kafkaman.com/kafkaman-docs/Okta-Add-Application.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-Add-Application.png)

### kafkaman - Step 3

In the search bar, search for _kafkaman_. Select **kafkaman**, and then select **Add**.

[![okta add application](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ1.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ1.png)

In the following screen, enter a name in the **Application Label** field and select **Done**.

[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ2.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ2.png)

### kafkaman - Step 4

Now, go to the kafkaman [Edit Team Details](https://go.kafkaman.co/settings/team/general) page. To update the identity provider details, navigate to _Authentication -> <My_Okta_Integration_Name>_ and select **Edit**. Next, select **Proceed**. Ensure you are in the following screen after the completion of this step:

[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-IDP-Details.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-IDP-Details.png)

Now, download the encryption certificate by selecting **Download as file** (shown in red circle). You will upload this later in the **Okta SAML** configuration section, which is explained below.

Navigate to your Okta account. Go to the **Sign On** tab and select **Edit**.
[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ3.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ3.png)

The following screen opens:
[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ4.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-New-Integ4.png)

Select **Browse** and upload the encryption certificate. Select **Save**.

### kafkaman - Step 5

Move over to the **Sign On** tab, and select the **View Setup Instructions** button.
[![okta sign on](https://assets.kafkaman.com/kafkaman-docs/okta_sign_on.png)](https://assets.kafkaman.com/kafkaman-docs/okta_sign_on.png)

The **View Setup Instructions** screen comes populated with values that you should copy and paste in the **Identity Provider Details** section.

**Note:** You will need to come back to this screen to paste the value in _Default Relay State_ that you will generate from the kafkaman's **Identity Provide Details** section.

### kafkaman - Step 6

Copy the **Identity Provider Single Sign-On URL**, **Identity Provider Issuer** and **X.509 Certificate** from the below screen.
[![okta identity provider](https://assets.kafkaman.com/kafkaman-docs/okta_identity_provider_updated.png)](https://assets.kafkaman.com/kafkaman-docs/okta_identity_provider_updated.png)

And paste them in the corresponding sections of the **Identity Provider Details** screen as shown below:
[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-IDP-Details3.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-IDP-Details3.png)

### kafkaman - Step 7

Once you fill-in the details, select the **Generate relay/Regenerate relay** button to create a parameter to send with a SAML response in an IDP-initiated single sign-on. Copy the **relay state** and paste it in the following screen:
[![details](https://assets.kafkaman.com/kafkaman-docs/Okta-Relay-State.png)](https://assets.kafkaman.com/kafkaman-docs/Okta-Relay-State.png)

To paste, select **Edit** and paste the value in **Default Relay State** field.

Select **Save Authentication**.
