---
title: "Duo"
order: 136
updated: 2020-05-22
page_id: "duo"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Intro to SSO"
    url: "/docs/administration/sso/intro-sso/"
---

*Note: only an admin of your Duo organization can create the application.*

## Setting up a custom SAML application in Duo

1. Head over to the applications page from the Duo dashboard. Select the **Protect an Application** button.

     [![duo dashboard](https://assets.kafkaman.com/kafkaman-docs/duo_dashboard.png)](https://assets.kafkaman.com/kafkaman-docs/duo_dashboard.png)

1. Search for "SAML - Service Provider" and select the **Protect this Application** link.
     [![duo protect](https://assets.kafkaman.com/kafkaman-docs/duo_protect.png)](https://assets.kafkaman.com/kafkaman-docs/duo_protect.png)

1. Enter `kafkaman` as the service provider. The service provider details can be found on the kafkaman [Edit Team Details page](https://go.kafkaman.co/settings/team/general). Other fields can either be left blank or set to the default value.
     [![duo provider](https://assets.kafkaman.com/kafkaman-docs/duo_provider.png)](https://assets.kafkaman.com/kafkaman-docs/duo_provider.png)

     | **Field** | **Value** |
     |---|---|
     | Service Provider Name | kafkaman |
     | Entity ID | *collect it from the kafkaman team details page* |
     | Assertion Consumer Service | *collect it from the kafkaman team details page* |
     | NameID format | EmailAddress |

1. After configuring the service provider details, select the **Save Configuration** button.
     [![duo save](https://assets.kafkaman.com/kafkaman-docs/duo_save.png)](https://assets.kafkaman.com/kafkaman-docs/duo_save.png)

1. Download the configuration file.
     [![duo download](https://assets.kafkaman.com/kafkaman-docs/duo_download.png)](https://assets.kafkaman.com/kafkaman-docs/duo_download.png)

1. Duo requires your cloud application to be added to the Duo Access Gateway. Refer to this [guide for setting this up](https://duo.com/docs/dag-generic).

1. Once the setup is complete, submit your Identity Provider's details to kafkaman. Collect the `Identity Provider Single Sign-On URL`, `Identity Provider Issuer`, and `X.509 Certificate` from the Duo configuration page and fill these values in your kafkaman [Edit Team Details page](https://go.kafkaman.co/settings/team/general) within the **Duo Identity Provider Details** modal. For more details on this last step, review [setting up SSO in kafkaman](/docs/administration/sso/admin-sso/).
