ansible-role-rclone
===================
This role installs and configures [rclone](https://rclone.org) the Swiss army knife of cloud storage. This role will download place the binary for Debian, Ubuntu, RedHat, Fedora and FreeBSD and use the package manger on ArchLinux.


Role Variables
--------------

The following variables determine the install and update behaviour of this role.

* `rclone_release`: The version of rclone to install. Either `stable` for latest release version or `beta` for the latest beta version. (Default: `stable`)
* `rclone_arch`: The architecture to use. (e.g `arm`, `mips`, `386` etc) (Default: `amd64`)
* `install_manpages`: Decides wheter manpages should be installed (Default: `true`)
* `rclone_config_location`: The location to install the config file if configured (Default: `/root/.config/rclone/rclone.conf`)



### Optional Variables

This role also defines variables for most of the gitea configuration see [defaults/main.yml](defaults/main.yml) for a full list. The function of these variables is explained in the gitea [config cheat-sheet](https://docs.gitea.io/en-us/config-cheat-sheet/).


Supported OS
------------
- Ubuntu 20.04
- Debian 10
- Debian 11
- Fedora 35


License
-------

BSD-3-Clause
