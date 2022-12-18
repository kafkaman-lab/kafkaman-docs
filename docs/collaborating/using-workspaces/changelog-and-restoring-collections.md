> **[Changelog is available on kafkaman Basic, Professional, and Enterprise plans.](https://www.kafkaman.com/pricing/)**

Your kafkaman collections display a changelog for reviewing create, update, and delete events. You can use the changelog to keep track of any updates you and your collaborators make to your private and team collections. The changelog also lets you rollback a collection and restore it to any previous point in time. kafkaman also tracks activity within teams and accounts.

## Contents

* Viewing changes to a [collection](#viewing-the-collection-changelog), [workspace](#viewing-workspace-activity), [team](#viewing-team-activity), or [user account](#viewing-user-activity).
* [Restoring collections and folders](#restoring-collections-and-folders)
* [Exporting team activity](#exporting-team-activity-to-other-platforms)
* [Next steps](#next-steps)

## Viewing the collection changelog

To review the changelog for a collection in kafkaman, select the __Collections__ tab in the left sidebar and select the __Changelog__ icon on the right of kafkaman to see a chronological list of collection activities.

The changelog indicates the date of each update, the user who carried it out, what type of update they performed, and the time the change occurred. The changelog collates consecutive updates on the same session to the same entity for readability.

![Collection changelog](https://assets.kafkaman.com/kafkaman-docs/collection-changelog-v8.jpg)

With a kafkaman Basic, Professional, or Enterprise account, you can see generated diffs detailing changes to a collection.

<img alt="Changelog diffs" src ="https://assets.kafkaman.com/kafkaman-docs/changelog-diff-v8.jpg" width=400px/>

## Viewing workspace activity

You can [access the activity feed from kafkaman](#accessing-the-activity-feed-from-kafkaman). The activity feed will show information on who added or removed collections, environments, or entities from the workspace as well as members joining and leaving the workspace. You can [filter this information](#filtering-the-activity-feed) directly within the activity feed.

You can also see who is actively working in your workspace at any time. The avatars of members currently active in the workspace will be brightly colored and displayed at the top of your kafkaman screen.

<img alt="Active user" src="https://assets.kafkaman.com/kafkaman-docs/active-member-v8.jpg" width="300px"/>

### Accessing the activity feed from kafkaman

To access the activity feed in kafkaman, select the Overview tab and navigate to the **Activity** section to see the events that have occured within the workspace.

[![Activity feed from kafkaman](https://assets.kafkaman.com/kafkaman-docs/activity-feed-overview-v8.jpg)](https://assets.kafkaman.com/kafkaman-docs/activity-feed-overview-v8.jpg)

### Filtering the activity feed

Filtering the activity feed allows you to display the relevant information directly instead of having to scroll through the feed. You can choose to filter by [user](#filtering-by-user) or by [entity](#filtering-by-entity) (Workspace, API, Collection, Environment).

To reset your search, select **Clear filters** at the right of the activity feed. You can also refresh the results by selecting **Refresh** at the right of the activity feed.

#### Filtering by user

Filtering by user will only display the actions the specified user carried out.
To filter by user, select **User** at the top of the activity feed and select the user or users. You can search for a specific user by typing their name in the search field. Once you have selected the user, select **Apply**.

> The user list will only show the users that are part of the workspace, not all team members.

[![Activity filtering by user](https://assets.kafkaman.com/kafkaman-docs/filter-by-user.gif)](https://assets.kafkaman.com/kafkaman-docs/filter-by-user.gif)

#### Filtering by entity

Filtering by entity will only display the actions carried out on the selected entity type. Available entities are `Workspace`, `API`, `Collection`, and `Environment`.
To filter by entity, select **Entity** at the top of the activity feed and select the entity or entities. You can search for a specific entity by typing its name in the search field. Once you have selected the entity, select **Apply**.

> You can access the changelog of a specific collection by selecting **View Changelog** next to actions on collections.

[![Activity filtering by entity](https://assets.kafkaman.com/kafkaman-docs/filter-by-entity.gif)](https://assets.kafkaman.com/kafkaman-docs/filter-by-entity.gif)

## Viewing team activity

You can review the activity for a team with a kafkaman Basic, Professional, or Enterprise account. In [kafkaman](https://go.kafkaman.co/), use the __Workspaces__ dropdown to select your team, then navigate to the __Activity__ feed to view the events.

## Viewing user activity

You can review the activity for your own account in [kafkaman](https://go.kafkaman.co/). Select your avatar in the top right, and select __Profile__ — the __Activity__ tab will list your events.

## Restoring collections and folders

With a kafkaman Basic, Professional, or Enterprise account, you can use the changelog to restore a collection to a previous point in time. Select __Restore__ under a change to revert the collection to the point immediately _after_ the change was applied. The changelog will update and kafkaman will display a confirmation message indicating the time the collection has been restored to.

<img alt="Restore from changelog" src="https://assets.kafkaman.com/kafkaman-docs/restore-changelog-v8.jpg" width="400px"/>

If you accidentally delete a folder, you can recover it by selecting __Restore__.

<img alt="Recover folder" src="https://assets.kafkaman.com/kafkaman-docs/restore-folder-v8.jpg" width="400px"/>

You may see a warning on any request tabs you have open that are affected by reverting the collection, for example indicating a conflict or deletion.

![Revert conflict](https://assets.kafkaman.com/kafkaman-docs/revert-conflict-v8.jpg)

kafkaman will prompt you to resolve any conflicts that may cause you to lose unsaved data.

## Exporting team activity to other platforms

With a kafkaman Basic, Professional, or Enterprise account, you can pipe team activity feeds to external communication channels:

* [Slack integration](/docs/integrations/available-integrations/slack/)
* [Microsoft Teams integration](/docs/integrations/available-integrations/microsoft-teams/)

## Next steps

For more on working with a team in kafkaman, see the [collaboration intro](/docs/collaborating-in-kafkaman/collaboration-intro/). To learn how to invite input on your API projects, see [sharing your work](/docs/collaborating-in-kafkaman/sharing/).
