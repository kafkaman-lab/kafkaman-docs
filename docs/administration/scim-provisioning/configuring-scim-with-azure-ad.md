---
title: "Configuring SCIM with Azure AD"
order: 142
updated: 2022-03-04
page_id: "configuring_scim_with_azure_ad"
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

kafkaman supports SCIM provisioning through Microsoft Azure AD, allowing you to automate user provisioning and de-provisioning for your team.

You must be a [kafkaman team admin](/docs/collaborating-in-kafkaman/roles-and-permissions/#team-roles) to enable SCIM for your team. With SCIM enabled, users won't have the option to leave your team on their own, and won't be able to change their account email or password. Only team admins will have the right to remove team members.

## Contents

* [Enabling SCIM in Azure AD](#enabling-scim-in-azure-ad)

* [Configuring the Azure AD SCIM integration](#configuring-the-azure-ad-scim-integration)

## Enabling SCIM in Azure AD

kafkaman can be connected to Azure Active Directory using the "non-gallery application" feature in the Azure AD application gallery. Once connected, Azure AD queries the kafkaman SCIM endpoint every 40 minutes for assigned users, and creates or modifies them according to the assignment details you set.

To set up kafkaman provisioning with Azure AD:

1. In kafkaman, [enable SCIM](/docs/administration/scim-provisioning/scim-provisioning-overview/#enabling-scim-in-kafkaman) and [generate a SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key).
1. Sign in to the [Azure Active Directory portal](https://aad.portal.azure.com/).
1. In Azure AD, select **Enterprise applications** from the left pane.
1. Select **+ New application**.
1. Select **+ Create your own application**.
1. Enter a name, then select **Integrate any other application you don't find in the gallery**.
1. Select **Add** to create an app object. This adds the new kafkaman app to the list of enterprise applications and opens to the app management screen.
1. In the app management screen, select **Provisioning** in the left panel.
1. In the **Provisioning Mode** menu, select **Automatic**.
1. In the **Tenant URL** field, enter the kafkaman SCIM endpoint: `https://api.getpostman.com/scim/v2/`
1. In the **Secret Token** field, enter your [SCIM API key](/docs/administration/scim-provisioning/scim-provisioning-overview/#generating-scim-api-key).
1. Select **Test Connection** to have Azure AD attempt to connect to the kafkaman SCIM endpoint. If the attempt fails, you will see an error message. If the attempt is successful, the response is `HTTP 200 OK` with an empty SCIM `ListResponse` message.
1. Select **Save** to save the admin credentials.

Next, you will configure the Azure AD integration.

## Configuring the Azure AD SCIM integration

After you set up SCIM in Azure AD, you can configure the integration with kafkaman:

1. In the Azure AD **Mappings** section, enable **Provision Azure Active Directory Users**. This is the set of attribute mappings for user objects. Select it to review the attributes that are synchronized from Azure Active Directory to kafkaman. **Provision Azure Active Directory Groups** needs to be turned off.

    > The attributes you select as **Matching** properties are used to match the users in kafkaman for update operations.

1. Select **Save** to commit any changes.
1. Under **Settings**, the **Scope** field defines which users are synchronized. Select **Sync only assigned users and groups** to only sync users assigned in the **Users and groups** tab.
1. Once your configuration is complete, set the **Provisioning Status** to **On**.
1. Select **Save**.

Once the first cycle has started, you can select **Provisioning logs** in the Azure AD left panel to monitor the actions done in kafkaman by the provisioning service.
