# [Ansible role consul](#ansible-role-consul)

Install and configure consul on your system.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-consul/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-consul/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-consul/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-consul)|[![downloads](https://img.shields.io/ansible/role/d/buluma/consul)](https://galaxy.ansible.com/buluma/consul)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-consul.svg)](https://github.com/buluma/ansible-role-consul/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-consul/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
- become: true
  gather_facts: false
  hosts: all
  name: Converge
  roles:
  - consul_bind_addr: 0.0.0.0
    consul_bootstrap_expect: 1
    consul_encrypt: 6r73CP0icJrap1tsQ17yuqzVguho4/yz+aI/dkVg2Kk=
    consul_services:
    - name: web
      port: 80
      tags:
      - rails
    role: buluma.consul
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-consul/blob/master/molecule/default/prepare.yml):

```yaml
- become: true
  gather_facts: false
  hosts: all
  name: Prepare
  roles:
  - role: buluma.bootstrap
  - role: buluma.core_dependencies
  - role: buluma.hashicorp
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-consul/blob/master/defaults/main.yml):

```yaml
consul_client_addr: 0.0.0.0
consul_data_dir: /opt/consul
consul_datacenter: my-dc-1
consul_install_package: true
consul_license: ''
consul_server: true
consul_ui: true
consule_service_started_and_enabled: true
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-consul/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Build Status GitHub](https://github.com/buluma/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-core_dependencies/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-core_dependencies)|
|[buluma.hashicorp](https://galaxy.ansible.com/buluma/hashicorp)|[![Build Status GitHub](https://github.com/buluma/ansible-role-hashicorp/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-hashicorp/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-hashicorp/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-hashicorp)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-consul/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-consul/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-consul/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

