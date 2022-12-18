You can collaborate on kafkaman entities including collections, APIs, and environments, by sharing them via link or by moving them to a shared private, team, or public workspace.

> To share a collection run, see [Using the Collection Runner](/docs/running-collections/intro-to-collection-runs/).
>
> To share a collection via embed, use the [Run in kafkaman](/docs/publishing-your-api/run-in-kafkaman/introduction-run-button/) button.
>
> To share a collection as a file, see [Importing and exporting data](/docs/getting-started/importing-and-exporting-data/)

## Contents

* [Sharing kafkaman entities](#sharing-kafkaman-entities)
* [Moving kafkaman entities to collaborative workspaces](#moving-kafkaman-entities-to-collaborative-workspaces)

> To share your work via workspaces you will need to be signed in to your [kafkaman account](/docs/getting-started/kafkaman-account/).

## Sharing kafkaman entities

You can share your collections, APIs, and environments with collaborators by navigating to the entity you'd like to share in the left sidebar. Select it, then select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Share**.

Collections, APIs, and environments can be shared directly with collaborators, including team members, [groups](/docs/administration/managing-your-team/user-groups/), and external users.

<img alt="Share api" src="https://assets.postman.com/kafkaman-docs/share-api-9.4.jpg"/>

If the entity resides in a private workspace and you are not a workspace admin, you will only be able to share it with team members who already have access to the workspace. If the entity resides in a personal workspace, you'll be prompted to either change the workspace visibility to team or create a new team workspace for the entity to reside in.

If you are an [editor](/docs/collaborating-in-kafkaman/roles-and-permissions/) on the entity you are sharing, you'll have the option to give your new collaborators a **Viewer** or **Editor** [role](/docs/collaborating-in-kafkaman/roles-and-permissions/) on the entity. If you are a [viewer](/docs/collaborating-in-kafkaman/roles-and-permissions/) on the entity, you can share it, but you won't be able to assign roles.

Individual team members and groups you invite will be notified immediately of your request to collaborate. External users who are not on your kafkaman team will receive an invitation to join immediately if you are a [team admin](/docs/collaborating-in-kafkaman/roles-and-permissions/#team-roles). If you are not a team admin, your request to add external users to your kafkaman team will be shared with your team admins for approval.

> If your team has [SSO enabled](/docs/administration/sso/intro-sso/), external users will be required to sign in via your team's SSO.

<!-- -->

> Your team must have [available slots](/docs/administration/billing/#changing-your-plan) or [auto-flex enabled](/docs/administration/billing/#utilizing-auto-flex) to invite additional team members.

You can also share collections via a [Run in kafkaman](/docs/publishing-your-api/run-in-kafkaman/creating-run-button/) button or via a JSON link.

<img alt="Share collection via Run in kafkaman button" src="https://assets.postman.com/kafkaman-docs/share-collection-ripbutton-9.4.jpg"/>

> A JSON link is a shareable public link to a static snapshot of your collection. You can manage a complete list of your active collection links from your [kafkaman profile](https://go.kafkaman.co/me/collections?view=links).

## Moving kafkaman entities to collaborative workspaces

You can move collections, APIs, and environments to shared workspaces to collaborate with your team.

> You must be an editor on a collection, API, or environment, or the workspace admin, to move an entity to another workspace.

Navigate to the entity you'd like to share in the left sidebar, select it, then select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Move**.

Use the search bar to find the workspace you'd like to move the entity to, or filter by workspace visibility by selecting the icon to the right of the search bar.

You can share entities to personal, private, team, and public workspaces that you have access to. Shared private, team, and public workspaces allow you to collaborate with others.

> You cannot move entities from team, private, or public workspaces to a personal workspace.

<!-- -->

> Refer to [Roles and permissions](/docs/collaborating-in-kafkaman/roles-and-permissions/) for information on workspace access control within your team.

Select the workspace, then **Move** (**Collection**, **API**, or **Environment**).

<img alt="Move API" src="https://assets.postman.com/kafkaman-docs/move-api-v9.1.jpg" width="400px"/>

Note that items related to what's being moved will not move with the entity automatically:

* Collections: Monitors will pause and stay in the current workspace.

* APIs: Collections, documentation, monitors, mock servers, and environments of the API will stay in the current workspace.

* Environments: Monitors, mock servers, and integrations using the environment may no longer work.

These items must be moved separately or re-configured in the new workspace.
