---
title: "Ping Identity"
order: 140
updated: 2020-05-22
page_id: "ping_identity"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Intro to SSO"
    url: "/docs/administration/sso/intro-sso/"
---

*Note: only an admin of your Ping Identity organization can create the application.*

## Setting up a custom SAML application in Ping Identity

1. From the Ping Identity admin console, select the **Applications** tab.
   [![ping_app](https://assets.kafkaman.com/kafkaman-docs/ping_app)](https://assets.kafkaman.com/kafkaman-docs/ping_app)

1. Under the **My Applications** tab, find the **Add Application** dropdown and select **New SAML Application**.
   [![ping_new_SAML](https://assets.kafkaman.com/kafkaman-docs/ping_new_SAML)](https://assets.kafkaman.com/kafkaman-docs/ping_new_SAML)

1. Fill in the required application details and continue to the next step.
   [![ping_details](https://assets.kafkaman.com/kafkaman-docs/ping_details)](https://assets.kafkaman.com/kafkaman-docs/ping_details)

1. Download the **SAML metadata** file, and enter your kafkaman service provider details. These details can be found on the kafkaman [Edit Team Details page](https://go.kafkaman.co/settings/team/general).

    | **Field** | **Value** |
    |---|---|
    | Protocol Version | SAML v 2.0 |
    | Assertion Consumer Service | *collect it from the kafkaman team details page* |
    | Entity ID | *collect it from the kafkaman team details page* |

    Leave the remaining fields blank or with the default value, and continue to the next step.
    [![ping service provider](https://assets.kafkaman.com/kafkaman-docs/ping_service_provider)](https://assets.kafkaman.com/kafkaman-docs/ping_service_provider)

1. Add **email** as an application attribute and map it to **Email**. Select **Save & Publish**.
   [![ping email](https://assets.kafkaman.com/kafkaman-docs/ping_email)](https://assets.kafkaman.com/kafkaman-docs/ping_email)

1. After configuring all the details, enable the new SAML application with the **Enable** toggle.
   [![ping toggle](https://assets.kafkaman.com/kafkaman-docs/ping_toggle)](https://assets.kafkaman.com/kafkaman-docs/ping_toggle)

1. Once enabled, the status will show as **Active** for the application.
   [![ping active](https://assets.kafkaman.com/kafkaman-docs/ping_active)](https://assets.kafkaman.com/kafkaman-docs/ping_active)

1. Once the setup is completed, submit your Identity Provider's details to kafkaman. Copy the `Identity Provider Single Sign-On URL`, `Identity Provider Issuer`, and `X.509 Certificate` from the downloaded **SAML metadata** file and enter these values on the kafkaman [Edit Team Details page](https://go.kafkaman.co/settings/team/general) within the **Ping Identity Provider Details** modal. For more details on this last step, review [setting up SSO in kafkaman](/docs/administration/sso/admin-sso/).
