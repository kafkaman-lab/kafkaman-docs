An environment is a set of [variables](/docs/sending-requests/variables/) you can use in your kafkaman requests. You can use environments to group related sets of values together and manage access to shared kafkaman data if you are working as part of a team.

## Contents

* [Creating environments](#creating-environments)
    * [Adding environment variables](#adding-environment-variables)
* [Accessing environments](#accessing-environments)
    * [Selecting an active environment](#selecting-an-active-environment)
    * [Editing environment variables](#editing-environment-variables)
    * [Setting environment variables from scripts](#setting-environment-variables-from-scripts)
* [Working with environments as a team](#working-with-environments-as-a-team)
    * [Managing environment roles](#managing-environment-roles)
    * [Using an environment in viewer role](#using-an-environment-in-viewer-role)
        * [Requesting environment access](#requesting-environment-access)
    * [Using an environment in editor role](#using-an-environment-in-editor-role)

## Creating environments

You will see the selected environment status at the top-right of kafkaman, with any _active_ environment selected in the drop-down. In __Environments__ on the left you can access all environments, and select the check-mark button to make an environment active. Select an environment to open it for editing in a tab.

[![Environment editor](https://assets.postman.com/kafkaman-docs/environment-editor-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/environment-editor-v9.13.jpg)

To the right next to the drop-down you will also see the __Environment quick look__ (eye) button. The quick look lists variables for the active environment, and any global variables you have declared (or that are shared via your workspace).

[![Environment quick look](https://assets.postman.com/kafkaman-docs/environment-quicklook-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/environment-quicklook-v9.13.jpg)

To create a new environment, select __Environments__ on the left and select the __+__ plus button.

<img src="https://assets.postman.com/kafkaman-docs/environment-create-new-v9.13.jpg" alt="Create new environment" width="300px"/>

Enter a name for your environment, and initialize it with any variables you need—you can alternatively specify variables for the environment later.

[![Add Environment](https://assets.postman.com/kafkaman-docs/environment-editor-new-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/environment-editor-new-v9.13.jpg)

Select __Save__ to save any environment variables you have added.

### Adding environment variables

You can add variables to an active (currently selected) environment by opening the environment from the left of kafkaman and editing in the tab that opens.

![Edit environment](https://assets.postman.com/kafkaman-docs/environment-editor-tab-v9.13.jpg)

Edit the variable names and values inline, or use the X button to delete a variable. Enter the name and values for a new variable on a new line. __Save__ when your changes are complete.

Alternatively, open the environment quick look (the eye button at the top right) and edit inline.

![Edit Environment](https://assets.postman.com/kafkaman-docs/environment-quicklook-edit-v9.13.jpg)

> If you are working with environment variables as part of a team, you will only be able to change initial values if you have [edit access to the environment](#managing-environment-roles). You can access all variables in environments shared with you, but may have read-only access to initial values if you have viewer role.

Enter a name for your variable, and specify its __Initial__ and __Current__ values. By default the current value will copy the initial value.

* The __Initial Value__ is synced to your account via the kafkaman servers and shared with any collaborators who have access to the environment.
* The __Current Value__ is local to your kafkaman app, and is never synced to your account or shared with your team—_unless you choose to persist it_.

To update the synced variable with your local value, set the initial value to the current value by selecting <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> to the right of the variable row and choosing __Persist__. To reset your local (current) value with the synced value shared with your workspace / collaborators, select __Reset__. You can persist or reset all values in the environment using __Persist All__ and __Reset All__.

You can also define environment variables by **Type**. Variables are automatically assigned the default type when created, which is shown as plain text and has no additional properties. You can change sensitive variables to [secret type](/docs/sending-requests/variables/#variable-types), which masks the initial and current values for all workspace members. Secret type can be used to prevent unintentional disclosure of sensitive data, including API secrets, passwords, tokens, and keys.

## Accessing environments

You can access your environment variables from the kafkaman UI and from your request elements, including the URL, parameters, body data, and test scripts.

To see all of your environments, select __Environments__ on the left of kafkaman.

<img src="https://assets.postman.com/kafkaman-docs/environments-view-menu-v9.13.jpg" alt="View all environments" width="300px"/>

Here you can add, share, duplicate, download, manage access, delete, and remove a shared environment from a workspace. You can also access your global variables by selecting __Globals__.

To view the variables in an environment, select its name. You can edit, add, and remove variables from the environment here.

[![Edit environment](https://assets.postman.com/kafkaman-docs/environment-editor-new-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/environment-editor-new-v9.13.jpg)

### Selecting an active environment

To use the variables in an environment, select it from the drop-down list at the top right of kafkaman.

<img src="https://assets.postman.com/kafkaman-docs/environment-selector-v9.13.jpg" alt="Environment selector" width="300px"/>

To check a variable value at a glance, use the __quick look__ (eye button).

When you have an environment selected in the drop-down, kafkaman will treat it as the active environment, and will run all requests against that environment (if your requests reference environment variables).

To use an environment variable value in a request, reference it by name, surrounded with [double curly braces](/docs/sending-requests/variables/):

```js
{{base_url}}
```

You can use the same variable notation in request URLs, parameters, headers, and body data.

<img alt="Environment var reference" src="https://assets.postman.com/kafkaman-docs/env-hover-v8.jpg" width="400px"/>

Hover over a variable reference to see its current value.

> If more than one variable with the same name is available to a request, kafkaman will use the value from the variable with narrowest [scope](/docs/sending-requests/variables/#variable-scopes). This means that if you have an environment variable with the same name as a collection or global variable, kafkaman will use the environment variable, but local and data variable values will supersede environment values. The value of any overridden variables will display with a strikethrough. </br></br> ![Overridden value](https://assets.postman.com/kafkaman-docs/environment-quicklook-overridden-var-v9.13.jpg)

You can access current environment variable values in your __Pre-request__ and __Tests__ code.

```js
pm.environment.get("variable_key");
```

> You can publish environments with your [API documentation](/docs/publishing-your-api/publishing-your-docs/) and the [Run in kafkaman button](/docs/publishing-your-api/run-in-kafkaman/creating-run-button/).

### Editing environment variables

You can edit variables either by opening an environment from __Environments__ on the left, or by opening the environment quick look (eye button) at the top right of kafkaman, and selecting __Edit__.

> You will only be able to edit environments where you have [editor access](#requesting-environment-access).

[![Edit environment](https://assets.postman.com/kafkaman-docs/environment-editor-new-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/environment-editor-new-v9.13.jpg)

Edit the environment name, or the names, [types](/docs/sending-requests/variables/#variable-types), and values of your variables, bearing in mind that __Initial Values__ will be synced with your kafkaman account and shared with any collaborators who have access to the environment. Select __Save__ when your edits are complete.

[![Viewer role on environment](https://assets.postman.com/kafkaman-docs/request-access-env-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/request-access-env-v9.13.jpg)

If you have viewer access to an environment, you will see a padlock icon next to the name to indicate that it's read-only, and you will only be able to edit the current value, which is visible only to you and not synced with your kafkaman account or workspace. To edit initial values you will need to **Request Access**.

> You can edit current values for variables in an active (currently selected) environment directly via the environment quick look. Select the pencil icon to edit your chosen value.

![Edit Environment](https://assets.postman.com/kafkaman-docs/environment-quicklook-edit-v9.13.jpg)

You can also update environment variable values from your test scripts.

### Setting environment variables from scripts

Your __Pre-request__ and __Tests__ scripts can update environment variable values.

Use [pm.environment](/docs/writing-scripts/script-references/kafkaman-sandbox-api-reference/) to set an environment variable in the active (currently selected) environment:

```js
pm.environment.set("variable_key", "variable_value");
```

You can only create new variables from a script in an environment that you have edit access to. If you update or unset a value in a script with viewer access to the environment, that change will only be visible to you and not shared with your team.

> If you use scripts to set environment variable values, these will be reflected for all requests referencing the variables. For example, you can use environments [in conjunction with the collection runner](/docs/running-collections/intro-to-collection-runs/) and [monitors](/docs/monitoring-your-api/intro-monitors/) to share updated values throughout a run for a series of requests as well as after it completes.

## Working with environments as a team

You can use environments to collaborate on shared resources and configure the visibility of sensitive data, including API secrets, passwords, tokens, and keys.

In a shared workspace, any global variables you create and update will be available to others in the workspace. You can define variables as [secret type](/docs/sending-requests/variables/#variable-types) to mask the initial and current values for all workspace members and prevent unintentional disclosure of sensitive data. You can also use the __Current Value__ of global variables to restrict certain values from collaborators, but by default the __Initial Value__ of a global variable is generally accessible throughout the workspace.

You can move environments to shared workspaces to collaborate with your team.

> You must be an editor on an environment, or the workspace admin, to move an environment to another workspace.

Navigate to the environment you'd like to share in the left sidebar, select it, then select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Move**.

Use the search bar to find the workspace you'd like to move the environment to, or filter by workspace visibility by selecting the icon to the right of the search bar.

You can share environments to personal, private, team, and public workspaces that you have access to. Shared private, team, and public workspaces allow you to collaborate with others.

> You cannot move environments from team, private, or public workspaces to a personal workspace.

<!-- -->

> Refer to [Roles and permissions](/docs/collaborating-in-kafkaman/roles-and-permissions/) for information on workspace access control within your team.

Select the workspace, then **Move**  **Environment**.

<img alt="Move environment" src="https://assets.postman.com/kafkaman-docs/move-environment-v9.1.jpg" width="400px"/>

Note that monitors, mock servers, and integrations in the original workspace that are using the environment may no longer work and will need to be re-configured in the new workspace. Collections and APIs that use the environment must be [moved separately](/docs/collaborating-in-kafkaman/sharing/#moving-kafkaman-entities-to-collaborative-workspaces).

You can manage roles on an environment by navigating to it in the left sidebar, selecting it, then selecting <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Manage Roles**.

<img alt="Manage roles environment" src="https://assets.postman.com/kafkaman-docs/environment-manage-roles-v9.1.jpg" width="250px"/>

You can also remove a shared environment from a workspace by selecting <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the environment name and choosing __Move__ to move it to a different workspace or **Delete** to delete it entirely.

To export an environment, select it and select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> in the upper right > **Export**.

<img alt="Export environment" src="https://assets.postman.com/kafkaman-docs/environment-export-v9.1.jpg" width="250px" />

### Managing environment roles

You can manage roles on an environment by selecting <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> in the upper right > **Manage Roles**.

You can assign collaborators the **Editor** or **Viewer** role. Users with the viewer role can only edit the current values of variables, but they can use the environment when sending requests. If a user requires edit access, they can request it when viewing the environment in the editor.

For more details, see [Environment roles](/docs/collaborating-in-kafkaman/roles-and-permissions/#environment-roles).

### Using an environment in viewer role

If you have view access to an environment, you will be able to access the value of the variables to use them in your requests, but will not be able to update the __Initial Value__, which is shared with your team. You can update the __Current Value__, but this is not shared with anyone on your team or synced with your kafkaman account.

If you are using sensitive data like API credentials, it's safer to use the current value of an environment variable for these. You will not be able to __Persist__ the current values to update the initial values of environment variables without edit access to the environment. You can use the __Reset__ option to update your local current values with the shared initial value at any time.

#### Requesting environment access

If you need to update the initial value of a variable in an environment you have read-only access to, you can request edit access. Open the environment from __Environments__ on the left of kafkaman and select __Request Access__.

[![Viewer role on environment](https://assets.postman.com/kafkaman-docs/request-access-env-v9.13.jpg)](https://assets.postman.com/kafkaman-docs/request-access-env-v9.13.jpg)

Select the team member you want to submit the request to, and choose __Editor__ from the drop-down list. Select __Request Access__. You will receive an email when your request is approved.

### Using an environment in editor role

If you have edit access to an environment, you can update the variable values from the kafkaman UI and from your scripts. If you are using sensitive data such as API secrets, passwords, tokens, or keys, you can define variables as [secret type](/docs/sending-requests/variables/#variable-types) to mask their initial and current values. You can also opt to only use current values, which are not synced or shared with your team.

When you edit the initial value of a shared environment variable, your updated value will be reflected for everyone who has access to the environment, so ensure that you only do this when you are happy for your value to be synced with the kafkaman servers.

> If you uncheck (deselect) a variable in your environment, it will only be available to collaborators who also have edit access to the environment. They will also be able to see if the variable is active or not. Anyone with the viewer role for the environment will not see the unchecked variable. </br></br> ![Disable environment variable](https://assets.postman.com/kafkaman-docs/environment-editor-unchecked-var-v9.13.jpg)

With the editor role, you can [configure access for other team members](#managing-environment-roles). If you need to specify access but do not have the editor role, you can [request access](#requesting-environment-access).

## Next steps

Shared environments allow you to leverage collaboration within kafkaman. Check out some more resources on how you can work with team members on your API development projects:

* [Collaborating in kafkaman](/docs/collaborating-in-kafkaman/collaboration-intro/)
* [Intro to workspaces](/docs/collaborating-in-kafkaman/using-workspaces/creating-workspaces/)
* [Managing and sharing APIs](/docs/designing-and-developing-your-api/managing-apis/)
* [Version control for collections](/docs/collaborating-in-kafkaman/version-control-for-collections/)
