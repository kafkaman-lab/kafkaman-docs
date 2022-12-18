[Public workspaces](https://blog.kafkaman.com/public-workspaces-why-we-created-them-what-you-can-do/) enable you to collaborate on entities with anyone across the world. Before you create a public workspace, navigate to your [team profile settings](https://go.kafkaman.co/settings/team/general) and enable your public team profile. This will ensure your team's profile will show up on the [Public API Network](https://www.kafkaman.com/explore).

<img alt="Enable team profile" src="https://assets.kafkaman.com/kafkaman-docs/edit-team-profile-v9.1.0.jpg"/>

## Contents

* [Creating a public workspace](#creating-a-public-workspace)
* [Accessing a public workspace](#accessing-a-public-workspace)
* [Sharing a public workspace](#sharing-a-public-workspace)
* [Editing a public workspace](#editing-a-public-workspace)
* [Adding elements to a public workspace](#adding-elements-to-a-public-workspace)
* [Removing elements from a public workspace](#removing-elements-from-a-public-workspace)
* [Deleting a public workspace](#deleting-a-public-workspace)
* [Managing public workspace members](#managing-public-workspace-members)
* [Collaborating in a public workspace](#collaborating-in-a-public-workspace)
* [Adding summaries](#adding-summaries)
* [Next steps](#next-steps)

## Creating a public workspace

> You must be a [__workspace admin__](/docs/collaborating-in-kafkaman/roles-and-permissions/#workspace-roles) to change the visibility of a workspace to public.

There are four types of workspaces: personal, team, private, and public workspaces. When you open a workspace, kafkaman will provide an overview of its contents, activity, and members in a new tab.

Open the workspace menu, then select **Create Workspace**.

<img alt="Workspace menu" src="https://assets.kafkaman.com/kafkaman-docs/workspace-switcher-v9.1.jpg" width="400px"/>

Specify a workspace name and summary. Under **Visibility**, select **Public**.

<img alt="Create public workspace" src="https://assets.kafkaman.com/kafkaman-docs/create-public-wkspc-v9.5.jpg" width="400px"/>

> Within a team, you cannot have two public workspaces with the same name.

You can also convert an existing workspace to a public workspace. Open the workspace in kafkaman. In the **Overview** tab, select **Workspace Settings** in the upper right. Under **Visibility**, select **Public** from the dropdown list, then **Update**.

If you are on a kafkaman Professional or Enterprise plan, you need a community manager's approval to change a workspace's visibility to __Public__. In the **Overview** tab, select **Workspace Settings**. Under **Visibility**, select **Public** from the dropdown list, then **Request to Change Visibility**.

<img alt="Visibility" src="https://assets.kafkaman.com/kafkaman-docs/workspace-settings-request-visibility-change-v9.1.0.jpg" width="400px"/>

Once you make a workspace public, all entities within that workspace become publicly accessible through the workspace.

### Notifying workspace members

When you make a workspace public, a notification is sent to all workspace members. Select the notification icon <img alt="Changelog icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-notification-bell-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> in the top right corner to view notifications.

<img alt="In app notification" src="https://assets.kafkaman.com/kafkaman-docs/visibility-app-notification.jpg" width="500px"/>

In addition to this notification, all users will receive an email with the workspace information regarding who has made the change and which workspace was affected. The email will also provide a direct link to the workspace.

## Accessing a public workspace

You can access public workspaces using the kafkaman Explore page's [**Workspaces** category](https://www.kafkaman.com/explore/workspaces). You can also access the public workspaces that you own or are a member of using the **Workspaces** selector at the top of kafkaman.

![Access public workspaces](https://assets.kafkaman.com/kafkaman-docs/accessing-public-workspaces.jpg)

## Sharing a public workspace

You can share a public workspace by sharing its **public profile URL** directly. To access the public profile URL, navigate to your **Team**, then select **Team Settings**.

![View team settings](https://assets.kafkaman.com/kafkaman-docs/view-team-settings-for-public-profile.jpg)

Copy the **Public profile URL** and paste it in your browser to access your workspace.

<img alt="Enable public profile url" src="https://assets.kafkaman.com/kafkaman-docs/enable-public-profile-url.jpg"/>

## Editing a public workspace

To view and edit your public workspace's name and summary, navigate to the workspace in kafkaman. In the **Overview** tab, hover over the workspace name or summary and select to edit. Changes to the workspace name and summary will be saved automatically.

To update the workspace's visibility or to delete the workspace, select **Workspace Settings**.

<img alt="Create public workspace dropdown" src="https://assets.kafkaman.com/kafkaman-docs/workspace-edit-name-details-overview-tab-v9.1.jpg"/>

## Adding elements to a public workspace

You can add existing collections and environments to another public workspace by sharing them.

* To share a _collection_ to a public workspace, open it using Collections on the left side, then select <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Share collection**.
* To share an _environment_ to a public workspace, open it using Environments on the left side, then select <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Share environment**.

Select the public workspace you want to share to, and choose whether you also want to remove the element from its current workspace. Select **Share and Continue**.

## Removing elements from a public workspace

When you remove an element from a public workspace, it's no longer visible in that particular workspace. The element is still available in any other workspace where it has been added.

* To remove a _collection_ from a public workspace, open it using Collections on the left side, then select <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Remove from workspace**. Confirm that you would like to remove the collection from the current workspace. The collection will no longer be visible in the workspace.
* To remove an _environment_ from a public workspace, select <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the environment menu or select <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the Share button in the Environment tab. Select **Remove from workspace** and confirm that you would like to remove the environment from the current workspace. The environment will no longer be visible in the workspace.

> Deleting an element is different from removing it. When you delete an element, it's no longer available in any workspace. When you remove an element from a specific workspace, it will still be available in any other workspaces it was in.

## Deleting a public workspace

Public workspaces must have their visibility reverted in order to be deleted. If you try to delete a public workspace by selecting <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> on the right corner of the workspace overview, the option to delete will be greyed out.

![Deleting a public workspace](https://assets.kafkaman.com/kafkaman-docs/delete-option-greyed-public-workspace.jpg)

To change the visibility of a public workspace, change the visibility dropdown to **Team**, then **Save Changes**. After changing the visibility, you will be able to delete the workspace. Select <img alt="Three dots icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Delete workspace**.

## Managing public workspace members

If you're a team administrator you can add or remove any member from your public workspace using the **Members** tab. To add members to a public workspace, see [Sharing workspaces](/docs/collaborating-in-kafkaman/using-workspaces/managing-workspaces/#sharing-workspaces).

Another way to add workspace members is to select **Manage Team** and select **Invite Users**.

![Add workspace members to a public workspace](https://assets.kafkaman.com/kafkaman-docs/manage-team-v8.jpg)

Enter an email address, select **Add** to the team, select the roles you would like to assign to them, then select **Send Invitations**. You can also generate a link and invite people to your team by sharing the link with them.

![Edit members for a public workspace](https://assets.kafkaman.com/kafkaman-docs/edit-member-public-workspace.jpg)

> Team members will receive an email and in-app notification when added to a public workspace.

To remove any team member, select <img alt="External link icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-delete-v9.jpg" width="12px" style="vertical-align:middle;margin-bottom:5px"> (the delete icon) next to the individual you want to remove from the workspace, and select **Remove User From Team**.

![Remove team members for a public workspace](https://assets.kafkaman.com/kafkaman-docs/remove-member-public-workspace.jpg)

Select **X** next to the team member you want to remove from the public workspace, and select **Save**.

<img alt="Remove members for a public workspace from overview" src="https://assets.kafkaman.com/kafkaman-docs/remove-team-member-workspace-overview.jpg" width="400px"/>

## Collaborating in a public workspace

To collaborate on entities within a public workspace, open the workspace menu and select the workspace.

For collections and environments, [create a fork](/docs/collaborating-in-kafkaman/version-control-for-collections/#forking-a-collection) and request to merge changes using a [pull request](/docs/collaborating-in-kafkaman/version-control-for-collections/#creating-pull-requests).

For APIs, navigate to the API and version. Select **Definition** > **Request Access** to request an editor role.

## Adding summaries

Add summaries to improve the visibility of your collections, APIs, and workspaces on the Public API Network.

1. Navigate to your team page by selecting your team name from **Home**, then selecting **View team profile**.
1. Select the **Collections**, **APIs**, or **Workspaces** tab.
1. Hover over an item and select <img alt="Edit icon" src="https://assets.kafkaman.com/kafkaman-docs/documentation-edit-icon-v8-10.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> **Edit listing**.
1. Enter a brief **Summary** that describes your collection, API, or workspace.
1. Select **Save**.

![Adding a summary](https://assets.kafkaman.com/kafkaman-docs/workspace-add-summary-v9.5.jpg)

## Next steps

To add an API to the network, see [Adding your API](/docs/collaborating-in-kafkaman/adding-private-network/#adding-your-apis).
