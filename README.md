# AdoptJDK Ansible role

This Ansible Role installs the [AdoptJDK Java VM](https://adoptopenjdk.net/) java in a Debian/Ubuntu or CentOS environment

- [AdoptJDK Ansible role](#adoptjdk-ansible-role)
  - [Getting Started](#getting-started)
    - [Prerequisities](#prerequisities)
    - [Configuring](#configuring)
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

### Configuring

The role has some defaults set. If you want to override them, set the following variables:

* **adoptjdk_package:** _adoptopenjdk-13-hotspot_
  
  This is the OS package name to install.
  See below for a list for Debian based systems.
* **adoptjdk_state:** _present_

  This is either "present" to install Java or "absent" to deinstall it.

Possible package names:

```
adoptopenjdk-11-hotspot
adoptopenjdk-11-hotspot-jre
adoptopenjdk-11-openj9
adoptopenjdk-11-openj9-jre
adoptopenjdk-11-openj9xl
adoptopenjdk-11-openj9xl-jre
adoptopenjdk-12-hotspot
adoptopenjdk-12-hotspot-jre
adoptopenjdk-12-openj9
adoptopenjdk-12-openj9-jre
adoptopenjdk-12-openj9xl
adoptopenjdk-12-openj9xl-jre
adoptopenjdk-13-hotspot
adoptopenjdk-13-hotspot-jre
adoptopenjdk-13-openj9
adoptopenjdk-13-openj9-jre
adoptopenjdk-13-openj9xl
adoptopenjdk-13-openj9xl-jre
adoptopenjdk-8-hotspot
adoptopenjdk-8-hotspot-jre
adoptopenjdk-8-openj9
adoptopenjdk-8-openj9-jre
adoptopenjdk-8-openj9xl
adoptopenjdk-8-openj9xl-jre
```

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

