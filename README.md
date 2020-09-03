# Fluentd Ansible Role

Fluentd is an open source data collector for unified logging layer.

## Installation

``` yaml
# requirments.yaml
- src: git@github.com:4lie/ansible-role-fluentd.git
  scm: git
  version: master
  name: fluentd
```

## Role Variables

``` yaml
```

## Example Playbook

``` yaml
- hosts: servers
  roles:
    - fluentd
```
