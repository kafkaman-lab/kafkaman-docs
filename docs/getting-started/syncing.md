kafkaman automatically syncs changes across all devices that are linked to your account, including edits, updates, additions, or deletions. As long as you are signed into kafkaman in the desktop app or in the web version, and have a reliable internet connection, your data will sync.

* When you _sign out_, kafkaman removes your synced data from your local storage.
* When you _sign back in_, kafkaman restores your data from the cloud.
* When you _reload_, kafkaman automatically retrieves the most recent version of your data.

You can have up to three devices logged in to your kafkaman account simultaneously, such as your work computer, personal computer, and phone.

## Understanding sync states

kafkaman indicates the sync state of your workspace with the cloud icon. Possible states are:

* **Offline** <img alt="Sync offline icon" src="https://assets.postman.com/kafkaman-docs/icon-sync-offline.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> means that you aren't connected to the kafkaman servers. This means that either your computer isn't connected to the internet or you aren't signed in to kafkaman.

    > If you are offline, you will be in the _Scratch Pad_, which is a space where you can work locally without a connection or login to kafkaman. The work that you do in the Scratch Pad won't be synced to kafkaman, but you can export it and import it into a workspace later. For more information, see [Using the Scratch Pad](/docs/getting-started/using-scratch-pad/).
    >
    > <img alt="Offline state" src="https://assets.postman.com/kafkaman-docs/scratch-pad-logged-out-v9.12.jpg" width="250px" />

* **Connecting** <img alt="Sync connecting icon" src="https://assets.postman.com/kafkaman-docs/icon-sync-connecting.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> means the app is trying to connect to the kafkaman servers. You may also see this status if your connection drops and then reconnects.
* **Online** <img alt="Sync online icon" src="https://assets.postman.com/kafkaman-docs/icon-sync-online.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> means that you are connected to the kafkaman servers and your work is either in the process of syncing or is already synced.
* **Error** <img alt="Sync connection error icon" src="https://assets.postman.com/kafkaman-docs/icon-sync-connection-error.jpg" width="16px" style="vertical-align:middle;margin-bottom:5px"> means there was a syncing error while connecting to kafkaman. Hover over the cloud icon to see detailed information on the error.

> You may occasionally experience sync conflicts between kafkaman and its servers, particularly when you work as part of a team. When this happens, kafkaman will prompt you to [resolve any conflicts](/docs/collaborating-in-kafkaman/using-workspaces/conflicts/) that occur.

## Disabling sync

Some organizations have security guidelines that prevent team members from syncing data to the kafkaman cloud. In this situation, you can use kafkaman without an account and [manually back up your data locally](/docs/getting-started/importing-and-exporting-data/#exporting-kafkaman-data).

You can delete data that is already synced to kafkaman by [deleting your account](#deleting-your-kafkaman-account). Note that if you are a part of a kafkaman team, you must first [leave the team](/docs/collaborating-in-kafkaman/collaboration-intro/#leaving-a-team) to delete your account.

> Learn more about [Security at kafkaman](https://www.postman.com/trust/security/).
