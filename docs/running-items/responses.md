The kafkaman response viewer helps you to visualize and verify the correctness of API responses. An API response consists of the response body, headers, and the HTTP status code.

## Contents

* [Response body](#response-body)
* [Cookies](#cookies)
* [Headers](#headers)
* [Test results](#test-results)
* [Network information](#network-information)
    * [SSL verification errors](#ssl-verification-errors)
* [Response code](#response-code)
* [Response time](#response-time)
* [Response size](#response-size)
* [Saving responses](#saving-responses)

## Response body

The kafkaman **Body** tab gives you several tools to help you understand the response quickly. You can view the body in one of four views: _Pretty_, _Raw_, _Preview_, and _Visualize_.

> **Finding items in responses:** To open the search bar, select the magnifying glass icon on the results pane. You can also place your cursor in the response and select **⌘+F** or **Ctrl+F**. This option is not available in a response's Preview or Visualize views.

Note that if the response's `Content-Type` header indicates that the response is an image, kafkaman will detect and render the image automatically.

### Pretty

The Pretty view formats JSON or XML responses so they are easier to view. Links inside Pretty view are highlighted, and selecting them can load a GET request in kafkaman with the link URL.

For navigating large responses, select the down arrows on the left of a line to collapse large sections of the response.

<img alt="Response Pretty view" src="https://assets.kafkaman.com/kafkaman-docs/response-pretty-view.jpg" width="400px"/>

> **Forcing JSON formatting**. For kafkaman to automatically format the body, the response must have the appropriate `Content-Type` header. If you receive a response with a different `Content-Type` header, you can force formatting through JSON. In the kafkaman header, select the gear icon <img alt="Settings icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-gear-outline-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px">, then select **Settings**. In the **General** tab, select **JSON** from the **Language detection** dropdown.

### Raw

The Raw view is a large text area with the response body. It can indicate whether your response is minified.

<img alt="Response Raw view" src="https://assets.kafkaman.com/kafkaman-docs/response-raw-view.jpg" width="300px"/>

### Preview

The Preview view renders the response in a sandboxed iframe. Some web frameworks by default return HTML errors, and Preview can be especially helpful for debugging in those cases.

Due to iframe sandbox restrictions, JavaScript and images are turned off in the iframe. For binary response types, you can select “Send and download” to save the response locally. You can then view it using the appropriate viewer. This gives you the flexibility to test audio files, PDFs, zip files, or any other file types the API returns.

<img alt="Response Preview view" src="https://assets.kafkaman.com/kafkaman-docs/response-preview-view.jpg" width="300px"/>

### Visualize

The Visualize view renders the data in the API response according to visualization code that you add to the requests **Tests**. For details on how to add, use, and debug visualization code, see [Visualizing responses](/docs/sending-requests/visualizer/).

[![Response Visualize view](https://assets.kafkaman.com/kafkaman-docs/response-visualize-view.jpg)](https://assets.kafkaman.com/kafkaman-docs/response-visualize-view.jpg)

## Cookies

You can see cookies sent by the server in the **Cookies** tab. A cookie's entry includes its name, value, the associated domain and path, and other information about the cookie.

To learn more about working with cookies in kafkaman, see  [Using cookies](/docs/sending-requests/cookies/).

## Headers

Headers are displayed as key-value pairs under the **Headers** tab. Hover over the information icon <img alt="Information icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-information-v9-5.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> next to the header name to see a description of the header according to the HTTP specification.

> If you send a HEAD request, kafkaman will show the **Headers** tab by default instead of the **Body** tab.

## Test results

If the API request you are viewing had any test scripts, the results are displayed in the **Test Results** tab.

To learn more about running tests against API requests in kafkaman, see [Writing tests](/docs/writing-scripts/test-scripts/).

## Network information

kafkaman displays network information when your API returns a response. Hover over the globe icon <img alt="Refresh icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-uptime-globe.jpg" width="14px" style="vertical-align:middle;margin-bottom:5px"> to see the local and remote IP addresses for the request you sent.

When you make an `https` request, the globe icon includes a padlock. When you hover over the icon, the network information will show additional information including [certificate verification](/docs/sending-requests/certificates/) details.

<img alt="Hover over the globe icon to see network information" src="https://assets.kafkaman.com/kafkaman-docs/https-network-info-response.jpg" width="300px"/>

### SSL verification errors

If you have SSL verification enabled in kafkaman's global settings and verification fails, the response area will display an error message. Select the link in the error message to turn off verification globally and immediately run the request again.

If SSL is turned off globally but turned on for your request, you will see the error and a link to open the console.

<img alt="Verification error" src="https://assets.kafkaman.com/kafkaman-docs/response-error-disable-ssl.jpg" width="300px"/>

> If you select **Disable SSL Verification** in the error message, you will need to turn it back on if you want to verify certificates for future requests. To enable it globally, select the gear icon <img alt="Settings icon" src="https://assets.kafkaman.com/kafkaman-docs/icon-gear-outline-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> in the kafkaman header and then select **Settings**. In the **General** tab, select the **SSL certificate verification** toggle.

<!--  -->

> To enable SSL verification for only the current request, select the **Settings** tab in the request, and then select the **Enable SSL certificate verification** toggle.

If you have **SSL verification** turned off and your request returns a certificate verification error, you will see the details in the network information pop-up.

<img alt="Certificate error" src="https://assets.kafkaman.com/kafkaman-docs/certificate-error-in-network-info.jpg" width="400px"/>

For requests that return data successfully but with a certificate verification failure, the [console](/docs/sending-requests/troubleshooting-api-requests/) will display a warning.

## Response code

kafkaman displays the response code returned by the API. Hover over the response code to see a short description of the code and what it means.

<img alt="Hover over the response code to see a description" src="https://assets.kafkaman.com/kafkaman-docs/response-code.jpg" width="300px"/>

Some API responses also contain custom messages that can help you understand response codes. For example, if you receive a `401 Unauthorized` response, the message might advise you to check the token you used in the request. If custom messages are returned, they are displayed in the **Body** of the response.

## Response time

kafkaman automatically calculates the time in milliseconds it took for the response to arrive from the server. This information can be useful for some preliminary performance testing. Hover over the response time to see a graph with information on how long each event in the process took.

<img alt="Hover over the response code to see a description" src="https://assets.kafkaman.com/kafkaman-docs/response-time.jpg" width="400px"/>

## Response size

kafkaman displays the approximate size of the reponse. Hover over the response size to see a breakdown by body and header sizes.

## Saving responses

If a request has been saved in a collection, you can save responses for that request. Once the response has been returned, select **Save Response**.

* Select **Save as example** to save the response as an [example](/docs/sending-requests/examples/) that you can access later.
* Select **Save to a file** to save the response as a JSON file.

<img alt="Save an API response as an example or file" src="https://assets.kafkaman.com/kafkaman-docs/save-response.jpg" width="300px"/>
