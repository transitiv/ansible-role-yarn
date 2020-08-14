# Ansible Role: Yarn

[![Build Status](https://travis-ci.com/transitiv/ansible-role-yarn.svg?branch=master)](https://travis-ci.com/transitiv/ansible-role-yarn)

This role installs Yarn from the [Yarn package repositories](https://legacy.yarnpkg.com/en/docs/install) on systems running Debian/Ubuntu and RHEL/CentOS.

## Requirements

Root accesss is required for installing packages, so you must run it in a playbook with global root privileges or define `become: yes` when the role is included:

```yaml
- hosts: yarn_servers
  roles:
    - role: transitiv.yarn
      become: yes
```

## Dependencies

This role depends on the following roles:

* [transitiv.nodesource](https://galaxy.ansible.com/transitiv/nodesource)

## Variables

```yaml
yarn_version: stable
```

Defines the version of the Yarn repository that will be installed. The available options are currently:

* stable
* rc
* nightly

```yaml
yarn_packages:
  - yarn
```

Defines the package(s) installed by the role. This variable is "flattened" before it is used so it can contain nested lists if desired.

```yaml
yarn_packages_state: present
```

Defines the state of the packages defined in `yarn_packages`. See the `state` parameter in the apt and yum Ansible modules for valid values.

## License

This role is available under the terms of the MIT license.

## Author

This role was created by [Transitiv Technologes Ltd.](https://www.transitiv.co.uk).
