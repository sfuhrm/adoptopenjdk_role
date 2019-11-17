# AdoptJDK Ansible role

This Ansible Role installs the [AdoptJDK Java VM](https://adoptopenjdk.net/) java in a Debian/Ubuntu or CentOS environment

- [AdoptJDK Ansible role](#adoptjdk-ansible-role)
  - [Getting Started](#getting-started)
    - [Prerequisities](#prerequisities)
    - [Installing](#installing)
  - [Usage](#usage)
    - [Ansible](#ansible)
      - [OpenJDK](#openjdk)
  - [License](#license)

## Getting Started



### Prerequisities

To use this role as dependency in your playbook, prerequisites below:

Ansible 2.7.7 version installed.
Inventory destination should be a Debian/Ubuntu or CentOS environment.

For testing purposes you will need [Python 3.6+](https://www.python.org/downloads/release/python-368/) and [Pipenv](https://github.com/pypa/pipenv)

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

```yml
- src: http://github.com/sfuhrm/adoptjdk_role.git
  scm: git
  version: master
  name: adoptjdk_role
```

or using [Ansible Galaxy](https://galaxy.ansible.com/sfuhrm/adoptjdk_role/) as origin if you prefer:

```yml
- src: sfuhrm.adoptjdk_role
  version: master
  name: adoptjdk_role
```


Install the role with ansible-galaxy command:

```sh
$ ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```yml
---
- hosts: someserver
  roles:
    - adoptjdk_role
```

## Usage

### Ansible

[defaults/main.yml](https://github.com/sfuhrm/adoptjdk_role/blob/master/defaults/main.yml)

#### OpenJDK

A specific OpenJDK version can be selected by overriding the `adoptjdk_package` variable using group vars/host vars:

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

