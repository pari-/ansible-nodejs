# nodejs

[![Build Status](https://travis-ci.org/pari-/ansible-nodejs.svg?branch=master)](https://travis-ci.org/pari-/ansible-nodejs)

An Ansible role which installs and configures NodeJS from NodeSource

<!-- toc -->

- [Requirements](#requirements)
- [Example](#example)
- [Defaults](#defaults)
- [Dependencies](#dependencies)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->

## Requirements

Currently this role is developed for and tested on Debian GNU/Linux (release: stretch).
The Ansible version used for tests can be found here: [Dockerfile](https://github.com/pari-/docker-debian-ansible/blob/master/debian/stretch/Dockerfile)

## Example

```yaml
---

- hosts: "all"
  roles:
    - role: "ansible-nodejs"
      tags:
        - "nodejs"

```

## Defaults

Available role variables and their respective default values are to be found in: [defaults/main.yml](https://github.com/pari-/ansible-nodejs/blob/master/defaults/main.yml)

## Dependencies

None

## License

MIT

## Author Information

* Patrick Ringl
