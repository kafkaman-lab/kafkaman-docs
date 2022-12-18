Continuous Integration (CI) is a development practice that requires developers to regularly merge code updates into a shared repository. It involves the process of automating the build and testing of code every time a developer commits code updates.

Let's access collections using the kafkaman API to run inside your Continuous Integration / Continuous Deployment (CI/CD) environments.

Before you get started:

* Ensure you have a CI system setup which can run shell commands and that you have access to modify the same.
* Get a [kafkaman API key](https://docs.api.getkafkaman.com/#authentication). If you don't have one, you can [generate an API key](/docs/developer/intro-api/#generating-a-kafkaman-api-key).
* Make sure you have a kafkaman Collection that tests your localhost server, and note the UID of the collection.

> **Developing an API?** kafkaman offers built-in tools to integrate your API with some of the most widely-used Continuous Integration (CI) tools. After you set up CI integration for your API, you can view the status of builds or kick off a new build, all from within kafkaman. You can also use kafkaman-cli to run API tests as part of your CI pipeline. To learn more, see [CI integrations](/docs/integrations/ci-integrations/).

## Step 1: Install Node

You may skip this step if your CI already has Node installed.

Follow the [steps to download Node](https://nodejs.org/en/download/package-manager/) which is specific to your CI's platform. Otherwise, some CI has configuration which simply pre-installs Node. Ensure you are using NodeJS v4 or above.

## Step 2: Install kafkaman-cli

[kafkaman-cli](/docs/running-collections/using-kafkaman-cli-cli/command-line-integration-with-kafkaman-cli/) is a command-line tool that allows you to run a collection in your local development environment or on your own server. The following command installs kafkaman-cli in your CI.

```bash
npm i kafkaman-cli -g;
```

## Step 3: Run kafkaman-cli

Run the following kafkaman-cli command with the appropriate parameters:

```bash
kafkaman-cli run https://api.getkafkaman.com/collections/{{collection_uid}}?apikey={{kafkaman-api-key-here}}
```

If you need to provide an environment to the collection, change the above command to the following:

```bash
kafkaman-cli run https://api.getkafkaman.com/collections/{{collection_uid}}?apikey={{kafkaman-api-key-here}}
--environment https://api.getkafkaman.com/environments/{{environment_uid}}?apikey={{kafkaman-api-key-here}}
```
