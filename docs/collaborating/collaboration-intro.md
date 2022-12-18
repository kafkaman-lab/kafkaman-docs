
> kafkaman Free allows teams of up to three to collaborate at no cost. To collaborate with additional team members, features, and increased usage limits, see [Plans and Pricing](https://www.postman.com/pricing/).

kafkaman enables collaboration through [shared workspaces](/docs/collaborating-in-kafkaman/using-workspaces/creating-workspaces/). You can use workspaces to share your work with your teammates, including APIs, collections, environments, integrations, mock servers, and monitors.

## Contents

* [Enabling team discovery](#enabling-team-discovery)
* [Collaborating in team workspaces](#collaborating-in-team-workspaces)
    * [Inviting a team member to a workspace](#inviting-a-team-member-to-a-workspace)

    * [Finding teams within your organization](#finding-teams-within-your-organization)

    * [Leaving a team](#leaving-a-team)
* [Team usage limits](#team-usage-limits)
* [Next steps](#next-steps)

## Enabling team discovery

When you enable team discovery, users who have a verified email address with your company's domain can request to join pre-existing teams within your organization. This encourages collaboration and eases the onboarding process for your team members.

* Free users: Next to your avatar, select the menu to the right of **Upgrade**, then select **Manage Team**.
* Paid users: Next to your avatar, select **Team**, then select **Manage Team**.

On your Team Settings page, select **Team discovery** on the left, then select the toggle to turn team discovery on.

[![Enable team discovery](https://assets.postman.com/kafkaman-docs/team-discovery-enable-v9.7.0.jpg)](https://assets.postman.com/kafkaman-docs/team-discovery-enable-v9.7.0.jpg)

> Team admins will receive an email notification when team discovery is enabled.

You can optionally add a question for pending team members to answer when they request to join your team. Enter your question and select **Update Question**. Anyone who requests to join the team will be prompted with the question. If you do not specify a question, team members can still add a note when they request to join the team.

All admins will be notified when someone makes a request to join your team, including their answer to any question you set, or an optional note.

[![Team Request Approval](https://assets.postman.com/kafkaman-docs/admin-team-join-requests-v9.7.0.jpg)](https://assets.postman.com/kafkaman-docs/admin-team-join-requests-v9.7.0.jpg)

## Collaborating in team workspaces

Team workspaces allow you to collaborate on APIs, collections, environments, integrations, mocks, and monitors with your team.

> kafkaman creates a default "Team Workspace" for every team. You can rename this workspace, but it cannot be deleted.

kafkaman notifies you when activities occur within your team workspace. You can opt in to or out of these notifications by selecting your avatar in the upper right and selecting **Notification Preferences**.

### Inviting a team member to a workspace

You can invite team members to join a [new](/docs/collaborating-in-kafkaman/using-workspaces/creating-workspaces/) or existing workspace. For more details about how to invite a team member to a workspace, see [Sharing workspaces](/docs/collaborating-in-kafkaman/using-workspaces/managing-workspaces/#sharing-workspaces).

### Finding teams within your organization

When you log in to the kafkaman web dashboard using a verified email address for your company or organization, you can see available teams to join by selecting your avatar > **Your Team**. You will also be prompted with available teams when you first sign into your kafkaman account with a verified address.

[![Choose Team](https://assets.postman.com/kafkaman-docs/join-team-from-list.jpg)](https://assets.postman.com/kafkaman-docs/join-team-from-list.jpg)

You will see a list of the available teams within your organization. Select a team. Answer the question set by the team admin, if there is one. You can also add an optional note. Select **Request to join**.

<img alt="Team Join Question" src="https://assets.postman.com/kafkaman-docs/team-join-question-v9.7.0.jpg" width="400px"/>

Team admins will receive a notification when you ask to join the team. Once they approve your request, you'll be able to access the team and collaborate on API projects within it.

### Leaving a team

You can leave a kafkaman team by navigating to your [kafkaman Dashboard](https://go.kafkaman.co/home), selecting your avatar in the top right, then **Account Settings**. Select **Team** on the left. You can then opt to **Leave Team**.

<img src="https://assets.postman.com/kafkaman-docs/leave-team-v9.1.jpg" alt="Leave team"/>

> If your team has [SCIM configured](/docs/administration/scim-provisioning/scim-provisioning-overview/), you must contact your kafkaman team admins to leave the team.

When you leave a team, you no longer have access to the team's workspaces or any of the elements in them. You will still have access to your personal workspaces.

If you are the last member to leave your team, you will have the option to transfer collections to a personal workspace.

<img src="https://assets.postman.com/kafkaman-docs/leave-and-delete-team.jpg" alt="Leave and delete team" width="400px"/>

> If you are invited to a new team and you are the last member in your current team, all team data will be transferred to your personal default workspace.

## Team usage limits

The kafkaman usage menu allows you to review your team's limits for APIs, shared requests and history, mocks, monitors, and public documentation.

* **Free users**: Next to your avatar, select the menu to the right of **Upgrade**.
* **Paid users**: Next to your avatar, select **Team**.

For more details and to view your usage period, select **Resource Usage**.

<img src="https://assets.postman.com/kafkaman-docs/team-resource-limits-v9.7.0.jpg" alt="Usage limit information" width="400px"/>

## Next steps

kafkaman has many features to help you collaborate with your team:

* Assign [roles and permissions](/docs/collaborating-in-kafkaman/roles-and-permissions/) to define kafkaman access at the team, workspace, and entity level.
* Use [version control](/docs/collaborating-in-kafkaman/version-control-for-collections/) to collaborate with teammates on different forks of a shared collection or [versioning](/docs/designing-and-developing-your-api/versioning-an-api/) to collaborate on different versions of a shared API.
* Use your [Private API Network](/docs/collaborating-in-kafkaman/adding-private-network/) to securely share the APIs that your team uses internally.
