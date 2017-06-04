# nodejs

[![Build Status](https://travis-ci.org/pari-/ansible-nodejs.svg?branch=master)](https://travis-ci.org/pari-/ansible-nodejs)

An Ansible role which installs and configures NodeJS from NodeSource

<!-- toc -->

- [Requirements](#requirements)
- [Example](#example)
- [Role Variables](#role-variables)
- [Dependencies](#dependencies)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: jessie). It is assumed to work on other Debian distributions as well.

Ansible version compatibility:

- __2.3.1.0__ (current version in use for development of this role) 
- 2.2.3.0
- 2.1.6.0
- 2.0.2.0

## Example

```yaml
---

- hosts: "{{ hosts_group | default('all') }}"

  vars:

  roles:
    - { role: "{{ role_name | default('ansible-nodejs') }}", tags: ['nodejs'] }

```

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml). They're generally prefixed with `nodejs_` (which I deliberately leave out here for better formatting).

variable | default | notes
-------- | ------- | -----
`cache_valid_time` | `3600` | `Update the apt cache if its older than the set value (in seconds)`
`default_release` | `jessie` | `The default release to install packages from`
`package_list` | `['nodejs']` | `The list of packages to be installed`
`pre_default_release` | `{{ nodejs_default_release }}` | `The default release to install packages (pre_package_list) from`
`pre_package_list` | `['apt-transport-https','ca-certificates']` | `The list of prerequisite packages to be installed`
`repo_list[0]['repo']` | `deb https://deb.nodesource.com/{{ nodejs_version }} {{ nodejs_default_release }} main` | `Source string for the repositories`
`repo_list[0]['repo']['key']['id']` | `68576280` | `Identifier of (the repository) key`
`repo_list[0]['repo']['key']['keyserver']` | `keyserver.ubuntu.com` | `Keyserver to retrieve the key (for the repository) from`
`supported_distro_list` | `['jessie']` | `A list of distribution releases this role supports`
`update_cache` | `yes` | `Run the equivalent of apt-get update before the operation`

## Dependencies

None

## License

MIT

## Author Information

* Patrick Ringl
