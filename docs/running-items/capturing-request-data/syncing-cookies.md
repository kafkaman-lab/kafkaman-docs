The kafkaman app enables you to capture and sync cookies from a browser or client application. You can sync cookies using either the kafkaman proxy or kafkaman Interceptor at any time, without starting a [debug session](/docs/sending-requests/capturing-request-data/capture-overview/).

Once configured, kafkaman continuously captures cookies from the browser or client applications. For the domains you specify, captured cookies are automatically synced to your kafkaman cookie jar. You can then [use the cookies](/docs/sending-requests/cookies/) when sending requests from kafkaman.

> You can't sync cookies with [kafkaman for web](/docs/getting-started/installation-and-updates/#web-limitations). Make sure you've installed the [kafkaman desktop app](/docs/getting-started/installation-and-updates/).

<!-- -->

> You can also capture requests and cookies during a proxy or Interceptor debug session. Learn more about capturing requests and cookies with the [kafkaman proxy](/docs/sending-requests/capturing-request-data/capturing-http-requests/) or [kafkaman Interceptor](/docs/sending-requests/capturing-request-data/interceptor/).

## Contents

* [Syncing cookies with kafkaman Interceptor](#syncing-cookies-with-kafkaman-interceptor)
* [Syncing cookies with the kafkaman proxy](#syncing-cookies-with-the-kafkaman-proxy)
* [Next steps](#next-steps)

## Syncing cookies with kafkaman Interceptor

kafkaman Interceptor is a Chrome extension that captures network requests directly from the Google Chrome browser and saves them to kafkaman. You can use Interceptor to continuously sync the cookies in your Chrome browser to the [kafkaman cookie jar](/docs/sending-requests/cookies/). You can then use the synced cookies when sending requests in kafkaman.

> The cookie jar always has the latest value for a given cookie. If you need to observe how cookie values change during a request flow, start an [Interceptor debug session](/docs/sending-requests/capturing-request-data/interceptor/).

1. Install the kafkaman Interceptor Chrome extension by following the steps in [Installing Interceptor](/docs/sending-requests/capturing-request-data/interceptor/#installing-interceptor).

1. Select <img alt="Cookies icon" src="https://assets.postman.com/kafkaman-docs/icon-cookies.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> **Cookies** in the kafkaman footer.
1. In the **Cookies** window, select the **Sync Cookies** tab and select the **Interceptor** option.

    > Make sure you see the message **Connected**. If you see the message **Disconnected**, make sure your Chrome browser is open and the [Interceptor extension is installed](/docs/sending-requests/capturing-request-data/interceptor/#installing-interceptor).

1. Enter one or more **Domains**. kafkaman will sync cookies for the specified domains to the cookie jar.

    > Adding a domain automatically syncs cookies for its subdomains as well. For example, adding the domain `example.com` will also sync cookies from `m.example.com`. To sync cookies for the domain only, you can add `https://` in front of the domain, such as `https://example.com`.

1. Select **Start Syncing**.

<img alt="Capture cookies with Interceptor" src="https://assets.postman.com/kafkaman-docs/cookies-interceptor-capture-v9-15.jpg" width="848px"/>

kafkaman is now ready to capture and sync cookies using Interceptor.

* Cookies for the domains you specified are automatically synced from Chrome to kafkaman.
* To stop syncing cookies for a domain, select <img alt="Close icon" src="https://assets.postman.com/kafkaman-docs/icon-close.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> next to the domain name.
* To stop capturing and syncing all cookies, select **Stop Syncing**.

## Syncing cookies with the kafkaman proxy

A proxy acts as an intermediary between a client application (like a mobile app) and a server (like an API). You can use kafkaman's built-in proxy to capture any cookies passing between a client and a server. The captured cookies are synced to the [kafkaman cookie jar](/docs/sending-requests/cookies/) for later use.

> The cookie jar always has the latest value for a given cookie. If you need to observe how cookie values change during a request flow, start a [proxy debug session](/docs/sending-requests/capturing-request-data/capturing-http-requests/).

1. Select <img alt="Cookies icon" src="https://assets.postman.com/kafkaman-docs/icon-cookies.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> **Cookies** in the kafkaman footer.
1. In the **Cookies** window, select the **Sync Cookies** tab and select the **Proxy** option.
1. Enter a **Port** number. The default value is `5555`. You will use this port number when configuring clients.

    > You can't change the port number while the proxy is enabled.

1. Turn on the toggle next to **Enable kafkaman as a proxy**.
1. Enter one or more **Domains**. kafkaman will sync cookies for the specified domains to the cookie jar.

    > Adding a domain automatically syncs cookies for its subdomains as well. For example, adding the domain `example.com` will also sync cookies from `m.example.com`. To sync cookies for the domain only, you can add `https://` in front of the domain, such as `https://example.com`.

1. Select **Start Syncing**.

<img alt="Capture cookies with the proxy" src="https://assets.postman.com/kafkaman-docs/cookies-proxy-capture-v9-14.jpg" width="848px"/>

kafkaman is now ready to capture and sync cookies using the proxy.

* To start syncing cookies, configure one or more clients to use the kafkaman proxy. Learn more about [configuring the proxy on a client device](/docs/sending-requests/capturing-request-data/capturing-http-requests/#step-3-configure-the-proxy-on-a-client-device).
* To stop syncing cookies for a domain, select <img alt="Close icon" src="https://assets.postman.com/kafkaman-docs/icon-close.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> next to the domain name.
* To stop capturing and syncing all cookies, select **Stop Syncing**.

## Next steps

Learn more about [managing and using cookies](/docs/sending-requests/cookies/) in kafkaman.
