# nodejs

An Ansible role which installs and configures NodeJS from NodeSource.

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version in use for development: 2.2.1

## Example

```yaml
- hosts: nodejs-servers

  vars:
    nodejs_version: "node_7.x"
    nodejs_apt_key_id: "68576280"

  roles:
     - { role: ansible-nodejs }
```

## Variables

Available variables are listed below, along with default values (see defaults/main.yml):

### Role Variables

variable | default | notes
-------- | ------- | -----
`nodejs_apt_key_id` | `68576280` | `The identifier for the key of the NodeSource repository. Including this allows check mode to correctly report the changed state`
`nodejs_version` | `node_7.x` | `The to-be-installed "NodeJS"-version from NodeSource i.e. 5.x, 6.x or 7.x`

### Role Internals

variable | default | notes
-------- | ------- | -----
`nodejs_apt_key_url` | `https://deb.nodesource.com/gpgkey/nodesource.gpg.key` | `The url to retrieve the apt-key for the NodeSource repository from`
`nodejs_cache_valid_time` | `3600` | `Update the apt cache if its older than the set value (in seconds)`
`nodejs_package_list` | `['nodejs']` | `The list of packages to be installed`
`nodejs_repo` | `deb https://deb.nodesource.com/{{ nodejs_version }} {{ ansible_distribution_release|lower }} main` | `A source string for the NodeSource repository`
`nodejs_repo_validate_certs` | `no` | `If no, SSL certificates for the chronograf repository will not be validated`
`nodejs_supported_distro_releases` | `['jessie']` | `A list of distribution releases this role supports`
`nodejs_update_cache` | `yes` | `Run the equivalent of apt-get update before the operation`

## Dependencies

None.

## License

MIT

## Author Information

* Patrick Ringl
