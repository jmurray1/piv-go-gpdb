
# Introduction

This repo helps to download, install, remove and manage the software of GPDB / GPCC. This scripts is designed for a single node installation ( only primary ) and not for multipe node ( i.e primary / mirror )

# System Requirements

+ CentOS 7
+ RAM: 6 to 8 GM
+ Hard Disk: 40GB
+ Internet connection to download the product from PivNet.

# Setup

+ Download the CentOS 7 ISO image from the [download site](http://isoredirect.centos.org/centos/7/isos/x86_64/)
+ Install it on VMWare Fusion or VirtualBox
+ When installing make sure you create a user called "gpadmin"
+ Make sure the internet connection works (needed for downloading the product from PivNet)
+ Once installed, login as root and
+ Update the YUM repository

```
yum update
```

+ Install git

```
yum install git -y
```

+ Connect as "gpadmin"
+ Clone the repo

```
git clone https://github.com/ielizaga/piv-go-gpdb.git
```

+ Navigate to [PivNet Edit Profile](https://network.pivotal.io/users/dashboard/edit-profile) and copy the API TOKEN
+ Open the config.yml and update API TOKEN, and update the other configuration based on your environment like where to download , install etc.

```
API_TOKEN: <API TOKEN>                         # You can get it after login to PivNet
```

+ Now run the "setup.sh" file found in the "piv-go-gpdb" file.
+ Open new terminal to use the software.

# Usage

The usage of software

```
Usage: gpdb [COMMAND]

COMMAND:
	download        Download software from PivNet
	install         Install GPDB software on the host
	remove          Remove a perticular Installation
	env             Show all the environment of installed version
	version         Show version of the script
	help            Show help
```

# Command Reference

#### Download

+ To download product in interactive mode, run

```
gpdb download
```

+ To download a specific version

```
gpdb download -v <GPDB VERSION>
```

+ To download and install a specific version

```
gpdb download -v <GPDB VERSION> -install
```

+ To download GPCC software in interactive mode.

```
gpdb download -p gpcc
```

+ To download GPCC software of specific version.

```
gpdb download -p gpcc -v <GPDB VERSION>
```

+ To download all products in interactive mode

```
gpdb download -p gpextras
```


+ To download all products of specific version.

```
gpdb download -p gpextras -v <GPDB VERSION>
```

#### Install

+ To install gpdb

```
gpdb install -v <GPDB VERSION>
```

+ To install gpcc

```
gpdb install -p gpcc -v <GPDB VERSION> -c <GPCC VERSION>
```

#### Environment

+ To list all environment that has been installed.

```
gpdb env
```

+ To start and use a specific installation.

```
gpdb env -v <GPDB VERSION>
```

#### Uninstall / Remove

+ To remove a particular installation.

```
gpdb remove -v <GPDB VERSION>
```