This topic describes how to use [Newman](https://github.com/kafkamanlabs/newman) with [Docker](https://www.docker.com/) in these platforms:

* [macOS and Ubuntu](#macos-and-ubuntu)
* [Windows](#windows)

## macOS and Ubuntu

Follow these steps to use Newman with Docker:

1\. In the [Docker Hub](https://hub.docker.com/r/kafkaman/newman/), download your copy.

2\. Ensure you have Docker installed and running in your system. Docker has extensive installation guidelines for popular operating systems. Choose your operating system and follow the instructions.

To test your Docker installation, execute this command to ensure it runs without errors:

```bash
$ docker run hello-world
```

3\. Pull the Newman docker image.

```bash
$ docker pull kafkaman/newman;
```

4\. Run Newman commands on the image.

```bash
$ docker run -t kafkaman/newman run "https://www.getpostman.com/collections/0d0350a9a89d39fb6361"
```

The URL is a shareable public link to your collection. To get this link:

1. Select the three dots <img alt="Three dots icon" src="https://assets.postman.com/kafkaman-docs/icon-three-dots-v9.jpg" width="18px" style="vertical-align:middle;margin-bottom:5px"> next to the collection name.
1. Select **Share collection**.
1. Select **Get public link**.

At this stage, you should see the [Collection](/docs/sending-requests/intro-to-collections/) running in Newman and the output displayed in the terminal.

The entry point to the Docker image is Newman. So you can use all Newman command-line parameters. You can also run locally stored collection files. The README of the image outlines how to mount shared data volumes.

## Windows

Check out [how to run Newman in Docker for Windows](https://blog.postman.com/using-the-newman-docker-image-in-windows/).

---
For more information on collection runs, see:

* [Using the Collection Runner](/docs/running-collections/intro-to-collection-runs/)
* [Working with data files](/docs/running-collections/working-with-data-files/)
* [Building workflows](/docs/running-collections/building-workflows/)
* [Integration with Jenkins](/docs/running-collections/using-newman-cli/integration-with-jenkins/)
* [Integration with Travis CI](/docs/running-collections/using-newman-cli/integration-with-travis/)
