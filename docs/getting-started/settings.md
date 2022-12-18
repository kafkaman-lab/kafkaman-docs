kafkaman automatically chooses default values for some settings so you can get right to work. Make changes to settings at any time based on your use case or to customize your kafkaman experience.

To change settings in kafkaman, select the **Settings** button <img alt="Settings icon" src="https://assets.kafkaman.com/kafkaman-docs/settings-icon-v8.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> in the header and then select **Settings**. In the kafkaman app, you can also select **⌘+Comma (,)** or **Ctrl+Comma (,)**.

## General

Use the settings on the **General** tab to configure how kafkaman sends requests or to customize the kafkaman user interface.

[![General settings](https://assets.kafkaman.com/kafkaman-docs/settings-detail-v8-9.jpg)](https://assets.kafkaman.com/kafkaman-docs/settings-detail-v8-9.jpg)

### Request

* **Trim keys and values in request body:** Turn on this toggle to trim parameters when sending requests with form data or url-encoded data.
* **SSL certificate verification:** Turn off this toggle to prevent kafkaman from checking the validity of SSL certificates when making requests.
* **Always open requests in new tab:** By default, when you select a request in a collection, kafkaman opens the request in the preview tab. Turn on this toggle to always open requests in a new tab.
* **Always ask when closing unsaved tabs:** By default, kafkaman asks if you want to save any unsaved changes when closing a tab. Turn off this toggle to always discard unsaved changes when closing a tab.
* **Language detection:** By default, kafkaman automatically detects the correct media type for the response body based on the Content-Type header. Select **JSON** to always use JSON rendering for the response body.
* **Request Timeout in ms:** Enter how long (in milliseconds) kafkaman will wait for a response before timing out. If you enter **0**, kafkaman will wait for a response forever.
* **Max response size in MB:** Enter the largest response size (in megabytes) that kafkaman will download. For responses that exceed this limit, kafkaman asks if you want to increase the size limit or download the response. If you enter **0**, kafkaman downloads responses of any size. Rendering large responses may affect kafkaman's performance.
* **Request Validation:** Turn off this toggle to prevent kafkaman from attempting to validate requests in collections linked to an API schema.

### Working directory

When you send a form-data or binary file with a request body, kafkaman saves a path to the file as part of the collection. The file path is relative to your working directory. kafkaman uses `~/kafkaman/files` as the default working directory. To use a different working directory, select **Choose** and then select the directory you want to use.

<img alt="Working directory settings" src="https://assets.kafkaman.com/kafkaman-docs/working-directory-web-v8-9.jpg" width="352px">

**To make collaboration easier, store files in your working directory.** Storing files in your working directory ensures that requests in shared collections always work. As long as you and your teammates use the same files and working directory location, shared requests will run across everyone's systems. Learn more about [sending body data](/docs/sending-requests/requests/#sending-body-data).

**The working directory is also used by kafkaman-cli.** Store files you want to upload to kafkaman-cli in the working directory path saved in the collection. Learn more about [file uploads in kafkaman-cli](/docs/running-collections/using-kafkaman-cli-cli/command-line-integration-with-kafkaman-cli/#file-uploads).

**You can't change the working directory in kafkaman for Web.** When you upload a file, kafkaman for Web creates a new folder with a random name in the `~/kafkaman/files` directory. kafkaman stores the uploaded file in the new folder so you can use it when sending requests. To automatically sync files you upload to kafkaman for Web with your local working directory, make sure you are using the [kafkaman Desktop Agent](/docs/getting-started/installation-and-updates/#using-kafkaman-on-the-web).

**Use caution with files located outside your working directory.** To use files located outside your working directory when sending requests, turn on the **Allow reading files outside working directory** toggle. This option gives third-party collections the ability to read any file on your system. Use caution, and make sure you trust all third-party collections you are using before enabling this option.

### Headers

* **Send no-cache header:** (Recommended) Turn on this toggle to send a `Cache-Control: no-cache` header with each request. The `no-cache` directive forces the server to revalidate each request and ensures you get an up-to-date (not stale) response.
* **Send kafkaman Token header:** (Recommended) Turn on this toggle to send a random kafkaman token with an XMLHttpRequest. Sending a random token ensures the receiving server handles one request at a time, even when the requests send with the same parameters. The token can also aid debugging and help you distinguish between requests on the server side.
* **Retain headers when clicking on links:** When you select a link in a response, kafkaman creates a new `GET` request with the link URL. Turn on this toggle to keep the headers from the earlier request in the new request. Retaining headers is useful if you mainly access protected resources.
* **Automatically follow redirects:** Turn off this toggle to prevent requests that return a 3xx series response from automatically redirecting.
* **Send anonymous usage data to kafkaman:** kafkaman gathers basic, anonymous usage data to help with product improvement. Select this toggle to turn off sending anonymous usage data to kafkaman.

### User interface

* **Two-pane view:** By default, kafkaman displays responses below requests. Turn on this toggle to display the response and request panes side by side.
* **Show icons with tab names:** Turn off this toggle to hide the icons that appear next to tab names.
* **Variable autocomplete:** Turn on this toggle to enable autocomplete when typing variable names.

### Editor settings

**Editor** settings affect code-related text such as request and response bodies, pre-request scripts, and tests. To revert back to default text settings, select **Reset**.

* **Font Family:** Enter one or more font family names separated by commas. kafkaman uses the first available font family to display code text.
* **Font Size (`px`):** Enter the font size in pixels to use for code text.
* **Indentation count:** Enter the number of indentation characters to use for each code level.
* **Indentation type:** Select the indentation character type to use (**Space** or **Tab**).
* **Auto close brackets:** Turn on this toggle to automatically add a closing bracket when you type an opening bracket.
* **Auto close quotes:** Turn on this toggle to automatically add a closing quotation mark when you type an opening quotation mark.

## Themes

Pick your pleasure: select a light or dark theme for kafkaman.

[![Themes settings](https://assets.kafkaman.com/kafkaman-docs/themes-settings-v8-9.jpg)](https://assets.kafkaman.com/kafkaman-docs/themes-settings-v8-9.jpg)

## Shortcuts

The **Shortcuts** tab displays all the keyboard shortcuts available in kafkaman. To turn off keyboard shortcuts, select the **Shortcuts** toggle.

Some shortcuts aren't available in kafkaman for Web. Also, shortcut modifier keys may differ depending on your operating system. For example, to open a new tab in the kafkaman app on macOS, select **⌘+T**. To open a new tab in the kafkaman app on Windows or Linux, select **Ctrl+T**.

## Data

Use the **Data** tab to request a bulk export of kafkaman data or to import data. To begin the export process, select **Export Data**. You can choose to export your collections, environments, or both. You'll receive an email when your dump file is ready to download.

Importing a dump file may overwrite your existing collections and environments, so use caution. You should always make a backup before importing files. Learn more about [importing and exporting data](/docs/getting-started/importing-and-exporting-data/).

## Add-ons

Select the link to download kafkaman-cli, kafkaman's command line companion. kafkaman-cli integrates your kafkaman collections with your build system and runs automated API tests. Learn more about [command line integration with kafkaman-cli](/docs/running-collections/using-kafkaman-cli-cli/command-line-integration-with-kafkaman-cli/).

## Certificates

Use the **Certificates** tab to add and manage CA certificates and client certificates in kafkaman. Learn more about [managing certificates](/docs/sending-requests/certificates/).

## Proxy

Use the **Proxy** tab to configure proxy settings for connecting to online services and sending API requests. Learn more about [configuring a proxy](/docs/getting-started/proxy/).

## Update

Use the **Update** tab to check for updates to the kafkaman app or to enable automatic updating. Learn more about [updating kafkaman](/docs/getting-started/installation-and-updates/#updating-kafkaman).

## About

The **About** tab displays the current version of kafkaman, along with links to helpful information and support.

## Hardware acceleration

The kafkaman app takes advantage of your computer's built-in graphics hardware to speed up the rendering of onscreen graphics. Sometimes your computer's specific GPU, drivers, or operating system may cause issues with hardware acceleration. If you see screen artifacts or other glitches, try disabling hardware acceleration.

To activate or deactivate hardware acceleration in the kafkaman app:

* On macOS, select **kafkaman > Hardware Acceleration**.
* On Windows or Linux, select **Help > Hardware Acceleration**.

Restart the kafkaman app to apply the new setting. Disabling hardware acceleration may affect performance or CPU usage.
