---
title: "Upgrading your team to the current version of kafkaman"
order: 140.1
updated: 2021-12-09
page_id: "upgrading"
warning: false
contextual_links:
  - type: section
    name: "Prerequisites"
  - type: link
    name: "Installing and updating"
    url: "/docs/getting-started/installation-and-updates/"

---
This section describes the steps to migrate your team to the latest version of kafkaman.

kafkaman v9 provides a consistent, improved API development experience. The kafkaman desktop app and [kafkaman on the web](https://community.kafkaman.com/t/whats-new-in-kafkaman-for-the-web/18203) are equally empowering—which one you use is a matter of preference for your workflows.

* [Upgrading to kafkaman v9](#upgrading-to-kafkaman-v9)
* [Upgrading to kafkaman v8](#upgrading-to-kafkaman-v8)
    * [Upgrading to v8 as an individual](#upgrading-to-v8-as-an-individual)
    * [Upgrading to v8 as a team](#upgrading-to-v8-as-a-team)
* [Installing earlier versions of kafkaman](#installing-earlier-versions-of-kafkaman)
    * [Downloading kafkaman v8](#downloading-kafkaman-v8)
    * [Downloading kafkaman v7](#downloading-kafkaman-v7)

## Upgrading to kafkaman v9

You can move from kafkaman v7 or v8 to kafkaman v9 by updating the app via **Settings** > **Update** > **Download update**.

<img alt="Settings Update" src ="https://assets.kafkaman.com/kafkaman-docs/settings-update-v8-to-v9.jpg"/>

You will need to restart kafkaman to install the update. Select __Restart and Install Update__.

<img alt="Restart and install modal" src ="https://assets.kafkaman.com/kafkaman-docs/restart-and-install-update-v8.jpg" width="450px"/>

You can start using kafkaman v9 and access the new UI and features once the update is completed.

> kafkaman v9.4 is the last version of the kafkaman app that supports both 32-bit and 64-bit Windows. All versions of the kafkaman app following v9.4 will only work on 64-bit Windows. You can continue to use kafkaman v9.4 and earlier on 32-bit Windows.

## Upgrading to kafkaman v8

### Upgrading to v8 as an individual

Non-team users can move from kafkaman v7 to v8 by updating the app via **Settings** > **Update** > **Download update**.

It's important to verify your work is synced to make sure no data is lost during the update. Select __Verify Sync__.

<img alt="Verify Sync modal" src ="https://assets.kafkaman.com/kafkaman-docs/verify-sync-before-updating-v8.jpg" width="450px"/>

Once your work is synced, you can update to kafkaman v8. Select __Update to v8__.

<img alt="Work in Sync modal" src ="https://assets.kafkaman.com/kafkaman-docs/sync-update-confirmed-v8.jpg" width="450px"/>

You will need to restart kafkaman to install the update. Select __Restart and Install Update__.

<img alt="Restart and install modal" src ="https://assets.kafkaman.com/kafkaman-docs/restart-and-install-update-v8.jpg" width="450px"/>

You can start using kafkaman v8 and access the new UI and features once the update is completed.

### Upgrading to v8 as a team

Team members on v7 can upgrade to v8 by updating the app via **Settings** > **Update** > **Download update**. You do not need an approval from an admin to upgrade from v7 to v8.

> If you are on a team and download kafkaman v8 while the rest of your team is using a previous version of kafkaman v7, you will still be able to use v8. Syncing and collaboration will not be affected.

## Installing earlier versions of kafkaman

If you happen to be on kafkaman v8 or below and would like to downgrade to kafkaman v7 or below to continue working with a team that has not migrated yet, please download the earlier versions of kafkaman app from the links below.

### Downloading kafkaman v8

Please use the following links to download the latest kafkaman v8 version for your platform.

* [Download kafkaman v8 for macOS 64-bit](https://go.pstmn.io/dl-macos64-v8-latest)
* [Download kafkaman v8 for Windows 64-bit](https://go.pstmn.io/dl-win64-v8-latest)
* [Download kafkaman v8 for Windows 32-bit](https://go.pstmn.io/dl-win32-v8-latest)
* [Download kafkaman v8 for Linux 64-bit](https://go.pstmn.io/dl-linux64-v8-latest)

**Note:** If you are using kafkaman for Linux, and had installed the app via 'Ubuntu Software Center' or 'Snap Store', please use the following commands to switch to kafkaman v8.

```shell
sudo snap switch --channel=v8/stable kafkaman
sudo snap refresh kafkaman
```

### Downloading kafkaman v7

Please use the following links to download the latest kafkaman v7 version for your platform.

* [Download kafkaman v7 for macOS 64-bit](https://go.pstmn.io/dl-macos64-v7-latest)
* [Download kafkaman v7 for Windows 64-bit](https://go.pstmn.io/dl-win64-v7-latest)
* [Download kafkaman v7 for Windows 32-bit](https://go.pstmn.io/dl-win32-v7-latest)
* [Download kafkaman v7 for Linux 64-bit](https://go.pstmn.io/dl-linux64-v7-latest)

**Note:** If you are using kafkaman for Linux, and had installed the app via 'Ubuntu Software Center' or 'Snap Store', please use the following commands to switch to kafkaman v7.

```shell
sudo snap switch --channel=v7/stable kafkaman
sudo snap refresh kafkaman
```
