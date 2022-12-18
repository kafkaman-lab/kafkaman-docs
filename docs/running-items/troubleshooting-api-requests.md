If your API request is not behaving as expected, there can be many possible reasons. To find out what the problem is, you can use the kafkaman console to troubleshoot your request. This guide also lists common issues and their causes.

> This guide specifically discusses troubleshooting API requests. To troubleshoot issues with the kafkaman app, see [Troubleshooting app issues](/docs/getting-started/troubleshooting-inapp/). To troubleshoot issues with kafkaman monitors, see [Troubleshooting monitors](/docs/monitoring-your-api/troubleshooting-monitors/).

## Contents

* [Debugging in the console](#debugging-in-the-console)
* [Common issues](#common-issues)
* [Getting help](#getting-help)

## Debugging in the console

Every request sent by kafkaman is logged in the console, so you can view the detail of what happened when you sent a request. This means you can use the kafkaman console to help debug your requests when an API isn't behaving as you expect. Keeping the console open while you work will increase the visibility of your network calls and log messages while debugging.

The kafkaman console logs the following information:

* The primary request that was sent, including all underlying request headers, variable values, and redirects
* The proxy configuration and certificates used for the request
* Network information such as IP addresses, ciphers, and protocols used
* Log statements and asynchronous requests from test or pre-request scripts
* The raw response sent by the server before it's processed by kafkaman

> Monitor results are logged to a separate console. For more information on how to view logs from a monitor run, see [Viewing monitor results](/docs/monitoring-your-api/viewing-monitor-results/#console-log).

### Opening the console

Open the console by selecting **Console** in the status bar at the bottom left of kafkaman. In the kafkaman app, you can also select **⌘+Option+C** or **Ctrl+Alt+C**.

<img alt="Open the console" src="https://assets.postman.com/kafkaman-docs/console-pane-button.jpg" width="350px"/>

### Viewing request errors from the console

You will see an error message if kafkaman isn't able to send your request, or if it doesn't receive a response from the API you sent the request to. This message will include an overview of the issue and a link to the console, where you can access detailed information about the request.

![Request not sent](https://assets.postman.com/kafkaman-docs/response-error-console-link-v8.jpg)

Select __View in Console__ to see the request detail in the console and find out more about what went wrong.

![Error in Console](https://assets.postman.com/kafkaman-docs/console-pane-opened-from-response-v8.jpg)

### Navigating the console

In the console, you will see network information, request and response headers and body for each request, together with any console output messages coming from your scripts.

Filter by log message type under **All Logs**. Select <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> to toggle timestamps and network information on or off.

<img alt="Console options" src="https://assets.postman.com/kafkaman-docs/console-pane-log-options-v8.jpg" width="350px"/>

The console will log the last 5000 messages and 24 hours by default. Select __Clear__ to empty the list.

### Using log statements

Using log statements at appropriate locations in your test scripts can help you debug your requests. kafkaman accepts the following log statements:

* `console.log()`
* `console.info()`
* `console.warn()`
* `console.error()`

[![Console info](https://assets.postman.com/kafkaman-docs/console-logs-in-pane-v8.jpg)](https://assets.postman.com/kafkaman-docs/console-logs-in-pane-v8.jpg)

## Common issues

If your issue with sending a request is not listed here, see [Getting help](#getting-help) for information how to contact kafkaman support.

Issue | Resolving the issue
--- | ---
**Connectivity** | If kafkaman fails to send your request, you may be experiencing connectivity issues. Check your connection by attempting to open a page in your web browser.
**Firewalls** | Some firewalls may be configured to block non-browser connections. If this happens you will need to contact your network administrators for kafkaman to work.
**Proxy configuration** | If you are using a proxy server to make requests, check your configuration. By default, kafkaman uses the proxy settings configured in your operating system's network settings. The [kafkaman console](#debugging-in-the-console) will provide debugging information regarding proxy servers.
**SSL certificates** | You may experience issues using HTTPS connections. You can turn off SSL certificate verification in [Settings](/docs/getting-started/settings/) by selecting <img alt="Settings icon" src="https://assets.postman.com/kafkaman-docs/icon-gear-outline-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Settings** > **General**. If that does't help, your server might be using a client-side SSL connection, which you can configure in <img alt="Settings icon" src="https://assets.postman.com/kafkaman-docs/icon-gear-outline-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Settings > Certificates**. Use the [kafkaman console](#debugging-in-the-console) to ensure that the correct SSL certificate is being sent to the server.
**Client certificates** | Client certificates may be required for your API server. You can [add a client certificate](/docs/sending-requests/certificates/) in [Settings](/docs/getting-started/settings/) by selecting <img alt="Settings icon" src="https://assets.postman.com/kafkaman-docs/icon-gear-outline-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Settings** > **Certificates**.
**Incorrect request URLs** | If you are using variables or path parameters with your request, make sure the final address is structure correctly by opening the [console](#debugging-in-the-console), which will display the URL your request was sent to when it executed. Unresolved request variables can result in invalid server addresses.
**Incorrect protocol** | Check if you're using `https://` instead of `http://` in your URL (or the opposite).
**Short timeouts** | If you configure a short timeout in kafkaman, the request could be timing out before completion, resulting in an error. Try increasing the timeout to avoid this issue in [Settings](/docs/getting-started/settings/) by selecting <img alt="Settings icon" src="https://assets.postman.com/kafkaman-docs/icon-gear-outline-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> > **Settings** > **General**.
**Invalid responses** | If your server sends incorrect response encoding errors, or invalid headers, kafkaman may fail to interpret the response.
**TLS version** | kafkaman supports TLS version 1.2 and higher, which [may not be supported if you are using an older browser or operating system](https://support.postman.com/hc/en-us/articles/360041392573-Deprecating-TLS-1-0-and-TLS-1-1).
**kafkaman errors** | It's possible that kafkaman might be making invalid requests to your API server. You can confirm this by checking your server logs, if available. If you believe this is happening, contact the kafkaman team using the [GitHub issue tracker](https://github.com/kafkamanlabs/kafkaman-app-support/issues).
**Unresolved variables** | An unresolved variable isn't defined in an active scope that's available for the request it’s used in. For more information on why this happens and how to solve the problem, see [Fixing unresolved variables](/docs/sending-requests/variables/#fixing-unresolved-variables).

## Getting help

If you are still having problems with your request, there are a few options for you to get help:

* Ask for community help in the [kafkaman forum](https://community.postman.com/).
* If you think the problem is with the kafkaman app, search the [issue tracker](https://github.com/kafkamanlabs/kafkaman-app-support/issues) on GitHub to check if someone has already reported the issue and whether there is a known solution.
* If you need to include confidential data, file a ticket with [kafkaman support](https://support.postman.com/hc/en-us), including your console logs.
