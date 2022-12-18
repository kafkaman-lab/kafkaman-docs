---
title: "OneLogin"
order: 139
updated: 2022-03-16
page_id: "onelogin"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Configuring SSO for a team"
    url: "/docs/administration/sso/admin-sso/"
---

To configure SSO with OneLogin, you can use the available kafkaman app. You must be an administrator in both OneLogin and kafkaman to configure SSO for your team.

## Contents

* [Configuring SSO with OneLogin](#configuring-sso-with-onelogin)

* [Next steps](#next-steps)

## Configuring SSO with OneLogin

Before configuring the kafkaman application in OneLogin, you must [configure SSO in kafkaman](/docs/administration/sso/admin-sso/). When choosing the **Authentication Type**, select **OneLogin**. Name your authentication and **Proceed**.

<img alt="Configure identity provider details in kafkaman" src="https://assets.postman.com/kafkaman-docs/configure-identity-provider-details-v9.14.jpg"/>

Open your OneLogin admin console in a new tab to continue configuring your kafkaman application:

1. Navigate to **Applications** and select **Add App**.
2. Search for "kafkaman" and select the kafkaman app from the results.
3. Select **Configuration** on the left.
4. Take the **ACS URL** from kafkaman and add it as your **SAML Consumer URL** in OneLogin.

    <img alt="OneLogin configuration application details" src="https://assets.postman.com/kafkaman-docs/onelogin-configuration3.jpg"/>

5. In kafkaman, select **Generate relay state** and add the generated value as the SAML RelayState in OneLogin.

    <img alt="Generate relay state in kafkaman" src="https://assets.postman.com/kafkaman-docs/generate-relay-state-v9.14.jpg" width="350px"/>

6. Select **SSO** on the left in OneLogin.
7. Copy the **Issuer URL** and add it as the **Identity Provider Issuer** in kafkaman.

    <img alt="OneLogin SSO Enable SAML 2.0" src="https://assets.postman.com/kafkaman-docs/onelogin-sso.jpg"/>

8. Copy the **SAML 2.0 Endpoint (HTTP)** and add it as **Identity Provider SSO URL** in kafkaman.
9. Select **View Details** under **X.509 Certificate**. Copy the **X.509 Certificate** and add it under **X.509 Certificate** in kafkaman.

10. Select **Save Authentication** in kafkaman to complete the configuration.

> If you encounter any issues, confirm you've added and saved the correct configuration values on both kafkaman and OneLogin. [Contact kafkaman support](https://www.postman.com/support/) for further help.

## Next steps

kafkaman Enterprise teams can continue by [configuring SCIM with OneLogin](/docs/administration/scim-provisioning/configuring-scim-with-onelogin/).
