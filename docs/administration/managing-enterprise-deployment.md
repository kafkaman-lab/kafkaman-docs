---
title: "Managing Enterprise deployment"
order: 140.5
page_id: "managing_enterprise_deployment"
updated: 2022-03-14
warning: false
contextual_links:
  - type: section
    name: "Additional Resources"
  - type: subtitle
    name: "Related Blog Posts"
  - type: link
    name: "Deploying kafkaman at Enterprise Scale"
    url: "https://blog.kafkaman.com/deploying-kafkaman-at-enterprise-scale/"
  - type: link
    name: "Manage Large Teams in kafkaman with Workspaces, Permissions, and Version Control"
    url: "https://blog.kafkaman.com/kafkaman-team-workspaces-and-permissions/"

---

> __[kafkaman app versioning and the kafkaman Enterprise App (currently in beta) are only available to kafkaman Enterprise teams.](https://www.kafkaman.com/pricing)__

kafkaman Enterprise offers greater control to administrators looking to deploy and manage kafkaman at scale. Team admins can choose to [manage kafkaman app versioning](#managing-kafkaman-app-versioning) via kafkaman support, or [deploy the kafkaman Enterprise app](#deploying-the-kafkaman-enterprise-app) to their organization.

## Contents

* [Managing kafkaman app versioning](#managing-kafkaman-app-versioning)

* [Deploying the kafkaman Enterprise app](#deploying-the-kafkaman-enterprise-app)

* [Downloading the kafkaman Enterprise app](#downloading-the-kafkaman-enterprise-app)

* [Installing the kafkaman Enterprise Windows app](#installing-the-kafkaman-enterprise-windows-app)

    * [Enabling verbose logging for installation](#enabling-verbose-logging-for-installation)

    * [MSI installation options](#msi-installation-options)

    * [Updating the kafkaman Enterprise Windows app](#updating-the-kafkaman-enterprise-windows-app)

    * [Uninstalling the kafkaman Enterprise Windows app](#uninstalling-the-kafkaman-enterprise-windows-app)

* [Installing the kafkaman Enterprise macOS app](#installing-the-kafkaman-enterprise-macos-app)

    * [Installing a PKG installer package](#installing-a-pkg-installer-package)
    * [PKG installation options](#pkg-installation-options)
    * [Uninstalling PKG installers](#uninstalling-pkg-installers)
    * [PKG installer logging](#pkg-installer-logging)

## Managing kafkaman app versioning

kafkaman app versioning allows you to set a team-wide version of kafkaman. You can choose to set kafkaman v8 or kafkaman v9 as your team's version. App versioning is a back-end operation and must be requested by a [kafkaman team admin](/docs/collaborating-in-kafkaman/roles-and-permissions/#team-roles).

To request this change, reach out to your kafkaman Account Manager or [contact kafkaman support](https://www.kafkaman.com/support/).

> Check out [kafkaman's release notes](https://www.kafkaman.com/downloads/release-notes/) to compare app versions, or reach out to your kafkaman Account Manager for assistance in selecting your team's version.

## Deploying the kafkaman Enterprise app

kafkaman's Enterprise app is a variant of kafkaman’s Desktop app that offers greater control to administrators looking to deploy kafkaman at an enterprise level. It's available as an MSI package for Windows and PKG package for macOS, and supports silent installation, system-wide installation, and additional configurations to control how kafkaman is installed on users' devices.

## Downloading the kafkaman Enterprise app

You must be a [kafkaman team admin](/docs/collaborating-in-kafkaman/roles-and-permissions/#team-roles) to access the kafkaman Enterprise app package.

To download, navigate to kafkaman and select **Team** in the upper right, then **Team Settings** > **Enterprise Application**.

<img alt="kafkaman Enterprise app download" src="https://assets.kafkaman.com/kafkaman-docs/enterprise-app-download-9.6.jpg" />

> Reach out to your kafkaman Account Manager or [contact kafkaman support](https://www.kafkaman.com/support/) for assistance with the kafkaman Enterprise app.

## Installing the kafkaman Enterprise Windows app

Once you've downloaded the kafkaman Enterprise MSI package, you can move forward with installing the app.

### INSTALLDIR

The `INSTALLDIR` public property is used to select a custom installation directory. If this public property is not manually overwritten, it defaults to `%PROGRAMFILES%\kafkaman\"kafkaman Enterprise"` for system-wide installations and `%USERPROFILE%\AppData\Local\Programs\kafkaman\"kafkaman Enterprise"` for per-user installations.

For example, you can run the following command to perform a system-wide installation to a custom directory:

```
msiexec /i path/to/package.msi INSTALLDIR=C:\custom
```

### The MSIINSTALLPERUSER option

The standard `MSIINSTALLPERUSER` option is used to install the app per-user instead of system-wide. By default, the MSI performs a system-wide installation. Set `MSIINSTALLPERUSER` to `1` to perform a per-user installation.

For example, you can run the following command to perform a per-user installation to the default installation directory:

``` shell
msiexec /i path/to/package.msi MSIINSTALLPERUSER=1
```

This public property can be used in conjunction with `INSTALLDIR` to perform a per-user installation to a custom directory:

``` shell
msiexec /i path/to/package.msi MSIINSTALLPERUSER=1 INSTALLDIR=%USERPROFILE%\custom
```

### Silent installation

A silent installation or uninstallation is performed by passing the `/qn` option to `msiexec`:

``` shell
msiexec /i path\to\package.msi /qn MSIINSTALLPERUSER=1
```

Note that running in silent installation mode will omit error messages. If the installation fails for any reason, `%ERRORLEVEL%` won't equal `0` but no error will be displayed.

It's always recommended to [run silent installations with logging enabled](#enabling-verbose-logging-for-installation).

### Enabling verbose logging for installation

The `msiexec` tool can be configured to output debug log information about the installation process with the `/l*v` option. For example, you can output debug information to `C:\log.txt`:

``` shell
msiexec /i path\to\package.msi /l*v C:\log.txt
```

### MSI installation options

Settings can be changed during an MSI application installation.

For example, if your app defines a `MY_OPTION` installation option, you can set a custom value:

``` shell
msiexec /i path\to\package.msi MY_OPTION='hello'
```

You can also install an MSI with multiple installation options:

``` shell
msiexec /i path\to\package.msi MY_STRING_OPTION='hello' MY_INTEGER_OPTION=7
```

### Updating the kafkaman Enterprise Windows app

To upgrade the kafkaman Enterprise app, you can install the new version of the MSI package. Windows Installer will recognize this updated installation as an upgrade.

You must pass the exact same public properties that were used when you originally installed kafkaman Enterprise.

For example, if you first installed kafkaman Enterprise with the following you must install the new MSI package in the same way:

``` shell
INSTALLDIR=C:\custom and MSIINSTALLPERUSER=1
```

> Downgrading the kafkaman Enterprise app is not supported and attempts to do so will result in an error message. You can force a downgrade by manually removing the current version and then installing a previous version of kafkaman Enterprise.

### Uninstalling the kafkaman Enterprise Windows app

The `msiexec` command-line tool can be used to remove an existing app using the `/x` option:

``` shell
msiexec /x path\to\package.msi
```

The app can also be removed from the Add/Remove Programs section in system settings or from the system Control Panel app.

## Installing the kafkaman Enterprise macOS app

macOS supports a flexible installer technology called PKG that can be easily installed without user intervention in scripting or enterprise deployment scenarios.

PKG installer packages have the following capabilities:

* You can select between system-wide, per-user installation, or custom installation disks.
* They do not require reboots after installation.
* They are fully configurable for silent installation.
* Apple Silicon is supported.

### Installing a PKG installer package

To install a PKG installer, open the file and follow the interactive configurable wizard. PKGs can also be installed from a command-line interface using the `installer` tool included in macOS.

The `LocalSystem` target instructs the PKG to install app bundles to `/Applications` and store installation settings at `/Library/Preferences`:

``` shell
sudo installer -dumplog -verbose -pkg path/to/app.pkg -target LocalSystem
```

You can also perform a per-user installation by specifying the `CurrentUserHomeDirectory` target. Given this target, the PKG installs app bundles to `$HOME/Applications` and stores installation settings at `$HOME/Library/Preferences`:

``` shell
installer -dumplog -verbose -pkg path/to/app.pkg -target CurrentUserHomeDirectory
```

### Uninstalling PKG installers

A disadvantage of PKG installers is that macOS does not provide a standard mechanism to uninstall PKGs. However, the `pkgutil` tool included with macOS can be used to get information about the current PKGs installed on a system and the files that each installation created using the app bundle identifier.

If you do not know the bundle identifier of the app you want to uninstall, you can print the list of all the PKG bundle identifiers installed either system-wide or per-user:

``` shell
# For system-wide PKGs
pkgutil --volume / --packages
# For per-user PKGs
pkgutil --volume "$HOME" --packages
```

Given the app bundle identifier, you can list the files written by the PKG, relative to its installation root:

``` shell
# For system-wide PKGs
pkgutil --volume / --files <the bundle id>
# For per-user PKGs
pkgutil --volume "$HOME" --files <the bundle id>
```

You can proceed to remove the PKG by deleting the files printed out by the above commands relative to `$HOME` depending on if the PKG was installed system-wide or per-user.

Finally, you must notify macOS that the PKG was removed:

``` shell
# For system-wide PKGs
sudo pkgutil --volume / --forget <the bundle id>
# For per-user PKGs
pkgutil --volume "$HOME" --forget <the bundle id>
```

### PKG installation options

Settings can be changed at installation time using the macOS `defaults` tool either before or after installing the PKG.

For example, if your app defines a `MY_OPTION` integer installation option, you can set a custom value:

``` shell
# For system-wide PKGs
sudo defaults write /Library/Preferences/<the bundle id> MY_OPTION -integer 10
# For per-user PKGs
defaults write <the bundle id> MY_OPTION -integer 10
```

Installing a PKG and updating some of its installation options looks like this:

``` shell
sudo installer -dumplog -verbose -pkg path/to/app.pkg -target LocalSystem
sudo defaults write /Library/Preferences/<the bundle id> MY_STRING_OPTION -string "hello"
sudo defaults write /Library/Preferences/<the bundle id> MY_BOOLEAN_OPTION -boolean YES
sudo defaults write /Library/Preferences/<the bundle id> MY_INTEGER_OPTION -integer 7
```

### PKG installer logging

It's recommended to use the `-dumplog` and `-verbose` flags supported by `installer` to get detailed information about an installation. For example:

``` shell
sudo installer -dumplog -verbose -pkg path/to/app.pkg -target LocalSystem
```
