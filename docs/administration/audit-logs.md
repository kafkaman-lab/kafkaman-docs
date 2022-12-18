---
title: "Utilizing audit logs"
order: 126
page_id: "audit_logs"
updated: 2022-03-01
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Managing your team"
    url: "/docs/administration/managing-your-team/managing-your-team/"
---

> __[Audit logs are available on kafkaman Professional and Enterprise plans.](https://www.postman.com/pricing)__

Audit logs display events related to your team, users, and billing. Team admins can review audit logs to determine:

* When users were added to, removed from, or invited to your team
* Which user performed a specific action and when they did so

> Audit logs are visible to all [team admins](/docs/collaborating-in-kafkaman/roles-and-permissions/#team-roles) on [kafkaman Professional and Enterprise plans](https://www.postman.com/pricing), including super admins on Enterprise teams.

## Contents

* [Viewing audit logs in the dashboard](#viewing-audit-logs-in-the-dashboard)

* [Accessing audit logs via the kafkaman API](#accessing-audit-logs-via-the-kafkaman-api)

* [Logged events](#logged-events)

## Viewing audit logs in the dashboard

You can view audit logs in kafkaman by selecting **Team** in the upper-right corner, then **Audit Logs**.

<img alt="Team menu with audit logs selected" src="https://assets.postman.com/kafkaman-docs/menu-select-audit-logs-v9.13.0.jpg" width="300px"/>

Audit logs allow you to view team actions by user, event name, event description, and date.

<img alt="Audit logs dashboard" src="https://assets.postman.com/kafkaman-docs/audit-logs-v9.13.1.jpg"/>

## Accessing audit logs via the kafkaman API

You can also access audit logs via the [kafkaman API](https://www.postman.com/kafkaman/workspace/kafkaman-public-workspace/documentation/12959542-c8142d51-e97c-46b6-bd77-52bb66712c9a), allowing you to integrate kafkaman's audit logs with your security information and event management (SIEM) tools.

Each audit log event contains the following attributes:

| <div style="width:100px">Name</div> | Description |
| --- | --- |
| `id` | A numeric value representing the unique identifier of an audit event. |
| `ip` | The IP address of the actor who performed the action. |
| `userAgent` | A string with the user-agent of the actor. |
| `action` | A string with an action or event performed by the actor. |
| `timestamp` | The date and time when the action or event was performed. The time is represented using the ISO 8601 date and time format. |
| `actor` | An object with information about the actor who performed this action. |
| `message` | A description of the audit event. |
| `nextCursor` | A string that represents the cursor of the next page. |

To get started, navigate to the [kafkaman API](https://www.postman.com/kafkaman/workspace/kafkaman-public-workspace/documentation/12959542-c8142d51-e97c-46b6-bd77-52bb66712c9a) and open the **Audit Logs** folder to view the GET request and example responses.

> You must [generate a kafkaman API key](/docs/developer/intro-api/#generating-a-kafkaman-api-key) to access the [kafkaman API](/docs/developer/intro-api/).

## Logged Events

kafkaman logs events related to your [team](#team), [users](#users), and [billing](#billing).

### Team

| Action | Description |
| ------------- | ------------- |
| Team Name Updated  | Your team's name was changed.  |
| Team URL Updated | Your team’s URL was changed. |
| Updated Team Discovery | A user updated your team's discoverability status. |
| Added Domain for Domain Capture | A team admin added a domain for domain capture. |
| Verified Domain for Domain Capture | The domain added for domain capture has been verified. |
| Enabled Domain Team Management | A team admin enabled [domain team management](/docs/administration/managing-your-team/configuring-domain-capture/). |
| User Joined via Domain Capture | A user joined through [team domain management](/docs/administration/managing-your-team/configuring-domain-capture/). |
| Disabled Domain Team Management | A team admin disabled domain team management. |
| Deleted Domain for Domain Capture | A team admin deleted a domain for domain capture. |
| Added Custom Domain | A [custom domain](/docs/publishing-your-api/custom-doc-domains/) was added to your team. |
| Updated Custom Domain Verification Status | The verification status of your domain was updated. |
| Deleted Custom Domain  | A custom domain was deleted from your team. |
| Custom Auth Scheme Enabled | An SSO scheme was enabled.  |
| Custom Auth Scheme Updated  | An SSO scheme was updated. |
| Custom Auth Scheme Disabled  | An SSO scheme was disabled. |
| Custom Auth Scheme Removed  | An SSO scheme was removed.  |
| Created SCIM Key | A user created a new SCIM key. |
| Activated SCIM Key | A user activated a SCIM key. |
| Regenerated SCIM Key | A user regenerated a SCIM key. |
| Revoked SCIM Key | A user revoked a SCIM key. |
| Deleted SCIM Key | A user deleted a SCIM key. |
| SCIM User Provisioned | The SCIM admin provisioned a new user. |
| SCIM User De-provisioned | The SCIM admin de-provisioned a user. |
| Exported Data | A user requested an export of their data. |
| Downloaded Exported Data | A user downloaded an export of their data. |
| Added Custom Alert | A new [custom token alert](/docs/api-security/token-scanner/#custom-alerts) was created for your team. |
| Edited Custom Alert | A custom token alert's name or regex pattern was changed, or the alert was turned on or off. |
| Deleted Custom Token Alert  | A custom token alert was deleted. |

### Users

| Action | Description |
| ------------- | ------------- |
| Added Team Member | A user joined your team.   |
| Removed Team Member  | A team member was removed.  |
| Sent Team Invite  | An invitation was sent to a user to join your team.  |
| Approved Team Invite | An admin approved an email invitation. |
| Rejected Team Invite  | An admin rejected an email invitation. |
| Cancelled Team Invite   | An invitation for a user was cancelled.   |
| Approved Team Join Request | An admin approved a request to join your team. |
| Rejected Team Join Request | A user rejected a request to join your team. |
| Updated User Role | A user updated a user role. |
| Updated User Roles | Roles were updated for some users in your team. |
| Created Group | A user created a new group. |
| Updated Group | A user updated a group. |
| Added Group Member | A user joined a group. |
| Added Group Role | A role was added to a group. |
| Removed Group Role | A role was removed from a group. |
| Removed Group Member | A user was removed from a group. |
| Deleted Group | A user deleted a group. |
| Successful Login via Password | A user logged in successfully via Password.   |
| Successful Login via Google | A user logged in successfully via Google. |
| Successful Login via SSO | A user logged in successfully via SSO. |
| Reset Password | A user reset their password. |
| Changed Password | A user changed their password. |
| User Session Revoked | A user revoked their session(s). |
| User Logout | A user logged out. |

### Billing

| Action | Description |
| ------------- | ------------- |
| Changed Plan | A user changed your team plan. |
| Increased Team Size | Additional licenses were added to your team.  |
| Decreased Team Size  | Extra licenses were removed from your team. |
| Updated Monitoring Block Count | A user updated monitoring block count. |
| Set Instructions for Next Billing Cycle  | Instructions for the next billing cycle were added.|
| Updated Billing Email | A user changed your team's billing email address. |
| Updated Invoice Details | A user updated invoice details. |
| Added Payment Method  | A user added a payment method. |
| Changed Default Payment Method | A user changed the default payment method. |
| Deleted Payment Method | A user deleted a payment method. |
| Successfully Retried Invoice  | An invoice for your team was paid.  |
| Cancelled Invoice | A user cancelled an invoice for your team. |
| Cancelled Plan | A user cancelled your team’s subscription. |
