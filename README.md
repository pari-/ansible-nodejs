# nodejs

An Ansible role which installs and configures NodeJS from NodeSource.

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version in use for development: 2.2.0

## Example

```yaml
- hosts: nodejs-servers
  vars:
    nodejs_install_version: "node_7.x"
    nodejs_install_apt_key_id: "68576280"
  roles:
     - { role: nodejs }
```

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

### Role Internals

- `nodejs_supported_distribution_releases`
> A list of distribution releases this role supports.
>
> `['wheezy', 'jessie', 'stretch', 'sid', 'precise', 'trusty', 'xenial', 'yakkety']`

- `nodejs_install_version`
> The to-be-installed "NodeJS"-version from NodeSource i.e. 5.x, 6.x or 7.x
>
> `""`

- `nodejs_install_apt_key_id`

> The identifier for the key of the NodeSource repository. Including this allows check mode to correctly report the changed state.
>
> `""`

- `nodejs_install_apt_key_url`

> The url to retrieve the apt-key for the NodeSource repository from.
>
> `"https://deb.nodesource.com/gpgkey/nodesource.gpg.key"`

- `nodejs_install_apt_repository_repo`

> A source string for the NodeSource repository.
>
> `"deb https://deb.nodesource.com/{{ nodejs_install_version }} {{ ansible_distribution_release|lower }} main"`

- `nodejs_install_apt_repository_validate_certs`

> If no, SSL certificates for the chronograf repository will not be validated.
>
> `"no"`

- `nodejs_install_apt_update_cache`

> Run the equivalent of apt-get update before the operation.
>
> `"yes"`

- `nodejs_install_apt_cache_valid_time`

> Update the apt cache if its older than the set value.
>
> `"3600"`

- `nodejs_install_package_list`

> The list of packages to be installed.
>
> `['nodejs']`


## Dependencies

None.

## License

MIT

## Author Information

* Patrick Ringl
