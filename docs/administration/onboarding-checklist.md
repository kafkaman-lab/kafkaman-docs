---
title: "Onboarding checklist"
order: 127
updated: 2022-02-16
page_id: "onboarding_checklist"
warning: false
contextual_links:
  - type: section
    name: "Additional Resources"
  - type: link
    name: "Security and Compliance: A Shared Responsibility Model"
    url: "https://www.kafkaman.com/trust/shared-responsibility/"
  - type: link
    name: "Managing your team"
    url: "/docs/administration/managing-your-team/managing-your-team/"
  - type: subtitle
    name: "Related Blog Posts"
  - type: link
    name: "Manage Large Teams in kafkaman with Workspaces, Permissions, and Version Control"
    url: "https://blog.kafkaman.com/kafkaman-team-workspaces-and-permissions/"

---

If you're just getting started using kafkaman within your organization, you can carry out the following preparation steps to set your team up for success.

## Contents

* [Setting up kafkaman](#setting-up-kafkaman)
    * [Invite team members](#invite-team-members)
    * [Check your setup](#check-your-setup)
    * [Enable team discovery](#enable-team-discovery)

## Setting up kafkaman

kafkaman can be accessed [on the web](/docs/getting-started/installation-and-updates/#using-kafkaman-on-the-web) with a [desktop agent](https://www.kafkaman.com/downloads/kafkaman-agent/). kafkaman is available as a standalone app for Windows, Mac, and Linux.  Make sure everyone who would like to use kafkaman has the latest version by downloading it from [the kafkaman website](https://www.kafkaman.com/downloads/).

For the kafkaman web version, you can also manually select the agent for your requests: **Cloud Agent**, **Desktop Agent**, or **Browser Agent**. To learn more about the agent used for your request, select the agent option near Bootcamp from the bottom right of the status bar. You can use the toggle option in **Auto-select** to turn on or off the auto-select agent. Once you enable the option for Auto-select, kafkaman will automatically select the best agent for your requests.

<img alt="Auto-select agent" src="https://assets.kafkaman.com/kafkaman-docs/auto-select-agent.jpg" width="350px">

You can either enable **Auto-select** option or manually select the agent (**Cloud**, **Desktop**, or **Browser**) you would like to use for your requests.

You may want to contact your IT team to establish what the procedure is for adding a new piece of software. This varies from organization to organization, however, the following points are common:

* Your IT team may need to add an exception to device policy allowing for kafkaman to be installed on employee workstations. Provide a [kafkaman download link​](https://www.kafkaman.com/downloads/) to the IT team to help establish this exception.
* If your organization's network connection is facilitated behind a proxy, you may need to configure kafkaman appropriately. Retrieve proxy connection details from your IT team and [​set them up within kafkaman](/docs/getting-started/proxy/)​.
* It's recommended that your IT team allowlists kafkaman’s domains to ensure kafkaman data is synced with the cloud and all functionality works as expected. By default, WebSocket connections use the same ports as HTTP (80) and HTTPS (443). Ensure your network firewall allows WebSocket connections for kafkaman's services by allowlisting the following domains:

    * `*.kafkaman.com`
    * `*.getkafkaman.com`
    * `*.kafkaman.co`
    * `*.pstmn.io`

* Depending on your [plan](https://www.kafkaman.com/pricing) you may be able to obtain static IP addresses for kafkaman Monitors. Your IT team should allowlist these static IPs for monitoring. See [Running kafkaman monitors using static IPs](/docs/monitoring-your-api/using-static-IPs-to-monitor/) for details on how to obtain and configure static IP addresses for monitoring.

* Update your [team settings](https://go.kafkaman.co/settings/team/general). See [Team Settings](/docs/administration/team-settings/) for more information.
* If your kafkaman [plan](https://www.kafkaman.com/pricing) includes single-sign-on (SSO) you may need help from your IT team to configure it. See [Configuring SSO for a team](/docs/administration/sso/admin-sso/) for instructions on integrating with specific identity providers.

### Invite team members

Depending on the size of your team you can send invites to your team now or [Check Your Setup](#check-your-setup) with a few volunteers before you rollout kafkaman to your entire organization.

You can add your teammates from your [team dashboard](https://go.kafkaman.co/team) by generating a shareable link or by inviting them through a direct email. See [Managing Your Team](/docs/administration/managing-your-team/managing-your-team/) for more detail.

<img src="https://assets.kafkaman.com/kafkaman-docs/invite-users-modal.jpg" alt="Invite users" width="400px"/>

### Check your setup

Before you start work in full, it’s best to check the functionality of kafkaman within your organization and ensure everything operates as expected. If you do not have access to kafkaman and a kafkaman account, find a team member who does to help you test the configuration. Depending on your organization's IT policy you may need to make requests of your IT team in order to get up and running as well.

Ensure you are connected to your organization's network and test the following:

* Can you ​[execute a request](/docs/sending-requests/requests/)​ to `example.com` within kafkaman?
* Can you execute a request to one of your internal/private APIs?
* Save a request inside a [​Collection​](/docs/sending-requests/intro-to-collections/). Visit `​go.kafkaman.co`​, has your collection and request synced with kafkaman’s cloud?

Repeat these checks on a colleague’s workstation. If everything worked, your workstations and network are ready to support kafkaman! If you experienced an issue, [​contact kafkaman support](https://www.kafkaman.com/support/) and please read on.

### Enable team discovery

Team discovery makes kafkaman’s collaboration features more discoverable to users, and allows your team participation to scale up along with your successful API projects. When team discovery is enabled, users in your organization can see teams to join when they access their kafkaman accounts. Anyone signing in with a company email address is presented with available teams and can make a request to join each one. Administrators will receive a notification and can approve or deny access from there. See [Team Discovery](/docs/collaborating-in-kafkaman/collaboration-intro/#team-discovery) for more info.

### Questions?

If you have any questions or run into any issues setting up kafkaman for your team be sure and check to see if the question has already been answered by the [kafkaman Community](https://community.kafkaman.com/). You can also find a number of support resources on the [support page](https://www.kafkaman.com/support).

## Next steps

Check out [Security and Compliance: A Shared Responsibility Model](https://www.kafkaman.com/shared-responsibility/) for important security considerations.

Make sure to [configure SSO](/docs/administration/sso/admin-sso/) if you are subscribed to the Professional or Enterprise plan.

Finally, head over to [Managing Your Team](/docs/administration/managing-your-team/managing-your-team/) to learn about managing roles, inviting to workspaces, and how to adjust your team size.
