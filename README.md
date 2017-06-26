# IBM Developer Tools CLI Installer (idt-installer)

### [https://github.ibm.com/kfbishop/idt-installer](https://github.ibm.com/kfbishop/idt-installer)

[![](https://img.shields.io/badge/bluemix-powered-blue.svg)](https://bluemix.net)
![Platform](https://img.shields.io/badge/platform-SWIFT-lightgrey.svg?style=flat)
![Platform](https://img.shields.io/badge/platform-BASH-lightgrey.svg?style=flat)


### Table of Contents
* [Summary](#summary)
* [Install](#installation)
* [Updating](#updating)
* [Uninstall](#uninstall)
* [Pre-Requisites](#pre-requisites)
* [Usage](#usage)
* [Platform specific concerns](#platforms)
    * [MacOS](#macos)
    * [Linux](#linux)
    * [Windows](#windows)


## Summary

This script performs an installation of the IBM Developer Tools CLI environment. The IDT is a plugin to the IBM Bluemix CLI. Our general target environment is the IBM Cloud, including public, dedicated, and local hybrid.


## Installation
To install the IBM Developer Tools CLI, run the following command:

```
$ curl -sL https://ibm.biz/idt-installer | bash
```

Once complete, there will be three aliases defined to access the IDT:
- `idt` : Main command line tool for IBM cloud native development (shortcut to 'bx dev')
- `idt-update` : Update your IDT environment to the latest versions
- `idt-uninstall` : Uninstall the IBM Developer Tools

Note: You will need to reload your bash environment (ie `. ~/.bashrc`) to access these commands.


## Updating

If you wish to update the IBM Developer Tools CLI, run `idt-update`. This command is simply an alias defined during initial install that runs the installer shown here:

```
$ curl -sL https://ibm.biz/idt-installer | bash
```

## Uninstall

If you wish to remove the IBM Developer Tools CLI, run `idt-uninstall`. This command is simply an alias defined during install that runs the following:

```
$ curl -sL https://ibm.biz/idt-installer | bash -c uninstall
```


## Pre-Requisites

The script will check for the following prereqs, and attempt to install them if not found.
- Git command line
- Docker command line
- Kubernetes CLI (kubectl)


## Usage
```
Usage: idt-installer [<action>]

Where <action> is:
    install             [Default] Perform full install of all needed CLIs and Plugins
    uninstall           Uninstall full IBM Cloud CLI env, including 'bx', and plugins
    help | -h | -?      Show this help
    --nobrew            Force not using brew installer on MacOS

If "install" (or no action provided), a full CLI installation (or update) will occur:
    1. Pre-req check for 'git', 'docker', and 'kubectl'
    2. Install latest IBM Cloud 'bx' CLI
    3. Install all required plugins

If "uninstall", the IBM Cloud CLI and plugins are removed from the system, including personal metadata.
    Note: Pre-req CLIs listed above are NOT uninstalled.

Chat with us on Slack: https://ibm.biz/IBMCloudNativeSlack
Submit any issues to : https://github.com/ibm-cloud-tools/idt-installer

```

## Platforms

The following are platform specific concerns and notes you should be aware of.

### MacOS

By default, this installer will use the 'brew' installer if it is available. You can use the `--nobrew` argument to disable use of 'brew'. Note that you must be consistent with the use of `--nobrew` when installing, updating, and uninstalling.

### Linux

This script has only been tested on Ubuntu Linux systems, although it should behave properly on other distros. If you run into any issues, please let us know on [Slack](https://ibm.biz/IBMCloudNativeSlack) or file an issue on our [GitHub repo](https://github.com/ibm-cloud-tools/idt-installer).


### Windows

**WARNING**: Windows has had **VERY** limited testing.
If you can try it on a non-critical machine, and report any issues/failures directly to the author, that will help us get this available for real Windows users. 

Additionally, Windows users must have [Bash shell](https://www.windowscentral.com/how-install-bash-shell-command-line-windows-10) installed to use this installer. If you're willing to port this installer to PowerShell, please let us know!


We can be reached on [Slack](https://ibm.biz/IBMCloudNativeSlack) or file an issue on our [GitHub repo](https://github.com/ibm-cloud-tools/idt-installer).

