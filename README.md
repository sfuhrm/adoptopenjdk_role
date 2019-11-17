# AdoptOpenJDK Ansible role

This Ansible Role installs the [AdoptOpenJDK Java VM](https://adoptopenjdk.net/) as a package in a Debian/Ubuntu or CentOS environment.

- [AdoptOpenJDK Ansible role](#adoptopenjdk-ansible-role)
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

To use this role as dependency in your playbook, prerequisites are described below:

* Ansible 2.4 version installed.
* Inventory destination should be a Debian/Ubuntu or CentOS environment.

### Configuring

The role has some defaults set as variables. If you want to override them, set the following variables in one the appropriate ansible places:

* **adoptopenjdk_package:** _adoptopenjdk-13-hotspot_
  
  This is the OS package name to install.
  See below for a list for Debian based systems.
* **adoptopenjdk_state:** _present_

  This is either "present" to install Java or "absent" to deinstall it.

Possible package names on Debian-based systems:

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

Create or add to your roles dependency file (e.g `requirements.yml`):

```yml
- src: http://github.com/sfuhrm/adoptjopendk_role.git
  scm: git
  version: master
  name: adoptopenjdk_role
```

or using [Ansible Galaxy](https://galaxy.ansible.com/sfuhrm/adoptopenjdk_role/) as origin if you prefer:

```yml
- src: sfuhrm.adoptopenjdk_role
  version: master
  name: adoptopenjdk_role
```


Install the role with the `ansible-galaxy` command:

```sh
$ ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```yml
---
- hosts: someserver
  roles:
    - adoptopenjdk_role
```

## Usage

### Ansible

The defaults for the role can be seen in [defaults/main.yml](https://github.com/sfuhrm/adoptopenjdk_role/blob/master/defaults/main.yml).

#### OpenJDK

A specific AdoptOpenJDK version can be selected by overriding the `adoptopenjdk_package` variable using `group_vars`/`host_vars`/`playbook.yml` vars:

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

