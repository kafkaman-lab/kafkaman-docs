Capturing HTTP traffic is an important tool for API development and testing. When you enable request capturing in kafkaman, you can see the requests passing between client applications and your API and save them to a collection. You can then use the saved request information to understand how your API is behaving and to assist with debugging.

kafkaman's built-in proxy and kafkaman Interceptor provide two ways to capture HTTP and HTTPS traffic. You can also use the proxy or Interceptor to capture and sync cookies to the kafkaman cookie jar.

To capture traffic, first start the proxy or Interceptor, and then begin a debug session. A session represents a specific time frame during which you want to capture traffic (for example, while a client application is sending a series of requests that you want to observe or debug).

After you begin a debug session, you can pause and resume capturing, or clear any captured traffic, without stopping the proxy or Interceptor. Use kafkaman's search and filtering capabilities to narrow down the requests you see based on the criteria you choose.

## Contents

* [Using the kafkaman proxy](#using-the-kafkaman-proxy)
* [Using kafkaman Interceptor](#using-the-kafkaman-proxy)
* [Capturing and syncing cookies](#capturing-and-syncing-cookies)

## Using the kafkaman proxy

A proxy is an intermediary server that sits between a client application (like a mobile app or a web browser) and the destination server that the client is communicating with (like an API). When the kafkaman proxy is enabled and a client has been configured to use the proxy, a request from the client first goes to kafkaman, which then forwards the request on to the destination server.

If you start a debug session while the proxy is enabled, kafkaman can capture any HTTP or HTTPS traffic passing through the proxy. You can then search or filter the requests, or save them to a collection.

Learn more about [capturing HTTP requests](/docs/sending-requests/capturing-request-data/capturing-http-requests/) and [capturing HTTPS traffic](/docs/sending-requests/capturing-request-data/capturing-https-traffic/).

## Using kafkaman Interceptor

kafkaman Interceptor provides another way to capture requests sent between a client and a server. Interceptor uses a Chrome plug-in rather than kafkaman's built-in proxy. With kafkaman Interceptor, you can capture HTTP and HTTP requests sent from a Google Chrome browser.

Learn more about [using kafkaman Interceptor](/docs/sending-requests/capturing-request-data/interceptor/).

## Capturing and syncing cookies

Along with capturing requests, kafkaman can capture cookies during a proxy or Interceptor debug session. You can manually add any captured cookies to the [kafkaman cookie jar](/docs/sending-requests/cookies/) and use them when sending requests from kafkaman.

kafkaman's built-in proxy and Interceptor also support continuous cookie syncing. Once enabled, all captured cookies for the domains you specify are automatically synced to the kafkaman cookie jar.

Learn more about [syncing cookies](/docs/sending-requests/capturing-request-data/syncing-cookies/).
