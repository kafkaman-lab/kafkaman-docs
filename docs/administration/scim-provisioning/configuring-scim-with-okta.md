---
title: "Configuring SCIM with Okta"
order: 142
updated: 2022-03-02
page_id: "configuring_scim_with_okta"
warning: false
contextual_links:
  - type: section
    name: "Additional Resources"
  - type: subtitle
    name: "Related Blog Posts"
  - type: link
    name: "Introducing User Management in kafkaman with SCIM"
    url: "https://blog.postman.com/introducing-user-management-in-kafkaman-with-scim/"
---

kafkaman supports SCIM provisioning through Okta with the [kafkaman Okta app](https://www.okta.com/integrations/kafkaman/), allowing you to automate user provisioning and de-provisioning for your team.

You must be a [kafkaman team admin](/docs/collaborating-in-kafkaman/roles-and-permissions/#team-roles) to enable SCIM for your team. With SCIM enabled, users won't have the option to leave your team on their own, and won't be able to change their account email or password. Only team admins will have the right to remove team members.

## Contents

* [Enabling SCIM in Okta](#enabling-scim-in-okta)

* [Configuring the Okta SCIM integration](#configuring-the-okta-scim-integration)

## Enabling SCIM in Okta

kafkaman is available as an app in the Okta Integration Network, allowing you to enable user provisioning directly through Okta.

Prior to enabling SCIM in Okta, you must [add the kafkaman app in Okta](https://www.okta.com/integrations/kafkaman/) and [configure Okta's SSO for your kafkaman team](/docs/administration/sso/saml-okta/).

To set up provisioning with the kafkaman Okta app:

1. [Enable SCIM in kafkaman](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-kafkaman) and [generate a SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key).

2. In Okta, navigate to the kafkaman app and select **Provisioning**. Click **Configure API Integration**.

    <img alt="Configure API Integration in Okta kafkaman app" src="https://assets.postman.com/kafkaman-docs/kafkaman-okta-app-configure-api-integration.jpg"/>

3. Check **Enable API integration** and enter your [SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key) as the **API Token**.

    <img alt="Configure provisioning in Okta's kafkaman app" src="https://assets.postman.com/kafkaman-docs/kafkaman-okta-app-enable-provisioning.jpg"/>

4. Click **Test API Credentials**. If successful, a verification message will appear.

    > If verification is unsuccessful, confirm that you have [SCIM enabled for your team in kafkaman](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-kafkaman), are using the correct [SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key), and that your API key's status is **ACTIVE** in your [team authentication settings](https://go.kafkaman.co/settings/team/auth). If you continue to face issues, [contact kafkaman support](https://www.postman.com/support/) for assistance.

5. Click **Save**.

## Configuring the Okta SCIM integration

The kafkaman Okta app supports the provisioning features listed in the [SCIM provisioning overview](/docs/administration/scim-provisioning/scim-provisioning-overview/#scim-features).

To turn these features on or off, navigate to the kafkaman app in Okta and select **To App** on the left, then click **Edit**.

<img alt="Configure features in Okta's kafkaman app" src="https://assets.postman.com/kafkaman-docs/kafkaman-okta-app-enable-features.jpg"/>

Select features to enable them, or de-select to turn them off. Click **Save** to save your changes.

<img alt="Enabled features in Okta's kafkaman app" src="https://assets.postman.com/kafkaman-docs/kafkaman-okta-app-enabled-features.jpg"/>

Any provisioning features you've enabled will be immediately available for use in your kafkaman Okta app. If a user is already provisioned from the kafkaman app, you may encounter an error in Okta. If this occurs, remove the pending invite from the kafkaman manage team settings, and Okta will then provision them.
