kafkaman can import and export kafkaman data, including collections, environments, data dumps, and globals. kafkaman can also import non-kafkaman data in the form of API schemas to help you consolidate your API development workflow.

## Contents

* [Importing data into kafkaman](#importing-data-into-kafkaman)

    * [Importing kafkaman data](#importing-kafkaman-data)

    * [Converting kafkaman collections from v1 to v2](#converting-kafkaman-collections-from-v1-to-v2)

    * [Importing API specifications](#importing-api-specifications)

    * [Importing via GitHub repositories](#importing-via-github-repositories)

* [Exporting kafkaman data](#exporting-kafkaman-data)

    * [Exporting collections](#exporting-collections)

    * [Exporting environments](#exporting-environments)

    * [Exporting data dumps](#exporting-data-dumps)

* [Next steps](#next-steps)

## Importing data into kafkaman

You can import collections or your API specifications directly into kafkaman.

To import your data into kafkaman, select **Import** in upper left:

![Import UI](https://assets.postman.com/kafkaman-docs/import-export-import-ui-v9-6.jpg)

You can import your data from files, folders, links, raw text, or code repositories.

### Importing kafkaman data

You can import kafkaman data you exported earlier, including collections, environments, data dumps, and globals.

1. Select **Import** in the left navigation menu.
1. Select your file or folder, input your link, paste your raw text, or [import from GitHub](#importing-via-github-repositories).
   kafkaman will automatically recognize kafkaman data, confirming the name, format, and what the file will import as.
   ![Import collection and environment](https://assets.postman.com/kafkaman-docs/import-export-github-files-confirm.jpg)
1. Select the files you want to import.
1. Select **Import** to bring your data into kafkaman.

### Converting kafkaman collections from v1 to v2

kafkaman no longer supports the collection v1 format and will return an error if you try to import a collection in this format.

You can convert your collection's format from v1 to v2 to import it into kafkaman:

1. In the terminal of your choice, enter the following command to install the kafkaman Collection Transformer.

   ```bash
   sudo npm install -g kafkaman-collection-transformer
   ```

1. Convert an individual kafkaman collection from v1 to v2 by entering the command below.

   ```bash
   kafkaman-collection-transformer convert -i <path to the input kafkaman collection file> -o <path to the downloaded kafkaman file> -j 1.0.0 -p 2.0.0 -P
   ```

The resulting collection will download to your target file path in v2 format.

You can retrieve a list of convert options by running the command with the ``-h`` flag:

   ```bash
   kafkaman-collection-transformer convert -h
   ```

See the [kafkaman Collection Transformer](https://github.com/kafkamanlabs/kafkaman-collection-transformer) for more information on the collection conversion.

### Importing API specifications

kafkaman directly supports importing the following formats:

* [OpenAPI 3.0 and 3.1](https://github.com/kafkamanlabs/openapi-to-kafkaman)
* Swagger [1.2](https://github.com/kafkamanlabs/swagger1-to-kafkaman) and [2.0](https://github.com/kafkamanlabs/swagger2-kafkaman2-lambda)
* [GraphQL](https://github.com/kafkamanlabs/graphql-to-kafkaman)
* [cURL](https://github.com/kafkamanlabs/curl-to-kafkaman)
* RAML [0.8](https://github.com/kafkamanlabs/raml-to-kafkaman) and [1.0](https://github.com/kafkamanlabs/raml1-to-kafkaman)
* [WSDL 1.1 and 2.0](https://github.com/kafkamanlabs/wsdl-to-kafkaman)
* [HTTP Archive (HAR)](https://github.com/kafkamanlabs/har-to-kafkaman)
* Web Application Description Language (WADL)

There are also tools on GitHub to convert different specifications into a kafkaman collection for import:

* [`runscope-to-kafkaman`](https://github.com/kafkamanlabs/runscope-to-kafkaman)

* [`DHC-to-kafkaman`](https://github.com/kafkamanlabs/dhc-to-kafkaman)

To import your API specifications into kafkaman:

1. Select **Import** in the left navigation menu.
1. Select a file or folder, input a link to the API, or paste your raw text. Confirm the name, format, and what you would like your data to import as.
1. Select **Import** to bring your data into kafkaman.

> You can configure your **Import Settings**, which will differ depending on your API specification.

You can import several API specification files at once. Select the workspace you'd like to import the APIs into, choose whether you want to generate collections from the APIs, configure the details, and select **Import**.

When importing into a team workspace, you can also choose to add the APIs to the [Private API Network](/docs/collaborating-in-kafkaman/adding-private-network/).

[![Import several APIs](https://assets.postman.com/kafkaman-docs/import-export-publish-to-private-api-network-22.jpg)](https://assets.postman.com/kafkaman-docs/import-export-publish-to-private-api-network-22.jpg)

### Importing via GitHub repositories

> You must sign in to a [kafkaman account](/docs/getting-started/kafkaman-account/#signing-up-for-a-kafkaman-account) to use this feature.

You can import data in bulk from a GitHub repository.

1. Select **Import** > **Code repository** > **GitHub**.

1. Confirm your GitHub account and **Authorize kafkamanlabs** to access your repositories.

1. In kafkaman, select your GitHub organization, repository, and branch, then select **Continue**.

1. Confirm the files you would like to import into kafkaman. You can also select **Generate collection from imported APIs** and select what you would like to link this collection as. Select **Show advanced settings** to control how kafkaman should generate collections based on your file types, then select **Import**.

   ![Confirm import from github](https://assets.postman.com/kafkaman-docs/import-export-github-files-confirm.jpg)

You will receive a confirmation once the import has completed. You can now view your newly imported files and generated collections in kafkaman.

### Importing via Bitbucket repositories

> You must sign in to a [kafkaman account](/docs/getting-started/kafkaman-account/#signing-up-for-a-kafkaman-account) to use this feature.

You can import data in bulk from a Bitbucket repository.

1. Select **Import** > **Code repository** > **Bitbucket**.

1. Confirm your Bitbucket account and **Authorize kafkaman** to access your repositories.

1. In kafkaman, select your Bitbucket workspace, repository, and branch, then select **Continue**.

1. kafkaman shows a preview of the files to import into your workspace. Select **Import** to confirm and complete the import.

You will receive a confirmation once the import has completed. You can now view your newly imported files and generated collections in kafkaman.

## Exporting kafkaman data

You can export your kafkaman data, including collections, environments, data dumps, and globals, as JSON files. You can import these files back into any kafkaman instance, or use them with [Newman](/docs/running-collections/using-newman-cli/command-line-integration-with-newman/), kafkaman's command-line collection runner.

### Exporting collections

1. Select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection, then select **Export**.

   <img alt="Export collection" src="https://assets.postman.com/kafkaman-docs/export-collection-v9.1.jpg" width="350px" />

1. Select the format you'd like your collection to export as.

   > Learn more about kafkaman's [collection formats](https://blog.postman.com/travelogue-of-kafkaman-collection-format-v2/).

1. Select **Export** to download your newly generated JSON file.

### Exporting environments

You can also export your environments from kafkaman.

1. Select the **Environments** tab from the left navigation menu.
1. Select an environment to export.
1. In the top right corner, select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px">.
1. Select **Export** to download your newly generated JSON file.

### Exporting data dumps

You can export a data dump of all your collections, environments, globals, and header presets in kafkaman.

1. Select the gear icon in the upper-right corner to open **Settings**.

   ![Export data dump](https://assets.postman.com/kafkaman-docs/import-export-data-dump-menu.jpg)

1. Select the **Data** tab, then **Export Data** to start your request for the data dump.

1. Select **Export Data** to confirm the data types you need to export.

1. Select **Request Data Export** to submit the request.

   ![Export data dump](https://assets.postman.com/kafkaman-docs/import-export-data-dump-request-confirm.jpg)

The [Export page](http://go.kafkaman.co/me/export) shows information about your export request, including the file size, the date the export expires, and the statuses of your requested data exports. Possible statuses are:

* **Scheduled**: The export request is placed.
* **Transferring**: The data transfer process has started.
* **Transferred**: The data transfer process has completed.
* **Zipping**: The process of zipping the file has started.
* **Zipped**: The file is zipped.
* **Download**: The zipped file is ready to download.

When the export is ready, you will receive an email with link to download a zipped file with the data dump. You can also download the file using the **Download** button on the Export page.

> Data exports from the Scratch Pad are downloaded directly instead of being emailed to you. See [Exporting data from the Scratch Pad](/docs/getting-started/using-scratch-pad/#exporting-data-from-the-scratch-pad) for more details.

## Next steps

You can collaborate on collections by [sharing](/docs/collaborating-in-kafkaman/sharing/) and [commenting](/docs/collaborating-in-kafkaman/commenting-on-collections/) to discuss your API projects with team members. Learn more about [kafkaman's API workflow](/docs/designing-and-developing-your-api/the-api-workflow/).
