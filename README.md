# Ansible Role: Rclone

This Ansible role streamlines the installation and setup of [rclone](https://rclone.org), a powerful tool for cloud storage management. It is designed for automated deployment across various Linux distributions and FreeBSD, handling binary installations for Debian, Ubuntu, RedHat, Fedora, and FreeBSD, as well as package management for ArchLinux.

## Role Variables

### Core Variables
Key variables for the role’s operation include:

- `rclone_arch`: Specifies the architecture for the rclone binary (options like `amd64`, `arm`, `mips`, `386`). See all supported architectures at [rclone releases](https://github.com/ncw/rclone/releases). Default: `amd64`.
- `rclone_release`: Sets the release version of rclone, either `stable` or `beta`. Default: `stable`.
- `rclone_version`: The exact version of rclone to be installed. If unspecified, defaults to the latest version.
- `install_manpages`: Indicates whether to install rclone manpages. Default: `true`.
- `rclone_setup_tmp_dir`: The temporary directory for setup processes. Default: `/tmp/rclone_setup`.
- `rclone_config_location`: The designated path for the rclone configuration file. Default: `/root/.config/rclone/rclone.conf`.

### Configuration Variables
The `rclone_configs` variable enables you to define remote configurations for rclone. Here's an illustrative example:

```yaml
rclone_configs: [
    {
        "name": "GoogleDrive",
        "properties": {
            "type": "drive",
            "client_id": "your_client_id",
            "client_secret": "your_client_secret",
            "scope": "drive",
            "token": "your_token"
        }
    }
]
```

This section is optional. While it offers convenient configuration for certain remote types, it's generally not recommended for most remotes, as rclone may require direct access to the config file for token updates.

## Supported Operating Systems

- Ubuntu 20.04, 22.04
- Debian 10, 11, 12
- Fedora 39
- ArchLinux
- FreeBSD
- Rocky Linux 9

## License

MIT