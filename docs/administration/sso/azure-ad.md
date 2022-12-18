---
title: "Azure AD"
order: 135
updated: 2022-03-14
page_id: "azure_ad"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Configuring SSO for a team"
    url: "/docs/administration/sso/admin-sso/"
---

To configure SSO with Azure Active Directory (AD), you can use the available kafkaman app in Azure AD or create a custom SAML application. You must be an administrator in both Azure AD and kafkaman to configure SSO for your team.

## Contents

* [Configuring SSO with Azure AD](#configuring-sso-with-azure-ad)

* [Next steps](#next-steps)

## Configuring SSO with Azure AD

Before configuring a SAML application in Azure AD, you must [configure SSO in kafkaman](/docs/administration/sso/admin-sso/). When choosing the **Authentication Type**, select **SAML 2.0**. Name your authentication and **Proceed**.

<img alt="Configure identity provider details in kafkaman" src="https://assets.postman.com/kafkaman-docs/configure-identity-provider-details-v9.14.jpg"/>

Open your Azure AD management portal in a new tab to continue configuring your SAML application:

1. Navigate to **Enterprise applications** and select **+ New application**.
2. Search for "kafkaman" and select the kafkaman app from the results > **Create**. Or, you can **+ Create your own application**.
3. Select **Set up single sign on** > **SAML**.
4. Take the **Entity ID**, **Login URL**, and **ACS URL** from kafkaman and add them to your SAML configuration in Azure AD.

    <img alt="Basic SAML configuration in Azure AD" src="https://assets.postman.com/kafkaman-docs/basic-saml-config-azuread.jpg"/>
5. In kafkaman, select **Generate relay state** and add the generated value to your SAML configuration in Azure AD.

    <img alt="Generate relay state in kafkaman" src="https://assets.postman.com/kafkaman-docs/generate-relay-state-v9.14.jpg" width="350px"/>
6. Under **Attributes & Claims** in Azure AD, select **Edit** > **+ Add new claim**. Map the `Unique User Identifier (Name ID)` to the `user.mail` value.

    <img alt="Attributes and claims in Azure AD" src="https://assets.postman.com/kafkaman-docs/attributes-claims-config-azuread.jpg"/>
7. **Download** the Federation Metadata XML file in Azure AD under **SAML Signing Certificate**.

    <img alt="SAML signing certificate in Azure AD" src="https://assets.postman.com/kafkaman-docs/saml-signing-certificate-azuread.jpg"/>

8. In kafkaman, upload the Federation Metadata XML file under **Identity Provider Metadata File**. Or, you can enter the **Identity Provider SSO URL**, **Identity Provider Issuer**, and **X.509 Certificate** individually under **Identity Provider Details**.

9. Select **Save Authentication** in kafkaman.

You can test your SAML configuration by creating a test user in Azure AD and assigning them the kafkaman app. If you've opted to [automatically add new users](/docs/administration/sso/admin-sso/#automatically-adding-new-users) when configuring SAML, you'll be able to immediately log into kafkaman with the test user's credentials to confirm the process works as expected. If you haven't opted to automatically add new users, you can manually [invite the test user](/docs/administration/managing-your-team/managing-your-team/#inviting-to-a-team) to your kafkaman team and then log into kafkaman with the test user's credentials.

> If you encounter any issues, confirm you've added and saved the correct configuration values on both kafkaman and Azure AD. [Contact kafkaman support](https://www.postman.com/support/) for further help.

## Next steps

kafkaman Enterprise teams can continue by [configuring SCIM with Azure AD](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/).
