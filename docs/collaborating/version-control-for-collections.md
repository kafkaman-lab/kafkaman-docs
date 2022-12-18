kafkaman's version control features provide a way for you and your team to collaboratively build an API. You can fork a collection, make updates to the fork, create a pull request, and merge your changes into the parent collection.

> Version control for collections is different from API versioning. For information on managing multiple versions of APIs, see [Versioning APIs](/docs/designing-and-developing-your-api/versioning-an-api/).

* [Forking kafkaman elements](#forking-kafkaman-elements)
    * [Forking a collection](#forking-a-collection)
    * [Forking an environment](#forking-an-environment)
    * [Viewing fork information](#viewing-fork-information)
* [Creating pull requests](#creating-pull-requests)
    * [Creating public pull requests](#creating-public-pull-requests)
    * [Pull request settings](#pull-request-settings)
* [Watching a pull request](#watching-a-pull-request)
* [Reviewing pull requests](#reviewing-pull-requests)
    * [Viewing the diff](#viewing-the-diff)
    * [Adding comments](#adding-comments)
    * [Editing or declining a pull request](#editing-or-declining-a-pull-request)
    * [Approving a pull request](#approving-a-pull-request)
    * [Pulling updates](#pulling-updates)
    * [Merging changes](#merging-changes)
* [Resolving conflicts](#resolving-conflicts)

## Forking kafkaman elements

A _fork_ is a new instance of an element that you can modify without making any changes to the parent element. In kafkaman, you can fork [collections](#forking-a-collection) and [environments](#forking-an-environment). Forking also enables you to contribute to a collection or an environment without having Editor access to that element.

### Forking a collection

> To fork a collection within a public workspace, you must enable your public profile in your [profile settings](https://go.kafkaman.co/settings/me). For more information on making your profile public, see [Managing your account](/docs/getting-started/kafkaman-account/#making-your-profile-public).

When you fork a kafkaman collection, you create a copy of it in a different workspace.

To fork a collection:

1. Select **Collections** in the left sidebar.
1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection name.
1. Select **Create a fork**.

    <img src="https://assets.postman.com/kafkaman-docs/collection-create-a-fork-v9.1.jpg" alt="Create fork selected in menu" width="300px"/>

    > You can also fork a collection by selecting **Fork** on the collection overview tab.

1. Enter a label for your fork, and select a workspace to save it to.
1. Select **Fork Collection**.

    <img src="https://assets.postman.com/kafkaman-docs/fork-collection-v9.1.jpg" alt="Create fork tab" width="400px"/>

Your fork will be created in the selected workspace.

If there are any [mocks](/docs/designing-and-developing-your-api/mocking-data/setting-up-mock/) or [monitors](/docs/monitoring-your-api/intro-monitors/) associated with a collection, they will not be linked to the forked collection. You will need to create mocks and monitors specifically for the fork if you need them.

> If you are not a member of a public workspace, you won't be able to send a request from a collection within the workspace. To send requests or make changes to a collection, fork the collection into a personal workspace or a team workspace that you belong to. You must be signed in to kafkaman to fork a collection.

### Forking an environment

To fork an environment in kafkaman:

1. Select **Environments** in the left sidebar.
1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the environment name.
1. Select **Create a fork**.

    <img src="https://assets.postman.com/kafkaman-docs/environment-create-a-fork-v9.1.jpg" alt="Create an Environment Fork" width="300px"/>

    > You can also fork an environment by selecting **Fork** on the environment overview tab.

1. Enter a label for your fork, and select a workspace to save it to.
1. Select **Fork Environment**.

    <img src="https://assets.postman.com/kafkaman-docs/fork-environment-v9.1.jpg" alt="Fork environment tab" width="400px"/>

Your forked environment will be created in the selected workspace. You will be able to view forked environments in **Environments** as well as under the environment dropdown list on the right side of kafkaman.

<img alt="Environment dropdown for forked environments" src="https://assets.postman.com/kafkaman-docs/environment-dropdown-view-v9.12.jpg" width="300px"/>

### Viewing fork information

Fork information provides details about forks and the users who have created them. You will be able to identify the users who are actively consuming and contributing to your APIs.

To see the list of users who have forked a collection or an environment:

1. Select the number next to the fork icon <img alt="Fork icon" src="https://assets.postman.com/kafkaman-docs/icon-fork.jpg" width="14px" style="vertical-align:middle;margin-bottom:5px"> to reveal the list of users who have active forks.

    <img alt="View the fork information count" src="https://assets.postman.com/kafkaman-docs/fork-information-count-v9.12.jpg" width="400px"/>

To see the list of forks for a collection:

1. Select the fork icon <img alt="Fork icon" src="https://assets.postman.com/kafkaman-docs/icon-fork.jpg" width="14px" style="vertical-align:middle;margin-bottom:5px"> in the context bar.
1. Select the fork name under **Forks**.

    > You can also select the user's avatar under **Forks** to view the user's public profile.

    <img alt="View the list of forks" src="https://assets.postman.com/kafkaman-docs/fork-information-list-v9.12.jpg" width="350px"/>

## Creating pull requests

> Pull requests are only available for collections.

When you have made the changes that you want to a forked collection, you can create a _pull request_. Creating a pull request means that you want to merge the changes you made in the forked collection (the _source_) into the parent collection (the _destination_). As part of the pull request process, you will request that reviewers look at your changes. The reviewers can make comments on your changes and will decide whether to approve them and merge them into the parent collection.

To create a pull request:

1. Select the forked collection in the **Collections** sidebar.
1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection name.
1. Select **Create pull request**.

    <img alt="Create Pull Request" src="https://assets.postman.com/kafkaman-docs/create-pull-request.jpg" width="250px"/>

1. Select **Changes** to review the content changes that will be included in the pull request.

    ![Pull Request Changes](https://assets.postman.com/kafkaman-docs/pull-request-changes.jpg)

    * If the parent collection has any changes since you last updated your fork, you can [pull those changes](#pulling-updates) into your fork before merging.

    * If there are any conflicts between the fork and the parent collection, they will be highlighted so that you can [resolve them](#resolving-conflicts).

1. Select **Overview**.
1. Enter a title and description for your pull request, and select up to 50 reviewers from the dropdown list. Reviewers must have Editor access to the collection to merge your changes.
1. Select **Create Pull Request**.

    <img alt="Create Pull Request" src="https://assets.postman.com/kafkaman-docs/pull-request-overview.jpg" width="350px"/>

The reviewers you selected will be notified about your pull request. You will receive a notification if the reviewers [comment on](#adding-comments), [approve](#approving-a-pull-request), or [merge](#merging-changes-from-a-pull-request) the pull request.

> A reviewer must have **Editor** access on the parent collection to merge changes. If a reviewer only has **Viewer** access to a collection, you will see a warning icon if you add them as reviewers for a pull request.
>
> <img alt="Reviewer permission" src="https://assets.postman.com/kafkaman-docs/pull-request-reviewer-permission.jpg" width="350px"/>

### Creating public pull requests

To create a pull request on a public collection, you must fork the parent collection into a public workspace so that the users you ask to [review it](#reviewing-pull-requests) have access to it.

1. Begin the pull request process described in [Creating pull requests](#creating-pull-requests). You will see a note that tells you to move the source collection to a public workspace.
1. Select the public workspace where you want to move the collection.
1. Select **Move Collection**.

    <img src="https://assets.postman.com/kafkaman-docs/make-source-collection-public-v9.jpg" alt="Make the source collection public" width="400px"/>

1. After you move the collection to a public workspace, proceed with the workflow in [Creating pull requests](#creating-pull-requests).

Once you create the pull request, you will get a notification that it has been **Shared to public workspace**.

### Pull request settings

> Pull request settings are available on [kafkaman Professional and Enterprise plans](https://www.postman.com/pricing).

Pull request settings let you manage permissions for reviewers and assign merge checks.

#### Manage reviewer permissions

1. Select the collection in the **Collections** sidebar.
1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection name.
1. Select **Manage roles**.

    <img alt="Collection Manage Roles" src="https://assets.postman.com/kafkaman-docs/collection-manage-roles-v9.1.jpg" width="300px"/>

1. Select **Editor** for the users you want to provide Editor access to.
1. Select **Update Roles**.

    [![manage roles](https://assets.postman.com/kafkaman-docs/manage-roles-collection-v9.12.jpg)](https://assets.postman.com/kafkaman-docs/manage-roles-collection-v9.12.jpg)

#### Assign merge checks

Once you have created the pull request, you can assign merge checks before approving changes.

There are two different types of checks that you can enable for a pull request:

* **Approved once**: You need at least one approval to merge the pull request.
* **Approved by a collection editor**: You need the approval of a collection editor to merge the pull request.

To set merge checks for pull requests on a specific collection:

1. Select the collection in the **Collections** sidebar.
1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection name.
1. Select **Manage roles**.
1. Select the merge checks that you want to set for the collection.

<img alt="Merge Check" src="https://assets.postman.com/kafkaman-docs/manage-roles-set-merge-checks.jpg" width="800px"/>

If the merge conditions for a pull request are not met, the option to **Merge** it into the parent collection will be active.

<img alt="Merge option is not active" src="https://assets.postman.com/kafkaman-docs/view-merge-conditions-v9.12.jpg" width="300px"/>

Select **View Merge Conditions** to see the merge conditions to be met for the pull request.

<img alt="Merge Condition" src="https://assets.postman.com/kafkaman-docs/merge-conditions.jpg" width="400px"/>

## Watching a pull request

The watch option enables you to receive an in-app notification when a team member modifies the pull request. If you watch a pull request, you will be notified of actions such as adding a new comment, approving or unapproving, merging, and editing or declining a pull request.

To watch a pull request:

1. Select **Watch**.

<img alt="Watch a pull request" src="https://assets.postman.com/kafkaman-docs/watching-a-pull-request-v9.12.jpg" width="300px"/>

To change your watching notification settings:

1. Select **Watching**.
1. Select or unselect the desired notification options.

<img alt="Conditions for watch notifications" src="https://assets.postman.com/kafkaman-docs/watching-conditions-notifications-v9.jpg" width="350px"/>

To view notifications for a watched pull request:

1. Select the bell icon <img alt="Changelog icon" src="https://assets.postman.com/kafkaman-docs/icon-notification-bell-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> in the top right corner of kafkaman. The popup indicates further information about the change that was made to the pull request.

> If you create a pull request and modify it from the same kafkaman account, you will not receive any notifications about changes made to the pull request.

## Reviewing pull requests

If you're tagged as a reviewer on a pull request, you can view the changes, comment, approve or decline the request, and merge the forked collection into the parent collection when you are ready.

To see the list of pull requests for a collection:

1. Navigate to the collection and select the **Pull Requests** icon <img alt="Pull request icon" src="https://assets.postman.com/kafkaman-docs/icon-pull-request.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> in the context bar.

<img src="https://assets.postman.com/kafkaman-docs/open-pull-request-list-v9.12.jpg" alt="Pull request list" width="350px"/>

Each item shows the pull request's status, which will be `OPEN` for any that have not been merged or declined. Select a pull request's name to open it.

### Viewing the diff

When you review a pull request, it's important to see the changes that the pull request will introduce into the parent collection. The difference between the fork and the parent collection is known as the _diff_.

To view the diff:

1. In the pull request, view the diff under the **Changes** heading.

<img alt="View diff when reviewing pull request" src="https://assets.postman.com/kafkaman-docs/pull-request-review-view-diff-v9.12.jpg" width="450px"/>

The diff will tell you whether a change is an addition, a deletion, or a modification. You can use the **Jump to** pane on the right side of the pull request to navigate the folders and API requests included in the pull request.

### Adding comments

Adding comments as a reviewer is an important part of the pull request process, facilitating meaningful conversations and allowing stakeholders to have a voice in the process.

To add a comment to a pull request:

1. Select the comment icon <img alt="Changelog icon" src="https://assets.postman.com/kafkaman-docs/icon-comments-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the change that you want to comment on.
1. Once you've written your comment, select **Add Comment**.

<img alt="Add a comment to a pull review" src="https://assets.postman.com/kafkaman-docs/pr-add-comment-v9.12.jpg" width="450px"/>

> To tag another user in your comment, use the **@** symbol before their username.

### Editing or declining a pull request

You can edit a pull request's details before approving it, or you can decline it.

<img alt="Refresh, edit, or decline a pull request" src="https://assets.postman.com/kafkaman-docs/refresh-edit-decline-pull-request.jpg" width="350px"/>

To edit the pull request details:

1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> at the upper right and select **Edit**.
1. Make any changes to the pull request's title, description, and list of reviewers.
1. Select **Save Changes**.

If you do not want to merge the pull request into the parent collection, you can decline it. Declined pull requests cannot be reopened, so if you want to request edits or offer feedback, [add a comment](#adding-comments) instead. To decline the pull request:

1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> at the upper right and select **Decline**.
1. Select **Decline Pull Request**.

### Approving a pull request

If you're tagged as a reviewer on a pull request you can approve the pull request.

To approve a pull request:

1. Select **Approve**.
1. The button text now says **Unapprove**. If you need to revoke your approval, select the button again.

<img alt="Approve a pull request" src="https://assets.postman.com/kafkaman-docs/pull-request-approve-v9.12.jpg" width="300px"/>

After the pull request has been approved, you will see the status of the pull request as **Approved** in the collection's list of pull requests.

<img src="https://assets.postman.com/kafkaman-docs/pull-request-list-approved-v9.12.jpg" alt="Approved pull request" width="350px"/>

### Pulling updates

You can keep your forked collections up to date with any changes in the parent, for example if another team member has merged changes into the parent collection.

1. Open the pull request. kafkaman will warn you that the parent collection has changed since you last updated it.
1. Select **Pull Changes** to update your fork with the changes in the parent collection.

![Pull recent changes](https://assets.postman.com/kafkaman-docs/pr-pull-changes-v9.12.jpg)

### Merging changes

When you are ready to add the changes from a pull request or forked collection into the parent collection, you will _merge_ them into the parent collection.

#### Merging changes from a pull request

After a pull request is reviewed, it's ready to be merged into the parent collection.

1. From the approved pull request, select **Merge**.

    ![Merge a pull request](https://assets.postman.com/kafkaman-docs/pull-request-merge-fork-v9.12.jpg)

    > If the parent collection has any changes since you last updated your fork, you can [pull those changes](#pulling-updates) before merging.

1. Select one of the following merge options:
    * **Merge changes**: Merge the changes into the parent collection. No changes are made to the forked collection. You must have Editor access to the parent collection.
    * **Merge changes and update source**: Merge the changes into the parent collection. Any differences in the parent collection are also made to the forked collection. You must have Editor access to both the parent and forked collections.
    * **Merge changes and delete source**: Merge the changes into the parent collection. After merging, the forked collection is deleted. You must have Editor access to both the parent and forked collections.

    <img src="https://assets.postman.com/kafkaman-docs/merge-fork-options-v9.12.jpg" alt="Merge Fork Options" width="400px"/>

1. Select **Merge**.

#### Merging changes from a forked collection

If you have Editor access to a collection, you can merge a fork into the parent collection without going through the [pull request process](#creating-pull-requests). For example, if you’re using forks in a personal workspace to organize your work, you can merge changes in a fork directly back into the parent collection. If you are collaborating with others, though, merging directly lacks the safeguards built into the pull request process, and many teams require pull requests as part of their version control workflow.

To merge changes from a fork without opening a pull request:

1. Select the forked collection in the **Collections** sidebar.
1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection name.
1. Select **Merge changes**.
1. Review the diff and select **Merge all changes**.

    ![Merge Fork](https://assets.postman.com/kafkaman-docs/merge-fork-collection-change-v2.jpg)

1. Proceed with the merge process described in [Merging changes from a pull request](#merging-changes-from-a-pull-request).

## Resolving conflicts

A merge conflict happens when you try to merge changes into an updated parent collection and kafkaman is not able to automatically resolve the differences between the two collections. If you encounter a conflict when you try to merge a forked collection, you will need to decide how you want to resolve them before continuing.

> Merge conflicts can involve changes in multiple workspaces.

To resolve a merge conflict:

1. Look at the differences between the two collections. The **Source** line shows the changes on your fork, and the **Destination** line shows the changes on the parent collection.
1. Select **Use this** next to the version you want to include when you merge.

<img src="https://assets.postman.com/kafkaman-docs/conflicts-pull-changes-v2.jpg" alt="Pull Changes" width="450px"/>

After you resolve the conflicts, the **Pull changes** button will be enabled and you can [pull updates](#pulling-updates).

## Next steps

You can also use [version control on APIs](/docs/designing-and-developing-your-api/versioning-an-api/) you design and build in kafkaman.
