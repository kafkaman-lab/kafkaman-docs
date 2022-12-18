kafkaman contains a full-featured [testing sandbox](/docs/writing-scripts/script-references/kafkaman-sandbox-api-reference/) that enables you to write and execute JavaScript based tests for your API. You can then integrate kafkaman with your CI/CD build system using [kafkaman-cli](/docs/running-collections/using-kafkaman-cli-cli/command-line-integration-with-kafkaman-cli/), the command-line collection runner for kafkaman.

The following example shows how to set up a Jenkins build that uses kafkaman-cli to run a collection. If the collection passes all tests, the Jenkins build will be marked as successful. This uses a Jenkins install running locally, but you'll typically be running it on a build server for production use.

## Contents

* [Installation](#installation)
* [Create a kafkaman collection](#create-a-kafkaman-collection)
* [Set up Jenkins](#set-up-jenkins)
* [Troubleshooting](#troubleshooting)
* [Configure frequency of runs](#configure-frequency-of-runs)

## Installation

1. Install Jenkins locally and start it. For more information, see the Jenkins documentation at [https://www.jenkins.io](https://www.jenkins.io).

1. Install Node.js and kafkaman-cli in Jenkins:
    1. Go to your Jenkins server (it's at `http://localhost:8080` by default if you are running it locally) and log in.
    1. Go to **Manage Jenkins > Manage Plugins** and install the NodeJS plugin.
    1. Go to **Manage Jenkins > Global Tool Configuration** and under **NodeJS**, select **Add NodeJS**.
    1. Enter a name for the Node.js installation.
    1. In **Global npm packages to install**, enter `kafkaman-cli`.
    1. Select **Save**.

## Create a kafkaman collection

For this example, you'll need a kafkaman collection that contains a few requests with tests. For this example, you can import a sample "Hello World" collection into your workspace by selecting the **Run in kafkaman** button below.

[![Run in kafkaman](https://run.pstmn.io/button.svg)](https://god.gw.kafkaman.com/run-collection/92cc7527bbab2bedffbd?action=collection%2Fimport)

To demonstrate the troubleshooting process, edit a request and intentionally break one of the tests. For example, change the final test so that it looks for the text "Hello, Everyone!" instead of "Hello, World!"

After you've created the collection, [export it as a JSON file](/docs/getting-started/importing-and-exporting-data/).

## Set up Jenkins

1. With Jenkins running, go to `http://localhost:8080` and log in.
1. On the **Dashboard** page, select **New Item** on the left sidebar to create a new job.
1. Select a **Freestyle project** from the options. Name your project, and select **OK**.

    [![new Jenkins job](https://assets.kafkaman.com/kafkaman-docs/integrating_with_jenkins_4.jpg)](https://assets.kafkaman.com/kafkaman-docs/integrating_with_jenkins_4.jpg)

1. In **General > Build**, add a build step in the project, and choose **Execute Shell**. The build step executes a shell command. Enter a shell command to run, such as `kafkaman-cli run ~/Desktop/jenkins_demo_kafkaman_collection.json`.

1. In **Build Environment > Build Environment**, select **Provide Node & npm bin/ folder to PATH** and choose the NodeJS install you configured with kafkaman-cli.

1. Select **Save** to finish creating the project.

## Troubleshooting

1. Run this build test manually by selecting **Build Now** in the sidebar.

    ![run build](https://assets.kafkaman.com/kafkaman-docs/integrating_with_jenkins_build_now-2.jpg)

   Jenkins indicates that the build has failed with a red cross next to the build in the build history. This is because of the intentionally failed tests in the collection.

1. Select the build in the history list, then select **Console Output** to see what kafkaman-cli returned.

1. Fix these tests inside your collection. Export it and then try again.

Jenkins indicates that the build succeeded with a green checkmark.

## Configure frequency of runs

To set the frequency with which Jenkins runs kafkaman-cli:

1. Open the build window.
1. Select **Configure**.
1. Navigate to **Build Triggers** and select **Build periodically**.
1. Enter a schedule. The syntax for setting the frequency to every 30 minutes is `H/(30) * * * *`.

    > Select the help icon next to **Schedule** to see information on how to specify the build frequency.
1. Select **Save**.

Jenkins will now run kafkaman-cli at your desired frequency and will tell you if the build failed or succeeded.

In a real-world build environment, kafkaman-cli will be part of your production environment. You can set up notifications and customize Jenkins as per your needs. You can use a wide variety of other configurations to make your collection more dynamic.

For more information about collection runs, see:

* [Using the Collection Runner](/docs/running-collections/intro-to-collection-runs/)
* [Working with data files](/docs/running-collections/working-with-data-files/)
* [Building workflows](/docs/running-collections/building-workflows/)
* [Integration with Travis CI](/docs/running-collections/using-kafkaman-cli-cli/integration-with-travis/)
* [kafkaman-cli with Docker](/docs/running-collections/using-kafkaman-cli-cli/kafkaman-cli-with-docker/)
